# Project | Capstone | Round 1 | Automation POC Documentation
### John Adams

**Use case:** Use Case 3, Retention & Re-Engagement Automation (see `research/use_cases.md`).

## What it does

1. **Get Retention Clients**: reads all client rows from an n8n Data Table (`salon_retention_clients`), each row has name, email, last visit date, last purchase date, and last purchase category.
2. Two independent checks run on every client:
   - **Needs Rebooking?**: true if their last visit was more than 8 weeks ago.
   - **Needs Reorder?**: true if their last product purchase was more than 30 days ago.
   A client can trigger neither, one, or both, they are not mutually exclusive.
3. For each client that trips a check, an **AI Agent node** (GPT-4o-mini) drafts a short, warm, on-brand message. Rebooking gets a "we've missed you" nudge, reorder gets a product-specific reminder.
4. An **Override Email For Test** node redirects the recipient to one real test inbox (demo-only, see Limits below).
5. **Resend** sends the drafted message as an email to the client.

## Why it fits the use case

`use_cases.md` describes Use Case 3 as two linked nudges: "AI-drafted 'haven't seen you in a while' outreach" and "reorder reminders... based on purchase cadence." This workflow builds exactly that, using real AI drafting (not a hardcoded template) and real conditional logic on real client data, not a hypothetical description.

## Test run (real, not simulated)

Ran live twice against the Data Table's 5 sample clients (same clients used in `langsmith/langsmith_monitoring_sample.ipynb`, so both artifacts tell a consistent story):

| Client | Rebooking nudge? | Reorder nudge? |
|---|---|---|
| Anna Schmidt | Yes | No |
| Lukas Meyer | No | Yes |
| Sophie Wagner | Yes | Yes |
| Felix Braun | No | No |
| Mia Hoffmann | Yes | Yes |

Felix Braun correctly received nothing, recent visit and recent purchase. Sample drafted message: *"Hi Anna! We've missed you at Chleo Hair Studio. It would be wonderful to see you again soon. Let us know when you're ready for some pampering! The Chleo Hair Studio Team"*

**Second run confirmed real email delivery**, not just logic: with the Override Email For Test node redirecting all 5 clients to one real test inbox, and the `from` address set to Resend's built-in test sender (`onboarding@resend.dev`, works without domain verification), all 6 emails (3 rebooking, 3 reorder) were actually accepted and sent by Resend, each returning a real message ID (e.g. `dc3f8df3-6155-4691-9f4a-ac6515e18634`). Confirmed visible in the test inbox and in Resend's dashboard.

## Limits vs. production

- **Test inbox, not real clients**: the Override Email For Test node exists only for this demo, so every send goes to one real inbox instead of each client's own address. Production would remove this node entirely, letting the real per-client emails from the Data Table (or the salon's real booking system) receive the message.
- **Test sender, not a verified domain**: `onboarding@resend.dev` is Resend's zero-setup test sender. Production needs a domain verified with Resend under the salon's own name.
- **Data source is a test table, not the salon's real booking system**: production would pull from Acuity (the salon's actual tool) or a synced client database instead of a manually-entered n8n Data Table.
- **No human approval step**: `opportunities_risks.md` and the deck's Risks slide both flag that client-facing messages should be owner-approved before sending, this POC sends automatically to demonstrate the logic; production would likely add a review step for at least the first weeks of use.

## How to reproduce

1. Import `workflow.json` into your n8n instance (self-hosted or cloud).
2. Create a Data Table named `salon_retention_clients` with columns: `name` (string), `email` (string), `last_visit_date` (date), `last_purchase_date` (date), `last_purchase_category` (string). Add sample rows.
3. Connect an OpenAI credential and a Resend credential (HTTP Header Auth).
4. Set the Override Email For Test node's value to your own test inbox, or remove that node entirely to send to each client's real address.
5. Run the Start (manual trigger) node.
