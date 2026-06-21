# Day 21 — Digital Privacy Intelligence Dashboard

**#60DayClaudeChallenge** · Built with Claude

## 🎯 Task

Build an interactive HTML dashboard that visualizes a digital footprint and privacy exposure from a self-reported list of apps — no real account, device, or database access involved. The dashboard covers a Digital Footprint Score, Privacy Score, Exposure Heatmap, Company Exposure Ranking, Data Collection Matrix, Risk Radar, Digital Twin Profile, Most Valuable Data Assets, a Privacy Improvement Simulator, and a Final Verdict.

## 🧠 Prompt Used

<details>
<summary>Click to expand the full prompt</summary>

```
### Sample User Dataset
Use the following dataset as the user's reported digital footprint.
Facts:
Applications : Instagram, Snapchat, TikTok, YouTube, Discord, WhatsApp, iMessage, Spotify, Roblox, PUBG Mobile, Amazon, Meesho, Google Search, Google Pay, Google Photos
Dataset Rules:
* Treat all listed services as Facts.
* Use these services to calculate all scores, exposure rankings, heatmaps, risk levels, ecosystem concentration, digital twin insights, data collection likelihood, and privacy recommendations.
* Infer parent companies from the services.
* Any behavioural, demographic, lifestyle, shopping, spending, entertainment, mobility, travel, communication, or technology-related conclusions must be labeled as Estimates.
* Never claim certainty.
* Never claim access to private databases.
* If information cannot reasonably be inferred, display: 'Not enough information provided.'

# Output Requirement
Generate a complete interactive HTML artifact starting with <style>.
Do not output markdown.
The artifact should feel like a premium cybersecurity dashboard.

Design Inspiration:
Notion, Stripe Dashboard, Linear, Google Privacy Checkup, Apple Privacy Reports, Modern SaaS Analytics Platforms.

### Dashboard Overview
Create a visually rich dashboard containing:
1. Digital Footprint Score (0-100)
2. Privacy Score (0-100)
3. Exposure Heatmap
4. Company Exposure Ranking
5. Data Collection Matrix
6. Risk Radar
7. Digital Twin Profile
8. Most Valuable Data Assets
9. Privacy Improvement Plan

Display:
Digital Footprint Score
🟢 0-30 = Minimal | 🟡 31-60 = Moderate | 🟠 61-80 = Significant | 🔴 81-100 = Extensive

Privacy Score
🔴 0-30 = Weak | 🟠 31-60 = Fair | 🟡 61-80 = Good | 🟢 81-100 = Strong

Include: Total Services Used, Number of Parent Companies, Ecosystem Concentration Score, Estimated Tracking Surface.

Create all sections exactly as specified including Digital Twin Profile, Exposure Heatmap,
Company Exposure Ranking, Data Collection Matrix, Risk Radar, WOW Insights,
Most Valuable Data Assets, Privacy Improvement Simulator, and Final Verdict.

Critical Rules:
* Never claim access to private databases.
* Never claim certainty about inferred traits.
* Separate Facts from Estimates.
```

</details>

## 🛠️ What I Built

A single self-contained HTML file (no external backend) that:
- Computes a **Digital Footprint Score** and **Privacy Score** from a 15-app dataset, with a transparent (illustrative) scoring breakdown.
- Tags every claim as **FACT** (reported), **DERIVED** (calculated from facts), or **ESTIMATE** (inferred, not certain) — so nothing is presented as more certain than it is.
- Renders an **Exposure Heatmap**, a ranked **Company Exposure list**, a 15×6 **Data Collection Matrix**, a 6-axis SVG **Risk Radar**, a **Digital Twin Profile**, a **Most Valuable Data Assets** ranking, **WOW Insights**, a live **Privacy Improvement Simulator** (checkbox toggles that recalculate scores in real time), and a **Final Verdict**.
- Repeats the disclaimer throughout: no account, device, or private database was accessed — this is a self-reported-data exercise, not a real audit.

## 📊 Dashboard Screenshots

<img width="1187" height="827" alt="Score Overview" src="https://github.com/user-attachments/assets/48ba8278-7329-40c8-9fc5-ddd5a10d9225" />

<img width="1201" height="797" alt="Exposure Heatmap" src="https://github.com/user-attachments/assets/a1de151b-988e-4343-9006-41892c3d9a4b" />

<img width="1082" height="880" alt="Company Exposure Ranking" src="https://github.com/user-attachments/assets/59168d36-0e85-4a58-b89b-a2018c3940f3" />

<img width="1072" height="455" alt="Risk Radar" src="https://github.com/user-attachments/assets/bccd3f3d-3fba-482f-8317-e81ea28c9cff" />

<img width="1067" height="482" alt="Digital Twin Profile" src="https://github.com/user-attachments/assets/c7b27fa0-25b7-448b-9ce7-54d46caf4d06" />

<img width="1062" height="497" alt="Privacy Improvement Simulator" src="https://github.com/user-attachments/assets/14b260e5-9316-4dec-b056-e05db340a83d" />

<img width="1067" height="441" alt="Final Verdict" src="https://github.com/user-attachments/assets/98146209-c7a7-4264-83bb-b6b8c1162cb9" />

## 🔐 Privacy & Risk Insights (Estimates — not facts)

- **Digital Footprint Score: 78/100 — 🟠 Significant.** Driven mainly by service volume (15 apps) and category diversity (social, messaging, gaming, shopping, finance, cloud).
- **Privacy Score: 38/100 — 🟠 Fair.** Pulled down by heavy data-minimization gaps and a concentrated ecosystem.
- **Ecosystem concentration:** 4 of 15 services (YouTube, Search, Pay, Photos) sit inside a single company — Google/Alphabet — making it the single highest-exposure company at an estimated 91/100.
- **Risk Radar:** Social Exposure (85) and Behavioral Profiling (80) are the two highest-risk dimensions; Communication Privacy Risk (50) is the lowest, mainly because WhatsApp and iMessage are end-to-end encrypted by default.
- **Most valuable data assets (estimated):** Location history and payment/shopping behavior rank highest in commercial value, ahead of social graph and search/content behavior.
- **Surprising finding:** 15 apps map to 11 separate parent companies — almost a 1:1 ratio — meaning data isn't just "a lot," it's also widely scattered across unrelated companies.

## 🧪 Risk Analysis

The biggest single lever isn't any one app — it's the **Google account**, which alone touches four different data categories (search history, video behavior, payments, and personal photos). Turning off ad personalization and avoiding "Sign in with Google" on third-party apps were the two simulator actions with the best privacy-gain-to-effort ratio.

## 💡 Key Learnings

- Claude can build a fully interactive, well-structured dashboard (live gauges, SVG radar chart, a working simulator) entirely in one HTML artifact with no backend.
- Separating **Fact / Derived / Estimate** at the UI level (not just in a disclaimer) is a strong pattern for any AI tool that makes inferences about a person — it keeps the tool honest without watering down the insight.
- A "privacy score" is most useful when it's paired with a **simulator**: seeing the number move when you toggle a setting makes the advice feel actionable instead of abstract.
- Real-world application: this same Fact/Derived/Estimate + simulator pattern could extend to a personal-finance dashboard, a resume/ATS scorer, or any tool that mixes hard data with model inferences.

## ▶️ How to Run

1. Download `digital_footprint_dashboard.html`.
2. Open it directly in any modern browser (Chrome, Edge, Firefox, Safari) — no server needed.
3. Scroll through each section; toggle the checkboxes in the **Privacy Improvement Simulator** to see the scores update live.
