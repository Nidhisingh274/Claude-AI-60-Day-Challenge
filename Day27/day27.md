# 🏥 Day 27 – Prior Authorization Story Simulator

> **#60DayClaudeChallenge** | Built with Claude · Anthropic AI

---

## 📌 What I Built

An **interactive educational web application** that teaches the complex Prior Authorization (PA) healthcare workflow through a conversational story — featuring Rahul (patient) and Priya (healthcare ops specialist) across **8 guided scenes**.

**App:** `pa-story-simulator.html` — Single-file HTML + Tailwind CSS + Vanilla JS

<img width="740" height="910" alt="pa-story-simulator" src="https://github.com/user-attachments/assets/e34d65d0-cf56-48f3-9fda-6f25020a2c02" />

**Features:**
- 8 story scenes covering the full Prior Authorization journey
- Branching choices after every scene (2 options each)
- Append-only chat feed — no innerHTML rewriting
- Real-time progress bar tracking across scenes
- Color-coded info cards (blue = info, amber = caution, red = denial, green = approval)
- Flow diagram: Provider → PA Request → Payer → Decision
- Completion stats screen with restart option

---

## 🚀 Prompt


```
Prior Authorization Story Simulator
Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
Use createElement + appendChild for every new chat bubble. Never call innerHTML = on the chat container.

Characters:
👦 Rahul — patient. Appears left.
👧 Priya — healthcare operations specialist. Appears right.
Narrators and doctors appear as centered italic text only, never chat bubbles.

Story — 8 scenes with append-only chat feed and progress bar:
1. Doctor Visit — Rahul visits City Medical Center. Dr. Patel diagnoses Rheumatoid Arthritis, prescribes Humira.
2. Insurance Roadblock — Dr. Patel's office submits PA directly to StarCare Health (payer). No pharmacy involved. Flow: Provider → PA Request → Payer. Approved PA is saved on file permanently.
3. What is PA? — Priya explains in plain language. Include: step therapy isn't just bureaucracy — for aggressive diagnoses, delays can affect disease progression. Cite: 'AMA 2023 PA Survey: PA causes treatment delays in the majority of cases.'
4. Insurance Review — Priya walks through what StarCare Health checks: eligibility, clinical documentation, ICD-10 diagnosis match, step therapy history. Explain why each matters.
5. Denial — Denied: missing step therapy documentation. Denial ≠ permanent. Priya notes the system side: 'PA denials cost physician offices 2+ staff hours to resolve.'
6. Appeal — Gather documents, Letter of Medical Necessity, formal appeal filing.
7. Approval — PA approved, saved on file. Reference number issued. No repeat PA needed for Humira.
8. Takeaways — Two perspectives: Patient (what Rahul learned) + System (how health systems track denial rate, appeal rate, resolution time).

After each scene show 2 choices that influence dialogue and progression.
Label StarCare Health as an illustrative example throughout.
Beginner-friendly language.
Healthcare education design system.
```

---

## 📸 Screenshots

### Scene 1 – Doctor Visit

<img width="725" height="741" alt="Doctor Visit" src="https://github.com/user-attachments/assets/7bf78aba-778f-4a62-b3eb-a9226e1ba195" />

### Scene 2 – Insurance Roadblock

<img width="675" height="82" alt="Flow Diagram" src="https://github.com/user-attachments/assets/fb6e998d-92db-4588-969c-b964d2bf7aca" />

### Scene 3 – What is PA?

<img width="691" height="646" alt="What is PA" src="https://github.com/user-attachments/assets/6137af29-1d89-4911-9fdf-2be1156a474c" />

### Scene 4 – Insurance Review

<img width="672" height="485" alt="Insurance Review" src="https://github.com/user-attachments/assets/8cc31df5-c348-4781-ad05-a8daf910832f" />

### Scene 5 – Denial

<img width="581" height="682" alt="Denial" src="https://github.com/user-attachments/assets/b74f7393-d724-4a16-bb99-400e5f9103cb" />

### Scene 6 – The Appeal

<img width="622" height="642" alt="Appeal" src="https://github.com/user-attachments/assets/c33f9af3-98c7-4fa7-95bb-2da477cdcd87" />

### Scene 7 – Approval

<img width="702" height="420" alt="Approval" src="https://github.com/user-attachments/assets/ef15f710-675b-4c7a-abc7-2d3a074d27cd" />

### Scene 8 – Takeaways

<img width="677" height="655" alt="Takeaways" src="https://github.com/user-attachments/assets/62167ad2-83a3-4b3d-b55b-b52da7323c2a" />

---

## 🔑 Key Takeaways from the PA Journey

- **Prior Authorization** is insurance approval required before covering high-cost medications like biologics
- **Step therapy** requires trying cheaper drugs first — skipping documentation of this is the #1 denial reason
- **Denial ≠ permanent** — most documentation-based denials are overturned on appeal
- **AMA 2023**: PA causes treatment delays in the majority of cases, with real clinical consequences
- **PA denials cost physician offices 2+ staff hours** per case to resolve
- Health systems track: Denial Rate, Appeal Rate, Resolution Time, Appeal Overturn Rate
- An approved PA stays on file — no repeat needed for the authorization period

---

## 🔑 Key Learnings

### About Prior Authorization
1. **PA is not a pharmacy step** — it goes directly from the provider's office to the payer (insurer). The pharmacy isn't involved until after approval.

2. **Step therapy is the #1 denial trigger** — insurers require proof that cheaper medications were tried first. Missing documentation of this = automatic denial.

3. **Denial is a checkpoint, not a dead end** — most documentation-based denials are overturned on appeal when the right evidence is submitted.

4. **Clinical delays have real consequences** — the AMA 2023 PA Survey found PA causes treatment delays in the majority of cases. For conditions like RA, even 4–8 weeks matters for disease progression.

5. **The administrative burden is significant** — PA denials cost physician offices 2+ staff hours per case to resolve, pulling clinical staff away from patient care.

### About Health Systems & Metrics
- **Denial Rate** — % of PA requests denied on first submission
- **Appeal Rate** — % of denials that are formally contested
- **Resolution Time** — avg. calendar days from submission to final decision
- **Appeal Overturn Rate** — % of appeals that succeed (a quality indicator)

### About Building with Claude
- Claude can generate complete, interactive educational web apps from a detailed prompt
- Specifying DOM manipulation rules (`createElement` vs `innerHTML`) in the prompt ensures cleaner, more maintainable code
- Character-based storytelling makes complex healthcare concepts accessible to beginners
- Branching dialogue trees can be implemented cleanly with vanilla JS choice handlers

--- 

## 🧠 What This Project Demonstrates

- Interactive storytelling as a teaching tool for complex workflows
- Claude generating complete single-file educational web apps
- Conversational UI design with branching decision trees
- Healthcare domain knowledge translated into beginner-friendly language
