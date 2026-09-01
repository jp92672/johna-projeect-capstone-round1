# Project | Capstone | Round 1 | Sector Research
### John Adams

**Client:** Independent hair salon, Prenzlauer Berg, Berlin
**Sector:** Hair & beauty services (Germany) · **Company size:** Micro business
**Segment:** High-end independent, appointment-only, €90-115 cuts, €145-275 color services
**Structure:** 2 owner-operators, 2 chair renters, no employees, open Tue-Sat

## Market Size & Structure

- **80,363 registered hairdressing salons in Germany**, as of the end of 2024. That is down slightly from 80,476 in 2023 [Branchenbericht 2024/2025].
  - What it means: the number of salons in Germany is not growing. It has been slowly shrinking for years.
  - Why it matters: this salon can't grow by "the market getting bigger." Growth has to come from doing more with the 4 chairs it already has.
- **€7.49bn in taxable turnover for 2023**, up 5.9% from 2022 [Statistisches Bundesamt].
  - What it means: even though the number of salons is shrinking, the total money the industry makes is going up.
  - Why it matters: existing salons are earning more each. This supports the same "grow from what you have" idea above.
- **Haircut prices rose faster than general prices in 2024.** Women's cuts +4.0%, men's cuts +4.0%, children's cuts +4.2%, versus 2.2% general inflation [Statistisches Bundesamt].
  - What it means: salons in this segment can raise prices and clients still pay.
  - Why it matters: as prices go up, every missed appointment costs more. This makes no-show and cancellation recovery more costly every year.
- **Over 70% of German salons have fewer than 5 employees.** Only 0.2% have more than 50.
  - What it means: a small salon with no employees, like this one, is the normal size for the industry.
  - Why it matters: none of our proposed solutions require hiring staff. That matches how the whole industry is operating lean.
- **Berlin's population was 3,700,577 at the end of 2025**, up 0.4% year over year [Amt für Statistik Berlin-Brandenburg].
  - What it means: this is background information about the city population growth.
  - Why it matters: Berlin's population is growing steadily each year with a potential pool of new clients (not all will be seeking high-end services). This is the starting point for the market size breakdown below.

### Market Opportunity Size (TAM, SAM, SOM)

Dashboard: `dashboard/01_tam_sam_som.csv`

- **TAM (total market): 3.7 million Berlin residents.** All potential clients citywide. Too broad to plan around, most residents aren't a fit for this salon's price point.
- **SAM (serviceable market): an estimated 20,000-60,000 people.** A modeled range of premium-appropriate clients within reach of the salon's location and pricing, not a measured number.
- **SOM (obtainable market): about 1,700-2,300 active clients.** The number this salon actually needs to run at 82% utilization, based on its own capacity (4 chairs, 152 chair-hours/week) and an assumed 1.5-2.0 visits per client per year. Capacity and utilization-target modeling from `research/external/Market Data Sheet | Premium Independent Hair Salon, Prenzlauer Berg, Berlin.md`, Section 1.
  - Why it matters: this salon isn't trying to capture a slice of 3.7 million people. It needs a few thousand loyal clients. That's a specific, reachable target, not a citywide growth problem.

## Labor Market & Training

- **Sector employment fell 2.6% in 2024** compared to 2023. 21,209 hairdressers were registered unemployed in 2024, up 3.8% from 2023 [Branchenbericht 2024/2025, citing Bundesagentur für Arbeit].
  - What it means: fewer people are working as hairdressers in Germany each year.
  - Why it matters: if this salon ever needs to replace a stylist or a chair renter, it will be harder to find one.
- **National apprentice numbers rose 2.8% in 2024**, the first rise in over a decade. **Berlin apprentice numbers fell 2.1%** in the same year, to 468.
  - What it means: nationally, more young people are starting to train as hairdressers. In Berlin, it's the opposite.
  - Why it matters: the local Berlin talent pipeline is shrinking even as the rest of the country improves. Losing a stylist here could be a risk in trying to secure a replacement.
- **Job vacancies in the sector fell 3.9% in 2024** (3,471 average reported openings, down from 3,612 in 2023).
  - What it means: salons are posting fewer job openings.
  - Why it matters: this likely means salons are scaling back on hiring under tight margins and operational costs.

## Operational Benchmarks (US/Canada Zenoti platform data)

| Metric | Average | Top earner |
|---|---:|---:|
| Online booking rate | 30% | 59% |
| Rebooking within 24 hours | 10% | 30% |
| Staff/chair utilization | 67% | 84% |
| Cancellation rate | 8% | n/a |
| No-show rate | 3% | n/a |

What each row means and why it matters:
- **Online booking rate.** Even at average salons, most bookings don't go through the salon's own system. This matches this salon's exact problem: clients call, WhatsApp, email, and DM instead of using Acuity.
- **Rebooking within 24 hours.** Top salons lock in a client's next visit right after their current one, most salons don't.
- **Staff/chair utilization.** Top salons fill more chair time than average ones. At €102/hour (average of the salon's Short, Mid, and Longer/Fuller cut prices, from `research/Salon Pricing.md`), 152 chair-hours/week, and 48 weeks/year, each point of utilization is worth about €7,442/year. The 17-point gap between average and top earners (67% to 84%) is about €126,513/year (see `dashboard/02_salon_utilization_opportunity.csv`). This uses one flat rate for all 4 chairs as a simplification. 2 chairs are rented and priced by the renters, so this is a rough planning estimate.
- **Cancellation and no-show rate.** Out of 100 appointments, about 8 get cancelled and 3 are no-shows, on average. This gives a starting point for how much lost time this salon might be dealing with.

Additional findings, and why they matter:
- **80% of salon and spa guests want to book by mobile phone.** [Zenoti, "Beauty & Wellness Industry Statistics 2025"] Supports building a simple chat-based booking assistant instead of a phone-only process.
- **42% of loyal clients (more than one visit a year) generate 80% of revenue.** [Zenoti, "Beauty & Wellness Industry Statistics 2025"] A small group of repeat clients brings in most of the money. Keeping them happy matters more than chasing new clients.
- **New client visits fell 9% in 2024, while existing client visits rose 1%.** [Zenoti, "Beauty & Wellness Industry Statistics 2025"] Industry-wide, fewer new people are coming in, but existing clients are visiting slightly more. This is more evidence that retention is the stronger opportunity right now, not new client growth.
- **71% of regular clients had skipped booking because it was too hard.** [Zenoti, "Salon Booking Flow Optimization: Convert More Guests in 2026" — a different Zenoti article from the one above] Booking friction pushes clients away, not just the owner's time.

## Relevance to This Salon

- Acuity is already in place, but calls, WhatsApp, email, and Instagram DMs bypass it, creating manual work for the owners.
- With only 4 chairs and no way to add staff, using existing chair-hours better matters more than finding new clients. The utilization numbers above are a comparison point once this salon's own hours are tracked.
- The owners report no-shows and late cancellations weekly to bi-weekly, and charge a €50 deposit. The deposit covers some of the financial loss, not the empty chair-time. The benchmarks above are a reference point, not this salon's actual rate.
- Retail is underdeveloped relative to the salon's upscale product line (Head On, Wella, Davines). Zenoti suggests 10-15% of service revenue as a rough reference, but it's vendor commentary, not a verified number.
- No solid Germany-specific data exists for haircare reorder cycles or product pairings.

## Sources

- [Consultant briefing](Berlin%20Hair%20Salon%20Industry_Consultant%20Briefing_V3.md)
- Zentralverband des Deutschen Friseurhandwerks, [Branchenbericht 2024/2025](external/Branchenbericht-2025.pdf): primary Germany-specific source
- IBISWorld, [Hairdressing & Beauty Treatment in Germany Industry Analysis, 2025](https://www.ibisworld.com/germany/industry/hairdressing-beauty-treatment/992/)
- Zenoti, [Beauty & Wellness Industry Statistics 2025](https://www.zenoti.com/thecheckin/beauty-wellness-industry-statistics-2025)
- Zenoti, [Salon Booking Flow Optimization: Convert More Guests in 2026](https://zenoti.com/thecheckin/salon-medspa-booking-flow-revenue/)
- Amt für Statistik Berlin-Brandenburg, [population statistics](https://www.statistik-berlin-brandenburg.de/presse/2026/73-bevoelkerungsfortschreibung-2025-berlin/)
- [Additional research notes](external/)
