# Day 16 — Build Your First Stock Research Skill

## What I Built

A custom Claude Skill called **`stock-fundamental-research`** which is a reusable AI workflow that performs deep fundamental analysis on any Indian or global listed stock without needing to re-enter the prompt every time.

---

## Steps Completed

### 1. Created the Custom Skill

- Navigated to **Skills** in Claude.ai
- Clicked **"New Skill"**
- Set **Skill Name**: `stock-fundamental-research`
- Pasted the **Description** (covering Indian & global listed companies, financial statements, competitive analysis, valuation, risks)
- Pasted the full **Instructions** (including modes: Quick Take, Deep Dive, Compare, Pros & Cons, Portfolio Fit)
- Saved the skill

<img width="1902" height="787" alt="skill-creation-screenshot" src="https://github.com/user-attachments/assets/3bc81a28-fa28-4f98-9f71-516ac6c18a4e" />

---

### 2. Tested the Skill — Reliance Industries Deep Dive

Activated the skill by selecting it, then sent:

```
/stock-fundamental-research analyse Reliance stock
```

Claude fetched live data from Screener, Tickertape, Kotak Neo, Moneycontrol, and BSE, then auto-generated a full 8-tab HTML research report.

<img width="987" height="182" alt="skill-selected-screenshot" src="https://github.com/user-attachments/assets/787c20b2-bb09-4d5a-aafc-d8514c038179" />

---

## Key Findings — Reliance Industries (NSE: RELIANCE) as of June 16, 2026

| Metric | Value |
|---|---|
| CMP | ₹1,331 |
| Market Cap | ₹17.68L Cr |
| P/E | 40.3× |
| 52W Range | ₹1,253 – ₹1,612 |
| FY26 Revenue | ₹11.76L Cr (+9.8% YoY) |
| FY26 EBITDA | ₹2.07L Cr (+13.4% YoY) |
| FY26 PAT | ₹95,754 Cr (+17.8% YoY) |
| ROE | 8.80% |
| ROCE | 9.18% |
| Net Debt | ₹1,24,717 Cr |
| Net Debt/EBITDA | 0.60× |
| Promoter Holding | 50.00% (zero pledging) |

**Overall Fundamental Quality: ⚡ Moderate-to-Strong**

---

## Report Tabs Generated

The HTML report included all 8 tabs:

1. **Snapshot** — CMP, Market Cap, 52W range, face value
2. **Valuation** — P/E, P/B, EV/EBITDA vs sector and 5Y average
3. **Growth** — Revenue, Profit, EPS CAGR (3Y/5Y), quarterly EPS trend
4. **Health** — D/E, Interest Coverage, Current Ratio, FCF
5. **Returns** — ROE & ROCE (current, 3Y avg, 5Y avg), Dividend history
6. **Peers** — Top 3 peers with P/E, P/B, ROE, Revenue Growth, D/E
7. **Ownership** — Promoter, FII, DII trends across 8 quarters
8. **View** — Strengths, watch-points, key metric to track, overall quality, disclaimer

<img width="1872" height="912" alt="reliance_deep_dive" src="https://github.com/user-attachments/assets/97f1074d-27bc-46f2-a92c-18d5497418d1" />

<img width="1877" height="901" alt="report-valuation-tab" src="https://github.com/user-attachments/assets/7f64e11d-c699-4cf8-96c1-0defc2867667" />

<img width="1870" height="905" alt="report-ownership-tab" src="https://github.com/user-attachments/assets/3381194c-3a4c-485b-8aaf-8d10c9da5762" />

---

## What Surprised Me

> Consumer businesses (Jio + Retail + Media) contributed **over 55% of consolidated EBITDA** for the first time in FY26 marking the completion of RIL's transformation from an energy company to a diversified consumer conglomerate.

And despite a ₹1.24L Cr net debt, the **Net Debt/EBITDA ratio is just 0.60×** indicating very comfortable leverage for a company of this size.

---

## Key Learnings

1. **Custom Skills eliminate prompt fatigue.** Once saved, the entire 500-word research prompt is invoked with a single `/skill-name` trigger — no copy-pasting ever again.

2. **Structured research > ad-hoc querying.** The 8-tab Deep Dive template forces systematic thinking: valuation → growth → health → returns → ownership, rather than jumping to one metric.

3. **Data sourcing matters.** The skill instructs Claude to cross-check figures across at least 2 sources (Screener, Tickertape, Moneycontrol, NSE/BSE). This significantly reduces hallucination risk for financial data.

4. **ROE ≠ the whole story.** Reliance's 8.8% ROE looks weak by the >15% benchmark, but it's distorted by an enormous equity base from decades of retained earnings and capex cycles — context from the report made this clear.

5. **Jio Platforms IPO is the single biggest catalyst** to watch for Reliance — management hinted at a mid-2026 timeline, which could unlock massive value.

6. **Reusability is the superpower.** The same skill works for TCS, HDFC Bank, Infosys, or any listed stock — the workflow adapts automatically.

---

## Disclaimer

*This is a fundamentals view for educational purposes only. It is not investment advice and not a buy/sell/hold recommendation. Verify all figures independently. The final decision is yours.*
