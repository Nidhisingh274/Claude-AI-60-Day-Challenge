# Day 30 — Supply Chain Optimizer

Built a complete interactive **Supply Chain Optimizer** simulation using Claude — a single-file React app that teaches supply chain fundamentals through hands-on decision making, like a real operations leader.

<img width="1092" height="892" alt="Welcome screen" src="https://github.com/user-attachments/assets/f450a172-1e5b-4ec0-95da-ae35ab8a8de6" />

---

## What I Built

A fully self-contained HTML app that:

1. Welcomes the user with a beginner-friendly explanation of what a supply chain is and why it matters.
2. Randomly generates a company profile (industry, products, countries served, demand level).
3. Walks the user through 5 real supply chain decisions:
   - Supplier strategy (single vs. multiple vs. global suppliers)
   - Factory location (domestic, nearshore, offshore, distributed)
   - Warehouse strategy (centralized, regional, distributed micro-fulfillment, drop-ship)
   - Transportation method (road, rail, sea, air)
   - Inventory strategy (low / just-in-time, balanced, high safety stock)
4. Explains the trade-off of every choice in plain English **before and after** selection.
5. Updates 5 live business metrics in real time after every decision: Cost Efficiency, Delivery Speed, Risk Resilience, Customer Satisfaction, Sustainability.
6. Generates a final dashboard with an Overall Supply Chain Score (0–100), strengths, weaknesses, biggest risk, and 3 concrete improvement recommendations all derived dynamically from the choices made.

---

## The Prompt

```
You are an expert frontend developer, UX designer, game designer, and supply chain consultant.
Build a complete single-file HTML app named 'Supply Chain Builder'.
Design it so a complete beginner can understand supply chains. Before every decision, explain what the concept means, why it matters, and how it affects a business.
Requirements:
* Output ONLY one HTML file.
* React via CDN + Babel JSX.
* Plain HTML, CSS, and JavaScript only.
* No Tailwind, npm, backend, APIs, images, or external assets.
* Runs offline by opening the HTML file.
* No placeholders or incomplete features.
Flow:
1. Welcome screen introducing supply chains in simple language.
2. Generate a random company (industry, products, countries served, demand level).
3. Guide the player through building their supply chain by choosing:
   * Number of suppliers (single or multiple)
   * Factory location
   * Warehouse strategy
   * Transportation method (road, rail, sea, air)
   * Inventory strategy (low, balanced, high)
4. After every choice, explain the trade-offs in plain English.
5. Display live business metrics that update after each decision:
   * Cost
   * Delivery Speed
   * Risk
   * Customer Satisfaction
   * Sustainability
6. At the end, generate a dashboard with an Overall Supply Chain Score (0-100), strengths, weaknesses, biggest risk, and three practical improvements.
Design:
* Premium enterprise dashboard.
* Dark theme.
* Responsive.
* Smooth transitions.
* Rounded cards.
* Hover effects.
* Animated progress bars.
* Replay button.
Randomize company details each playthrough. Organize the app into reusable React components using useState. Ensure every button works and return ONLY the complete HTML inside one code block.
```

---

## Screenshots

### Run 1: Company generated (Summit Collective)

<img width="1667" height="787" alt="Summit Collective" src="https://github.com/user-attachments/assets/03a38479-dbce-4498-b165-584faf64c25a" />

### Run 1: Supplier decision with trade-off + updated metrics

<img width="1322" height="882" alt="Supplier decision" src="https://github.com/user-attachments/assets/aff007a9-8a06-43f4-b5a3-ef611b194353" />

### Run 1: Final dashboard (Score 68/100)

<img width="846" height="907" alt="Run 1 Final dashboard" src="https://github.com/user-attachments/assets/42321ff1-ea03-4705-8c8e-557a2557ffc5" />

### Run 2: Company generated (Meridian Collective) — replay proof

<img width="1617" height="790" alt="Meridian Collective" src="https://github.com/user-attachments/assets/c9da308d-8a6c-4630-a7ca-f507c993c06e" />

### Run 2: Final dashboard (Score 67/100)

<img width="827" height="897" alt="Run 2 Final dashboard" src="https://github.com/user-attachments/assets/788e8ce5-58c4-4d9c-ac49-50bade258db3" />

---

## Generated HTML File

> The complete single-file application is uploaded as `supply-chain-builder.html` in `/Day30/`. Open it directly in any browser — no installation, no server, no internet connection required after the page loads its fonts/icons.

---

## Key Learnings

**1. Optimization is a sequence of trade-offs, not a single right answer.**
Every decision in the simulator pulls metrics in different directions — picking global suppliers crushed Cost Efficiency but maxed out Risk Resilience in Run 1. There is no "perfect" supply chain, only a chain that's well-suited to a specific company's demand level, products, and market. This is exactly how real operations leaders think: every choice is a deliberate trade, not a free win.

**2. The biggest single decision early in the chain has compounding downstream effects.**
In both runs, the supplier strategy chosen in Decision 1 was the factor most responsible for the "biggest risk" flagged in the final dashboard even though Decisions 2 through 5 happened much later. This mirrors real supply chains, where sourcing decisions made at the very start of a project are usually the hardest and most expensive to reverse later (e.g. moving away from a single supplier after a factory is already built around their materials).

**3. Claude can model business systems, not just generate UI.**
What stood out most building this with Claude wasn't the dark-theme dashboard or the animated progress bars, it was that the underlying scoring logic (cost/speed/risk/satisfaction/sustainability deltas per choice, the weighted final score, and the dynamically generated strengths/weaknesses/improvements) all had to be internally consistent business logic, not just decorative numbers. Claude generated a working simulation engine inside a single HTML file, with no backend, that produces different but always-coherent outcomes depending on user choices.

**4. Randomization + consistent logic = genuine replayability.**
Because the company profile, demand level, and starting conditions randomize each playthrough while the underlying trade-off math stays fixed, two runs (Summit Collective at 68/100 and Meridian Collective at 67/100) told two different stories even though the final scores were close proving the simulation responds meaningfully to different inputs rather than just reshuffling cosmetic details.

**5. Real-world application.**
This kind of interactive, consequence-driven learning tool is genuinely useful beyond the challenge. It could be adapted for onboarding new operations hires, teaching MBA/business students supply chain fundamentals, or even as a lightweight internal training tool for non-supply-chain teams (marketing, finance) to understand why logistics decisions affect cost and customer experience the way they do.

---

## Final Score Summary

| Run | Company | Industry | Overall Score | Biggest Risk |
|-----|---------|----------|---------------|---------------|
| 1 | Summit Collective | Pharmaceuticals & Health | **68 / 100** | Cost Efficiency (28/100) — driven by "4+ Global Suppliers" |
| 2 | Meridian Collective | Toys & Games | **67 / 100** | Sustainability (47/100) — driven by supplier/transport choices |
