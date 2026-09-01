# Project | Capstone | Round 1 | Cost Analysis
### John Adams

**Client:** Independent hair salon, Prenzlauer Berg, Berlin
**Scope:** MVP covering all 3 proposed use cases (Booking Assistant, No-Show & Cancellation Recovery, Retention & Re-Engagement)

## Consultant Rate

€900/day, mid-to-upper end of German freelance/independent consultant rates for automation and AI work (typical range €600-1,200/day depending on seniority and specialization). This is a planning assumption, not a quoted rate.

## One-Time Project Fee

| Phase | Consultant Days | Cost |
|---|---:|---:|
| Discovery & measurement setup (shared foundation) | 0.5 | €450 |
| Use Case 1: AI Booking & Inquiry Assistant | 3 | €2,700 |
| Use Case 2: No-Show & Cancellation Recovery | 2.5 | €2,250 |
| Use Case 3: Retention & Re-Engagement Automation | 4 | €3,600 |
| Integration & owner training (all 3) | 0.5 | €450 |
| **Total** | **10.5** | **€9,450** |

Use Case 3 costs more because it has three linked pieces (rebooking outreach, reorder reminders, product recommendations). Use Case 2 costs less because it reuses Use Case 1's booking infrastructure.

The project fee includes 2 weeks of post-launch support (bug fixes, tuning) as standard handover.

## Tooling Costs (Client-Paid)

The salon sets up and pays for all tool subscriptions directly, on their own card. We're granted admin and configuration access to build and maintain the workflows, but never own or bill through these accounts. This keeps the client in control of their own tools and avoids lock-in risk if the engagement ends.

| Tool | Purpose | Monthly Cost |
|---|---|---:|
| n8n | Powers all 3 automations | €20-50 |
| Twilio (SMS + WhatsApp) | Booking and retention outreach, reaches clients on either channel | €10-30 |
| LLM API | Conversational logic, message drafting | €20-40 |
| Airtable | Client data and notes storage | Free tier likely sufficient, or €10-20 if a paid tier is needed |
| **Total** | | **€50-140/month** |

## Ongoing Support (Optional)

The salon can walk away after handover and self-manage entirely, they own all the tool accounts. Two paid options if they want ongoing help:

**Option A: Monthly management retainer.** Proactive: tool updates, monitoring, minor tweaks, priority response. Client picks the structure:
- Flat fee: €200-300/month, or
- Percentage of tool spend: 10-15%, €150/month minimum

**Option B: On-demand hourly.** Reactive only, no monthly commitment: €120/hour when something breaks and they call. We do not proactively update, monitor, or maintain the tools under this option.

## Assumptions

| Assumption | Why |
|---|---|
| Consultant rate of €900/day | Mid-to-upper German freelance automation/AI consulting rate, not a vendor quote |
| Tool costs are estimates | Based on typical no-code tool pricing at this salon's low volume (4 chairs), not vendor quotes |
| Fee covers all 3 use cases as one MVP | Client can also choose fewer than 3, cost would scale down |
| No employee hiring required | Matches the fit constraint already established in `research/use_cases.md` |
| Client owns all tool accounts | Consultant has admin access only, no billing intermediary role |

## Sources

- [Use case proposals](../research/use_cases.md)
- [Sector research](../research/sector_research.md)
