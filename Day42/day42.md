# Build Personal Financial Command Center
### Create Your AI-Powered Financial Dashboard

This repository/submission documents the build of a **Personal Financial Command Center** — a single-file, self-contained HTML dashboard generated with Claude that helps track income, expenses, budgets, savings runway, job-search momentum, and a personalized financial health score.

---

## 🧠 The Prompt Used

Below is the exact prompt given to Claude to generate the dashboard:

```
# Personal Financial Command Center
You are an expert financial planner, budgeting specialist, investment advisor, UI/UX designer, data visualization expert, and senior frontend developer.
Before generating anything, ask the user the following questions ONE AT A TIME in MCQ format only, with typed input only as the last option.
1. Who is this financial dashboard for?
(Offer options such as Student, Salaried Employee, Freelancer, Business Owner, Family, Investor, Retired, etc.)
2. Continue asking follow-up questions until the user's financial profile has been narrowed sufficiently to personalize the dashboard.
Do not stop after identifying only the user type. Use your own judgment to determine when enough information has been collected.
3. Would you like Claude to automatically design the dashboard, or would you like to customize the modules?
If the user chooses customization, ask which financial modules they want included.
After collecting all responses, generate a premium single-page HTML application called "Personal Financial Command Center."
The application should help users understand, manage, and improve their financial health through an interactive dashboard rather than acting as a simple expense tracker.
Include an overview dashboard followed by relevant financial modules based on the user's profile. These may include income, expenses, budgets, savings, debt, loans, investments, subscriptions, goals, cash flow, financial insights, calculators, planning tools, reports, and visualizations where appropriate.
Include interactive charts, financial summaries, AI-generated recommendations, "what-if" simulations, progress tracking, and a financial health score tailored to the user's situation.
Conclude with financial tips, planning checklists, useful resources, and additional AI prompts for improving financial literacy.
Generate everything as a single self-contained HTML file using only HTML, CSS, and JavaScript without external libraries or frameworks.
Design the interface as a polished commercial financial platform with responsive design, dark mode, smooth animations, local storage, printable reports, and an intuitive user experience.
```

Claude then asked a short series of MCQ-style questions (user type → current situation → top priority → debt status → timeline → auto-design vs. customize → module scope), and used the answers to tailor the dashboard's modules, copy, and financial-health-score logic to the resulting profile.

---

## 📸 Screenshots

<img width="1092" height="867" alt="Overview" src="https://github.com/user-attachments/assets/40bc434c-6b7a-4f9a-80a1-48f1e7593a58" />

<img width="1103" height="914" alt="Learn   Resources" src="https://github.com/user-attachments/assets/a47e37e3-4ee1-46ca-976e-bc92b18e6568" />

---

### Key Learnings
- **What I completed:** Went through Claude's guided MCQ intake (user type → current situation → top priority → debt status → timeline → auto-design vs. customize), then got a fully working, single-file HTML dashboard back — no separate backend, no build step, just one file that opens in a browser and persists data via local storage.
- **What surprised me:** Claude didn't just drop in generic "income/expense tracker" modules, it reframed the whole dashboard around the profile it was given. For a job-seeker living on family support, the headline visual became a "runway" (how many months the money lasts) instead of a generic net-worth chart, and a job-application funnel sat right next to the budget, treating the job search itself as a financial variable.
- **Most useful module:** The what-if simulator paired with the runway strip. Being able to drag a slider and watch the runway number react in real time made the trade-off between cutting a specific expense and buying more job-search time immediately obvious something a static spreadsheet never communicated as clearly.
- **A real bug I caught:** The financial health score originally gave full "runway" points any time income matched expenses even with ₹0 in savings, or with literally no data entered at all. Pointing this out to Claude got it fixed in one pass: it now distinguishes "no data yet," "breakeven with zero buffer," and "true stable surplus with a cushion," and the score itself was reweighted so a zero-buffer breakeven scores meaningfully lower than a breakeven backed by real savings.
- **Real-world application:** Beyond the challenge, this kind of profile-aware, single-file dashboard pattern is genuinely reusable, the same approach (interview the user first, then generate a tailored tool instead of a generic template) works for budgeting, project trackers, or any small internal tool that would otherwise need a "one-size-fits-all" form.

---
