# Project | Capstone | Round 1 | Use Case Proposals
### John Adams

**Client:** Independent hair salon, Prenzlauer Berg, Berlin
**Segment:** High-end independent, appointment-only, €90-115 cuts, €145-275 color services
**Structure:** 2 owner-operators, 2 chair renters, no employees, open Tue-Sat

Fit constraint: any solution must run with no added headcount, low ongoing admin burden for 2 working owners, and low/no-cost tooling (free tiers used to demo logic, not necessarily the named production tool).

## Use Case 1 — AI Booking & Inquiry Assistant

**Problem:** Bookings are meant to run through the Acuity Scheduling tool, but clients also call, WhatsApp, email, and DM directly. The owner has to explain unavailability and manually arrange alternate dates with such clients.

**Solution:** A conversational assistant (chat/WhatsApp-first, phone optional) that checks real Acuity availability and responds to inquiries directly. It confirms open slots, redirects to booking, or flags when the salon is genuinely full and suggests the next opening. The owner is not in the loop for routine cases.

**Fit for company size:** Removes a recurring manual task from 2 people with no admin support, and doesn't require new hires or complex integration. A lightweight assistant reading a shared calendar fits a 4-chair shop.

## Use Case 2 — No-Show & Cancellation Recovery

**Problem:** No-shows/late cancellations happen weekly to bi-weekly. A €50 deposit is charged under a set cancellation window, but it doesn't recover the lost chair-time itself. That slot still sits empty.

**Solution:** Automated pre-appointment reminders to reduce no-shows in the first place, plus an automated waitlist that gets pinged the moment a slot opens up from a cancellation.

**Fit for company size:** Fully automatable with no staffing need. Directly recovers revenue that is currently just lost.

## Use Case 3 — Retention & Re-Engagement Automation

**Problem:** Retail revenue is light and inconsistent despite an upscale, exclusive product line (Head On, Wella, Davines). There's no structured process for encouraging repeat visits or repeat product purchases — it happens passively via loyalty and word of mouth only.

**Solution:** Three linked nudges:
1. **Rebooking outreach**: "haven't seen you in a while" messages based on last-visit history
2. **Reorder reminders**: for existing clients, based on purchase cadence (e.g. a client who buys shampoo roughly monthly gets a nudge around day 28-30)
3. **Simple product recommendations**: lightweight rule-based matching, not a full e-commerce recommendation engine (e.g. color clients → color-care shampoo, styling-heavy clients → a specific styling product). This applies to new clients too, since it's based on service type, not purchase history.

**Fit for company size:** Turns an existing strength (loyal client base, quality retail line) into a proactive revenue stream without new staff or a sales process. Rule-based recommendations keep this achievable at their scale, unlike the complex recommendation engines e-commerce platforms run.

---

## Market/Operational Data Needed

The SWOT and use cases above are grounded in owner-provided detail and the sector briefing, but the dashboard and cost/ROI story need harder numbers. Flagging what's missing so it can be sourced (Kaggle, Hugging Face, or other public datasets) or reasonably estimated if unavailable:

- **Salon/appointment booking dataset**: realistic appointment volume, duration, and no-show/cancellation rates for a small service business, to model Use Case 1 & 2 metrics (chair utilization, no-show rate) if no real booking export is available
- **Beauty/personal care retail purchase-cycle data**: typical reorder intervals for haircare products (shampoo, styling, color-care), to ground the Use Case 3 reorder-reminder logic in real consumer behavior rather than a guessed 30-day cycle
- **Berlin/Germany hair salon market sizing or benchmark data**: visit frequency trends, average spend, digital adoption rates, to support the sector_research.md validation (the briefing has some of this, but current-year confirmation would strengthen it)
- **Customer churn / re-engagement response-rate benchmarks**: for a service or retail business, to set a realistic expectation for how much a "haven't seen you" nudge actually recovers (avoids overpromising ROI in Round 2)
- **Haircare product/service pairing data**: e.g. a retail transaction or market-basket style dataset, to ground the simple rule-based recommendation logic in real product-affinity patterns rather than guessed pairings

## Sources

- [Consultant briefing](Berlin%20Hair%20Salon%20Industry_Consultant%20Briefing_V3.md)
- [Sector research](sector_research.md)
- [Opportunities & risks](opportunities_risks.md)
