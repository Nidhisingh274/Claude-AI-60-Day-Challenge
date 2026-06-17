# Day 17 — AI Vehicle Cost & Fuel Analysis Dashboard

**Challenge:** 60 Day Claude Challenge
**Tool used:** Claude (claude.ai, web chat)
**Vehicle profile:** Maruti Suzuki Baleno · Petrol · Mixed usage · 700 km/month · 3 years old

Prompt Used:

```
## Details
- Vehicle : [YOUR VEHICLE MODEL]
- Fuel    : [Petrol/Diesel/CNG/E85/EV]
- Usage   : [City/Highway/Mixed/Fleet]
- KM/month: [e.g. 1000]
- Car Age : [e.g. 3 yrs]

## Role
Data analyst. Read attached CSV → compute metrics → output one HTML dashboard. HTML only, no explanation.

## Compute (group by Fuel_Type)
1. Avg Cost/km        = Fuel_Cost_INR ÷ Distance_km
2. Avg CO₂/km         = CO2_emitted_kg ÷ Distance_km
3. Avg Maintenance/km = Maintenance_Cost_INR ÷ Distance_km
4. Avg Refuel time    = Refuel_Recharge_time_min
5. Age buckets: New(0-2y) Mid-life(3-5y) Aged(6-9y) Old(10+y)
   → show Cost/km and Maint/km per bucket. Mark [CAR AGE] yrs.
6. E85 Paradox:
   - Pump saving    = ((Petrol_price−E85_price)/Petrol_price)×100
   - Running penalty= ((E85_cpkm−Petrol_cpkm)/Petrol_cpkm)×100
   - Break-even     = (E85_mileage÷Petrol_mileage)×Petrol_price
7. E85 Score/10: cost=4pt CO₂=3pt refuel=2pt maint=1pt

## Dashboard (no CDN, pure SVG charts, CSS in <style>, JS in <script>)
Dark navy #0a0f1e, glassmorphism. Colours: E85=amber Petrol=blue Diesel=grey CNG=green EV=purple.

1. Header — '[YOUR VEHICLE] · [FUEL] · Age:[CAR AGE]y · [KM/month]km/mo'
2. KPI Cards (5) — your fuel cost/km | E85 cost/km | E85 premium vs Petrol | break-even price | your monthly cost
3. SVG bar chart: Cost/km per fuel | SVG doughnut: CO₂/km per fuel (hover tooltips)
4. SVG line chart: Cost/km vs age (0-12y) per fuel. Vertical line at [CAR AGE].
5. SVG gauge: E85 score/10 (CSS animated). One verdict sentence.
6. Fuel cards: highlight [FUEL] with glow. Each: 2 pros ✅ 2 cons ❌ best-for 🚗

Output: <!DOCTYPE html> only. All numbers from CSV. Responsive 375px–1440px.

```

---

## 1. What I built

I gave Claude a 52-row CSV of trip-level fuel data across five fuel types (CNG, Diesel, E85/Flex-Fuel, Petrol, Electric) and asked it to turn that into a single, self-contained HTML dashboard — no chart libraries, no CDN, pure SVG, dark glassmorphism UI. Claude read the CSV, computed every metric itself (cost/km, CO₂/km, maintenance/km, refuel time, age-bucket breakdowns, and an "E85 Paradox" set of pump-saving vs running-cost calculations), and shipped one HTML file with five KPI cards, a bar chart, a doughnut chart, a line chart with a linear trend per fuel, an animated gauge, and five fuel comparison cards.

The dashboard is parameterized to my own vehicle (Petrol Baleno, age 3, 700 km/month), so the "your cost" KPIs and the highlighted fuel card reflect my actual situation rather than a generic average.

## 📸 Screenshots

### Overview

<img width="1280" height="256" alt="01_header_kpi" src="https://github.com/user-attachments/assets/ad2714a3-5f5a-4841-85af-3b7e87761017" />

### Cost & Emissions

<img width="1280" height="471" alt="02_cost_emissions_charts" src="https://github.com/user-attachments/assets/4e54e824-5e2a-4b84-8d82-551627d62f1b" />

###  Age Bucket Analysis

<img width="1280" height="243" alt="03_age_buckets" src="https://github.com/user-attachments/assets/a2fa0f76-8c25-42cc-81b0-343b94d37132" />

### Trend Analysis

<img width="1280" height="511" alt="04_cost_vs_age_line_chart" src="https://github.com/user-attachments/assets/1a0bbef2-d93a-4421-8e2f-9f801b569048" />

### E85 Score/Verdict

<img width="1280" height="304" alt="05_e85_gauge_verdict" src="https://github.com/user-attachments/assets/9f841330-5451-4307-b3c9-612416b902b9" />

### Fuel Comparison Cards 

<img width="1280" height="325" alt="06_fuel_comparison_cards" src="https://github.com/user-attachments/assets/dbb6fb5b-f049-4844-a38e-2e02bca6747d" />

---

## 2. Key insights from the dataset

**The E85 Paradox is real.** E85 is priced about 18% cheaper than Petrol at the pump (₹82/L vs ₹100/L), which sounds like an obvious win. But because E85's typical mileage is roughly 21% lower (12.9 km/L vs 16.3 km/L), the actual cost per kilometre comes out *higher* — ₹6.37/km vs ₹6.15/km, a 3.6% running-cost penalty. The cheaper pump price doesn't survive contact with the worse mileage. E85 only becomes cheaper to run than Petrol once its price drops below roughly ₹79.1/L — the break-even point.

**Electric is in a different league entirely on running cost.** EV cost/km in this dataset (₹1.75/km) is less than a third of Petrol's, and EV also has the lowest maintenance/km (₹0.23). The trade-off is operational, not financial: a 45-minute recharge versus a 5-minute Petrol fill, and a much shorter range per full charge in this sample (6.9 km per charge-unit vs 16.3 km/L for Petrol).

**E85 wins decisively on emissions.** Despite losing on running cost, E85 has the lowest CO₂/km of all five fuels (0.070 kg/km), beating even EV (0.091 kg/km) and Petrol (0.171 kg/km) in this dataset. If the goal is tailpipe emissions rather than cost, E85 is the standout — just not a free lunch.

**Maintenance cost rises faster with age than fuel cost does.** Pooling all fuel types by vehicle-age bucket, cost/km moves from ₹4.23 (new) to ₹5.29 (10+ years) — a ~25% increase — but maintenance/km moves from ₹0.35 to ₹1.41, roughly a 4x increase. Aging hits the maintenance line much harder than the fuel line.

**My own car sits in a reasonable spot.** At 3 years old, my Petrol Baleno's mid-life bucket (3–5y) shows the *lowest* pooled cost/km of any age bucket (₹4.09) in this dataset — slightly better than the New bucket, likely because very new vehicles in the data include some higher-cost fuel types. Maintenance/km at this age (₹0.56) is moderate, well short of the Aged or Old buckets.

**E85 suitability score: 5.7/10.** Weighting cost (4pt), CO₂ (3pt), refuel time (2pt), and maintenance (1pt) and scoring each fuel relative to the best- and worst-performing fuel in the dataset on each metric, E85 lands at 5.7/10 — solidly middle of the pack. It loses points on cost and refuel speed but gains them back on CO₂ and maintenance.

---

## 3. How data visualization helped

Looking at the raw CSV, the E85 paradox is not obvious — you'd have to mentally divide fuel cost by distance for every row, then average by fuel type, then separately compute mileage ratios, before noticing that the "cheaper" fuel is actually pricier per kilometre. Putting the cost/km bar chart next to the doughnut for CO₂/km made the trade-off visible at a glance: E85's bar is the tallest (worst cost), but its doughnut slice is the smallest (best emissions). That single side-by-side comparison communicated the entire paradox without needing to read a number.

The line chart (cost/km vs. vehicle age, 0–12 years) was useful for a different reason — it let me see that the *ordering* of fuels by cost/km stays consistent across the whole age range; the lines don't cross. That's a more reassuring signal than a single age-bucket snapshot, because it means the conclusion ("Petrol and E85 are the priciest, EV the cheapest") holds regardless of how old the car is.

The gauge for the E85 score did the most compression: four weighted sub-scores collapsed into one number and one needle position, which is honestly the fastest way to communicate "is this worth switching to" without making the reader do mental arithmetic on four separate metrics.

---

## 4. Learnings

- A clear, structured prompt (explicit formulas, explicit groupings, explicit chart types) produces a dashboard that's directly usable — Claude computed every derived metric (cost/km, CO₂/km, maintenance/km, age buckets, pump saving %, running penalty %, break-even price) correctly from raw CSV columns without needing follow-up corrections.
- Constraining the tech stack ("pure SVG, no CDN, CSS in `<style>`, JS in `<script>`") forced a genuinely portable single-file output — it opens identically in any browser with no external dependencies and no network calls.
- Parameterizing the dashboard to a specific vehicle (rather than leaving it generic) made the KPIs personally meaningful instead of abstract averages, which is the difference between "a dashboard" and "my dashboard."
- The E85 Paradox is a good reminder that pump price and running cost are two different numbers, and headline savings can evaporate once mileage is factored in — a pattern that generalizes well beyond fuel, to any "cheaper per unit but you need more units" decision.

---

## 5. Real-world application

This same pattern — read transactional/log-level data, compute per-unit economics, and surface a trade-off that isn't visible in the raw numbers — applies directly to other recurring-cost decisions: comparing electricity tariff plans against actual usage logs, evaluating cloud compute instance types against workload logs, or comparing subscription tiers against actual usage. The "cheaper sticker price, worse per-unit economics" pattern shows up constantly once you're looking for it.

---

*All figures in this report and the dashboard are computed directly from `day17_e85_dataset_optimised.csv` (52 trip records, 5 fuel types) using Claude.*
