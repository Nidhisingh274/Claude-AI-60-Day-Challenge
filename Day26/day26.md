# Day 26 — Prior Authorization Workflow Simulator

<img width="1011" height="842" alt="Prior Authorization Workflow Simulator — cover" src="https://github.com/user-attachments/assets/98b95217-7e0b-407f-b3d5-5c346df81532" />


**#60DayClaudeChallenge | Day 26 of 60**

A gamified, drag-and-drop simulation of the US healthcare **Prior Authorization (PA)** process built as a single self-contained HTML file using Claude.

---

## 📌 What this project is

Prior Authorization is one of the most misunderstood (and most frustrating) parts of the US healthcare system. Patients hear "we need to get this pre-approved" and have no idea what's actually happening behind the scenes between their doctor's office and their insurance company.

This simulator turns that invisible back-office process into something you can *see and play through*: drag a patient's case folder across three lanes — **Patient → Provider → Payer** — and experience medical necessity review, document collection, payer submission, and every possible outcome (Approval, Pend, Denial, Appeal, Peer-to-Peer Review) exactly the way it happens in real revenue-cycle operations.

It was generated end-to-end by Claude that runs in any browser with no setup.

---

## 🧠 The exact prompt used

> **Prior Authorization Workflow Simulator (gamified, drag-and-drop)**
>
> Build a single-file, self-contained HTML application (HTML + CSS + vanilla JavaScript, no external dependencies, no build step) that visually simulates the US healthcare Prior Authorization (PA) workflow as an interactive, gamified, drag-and-drop experience.
>
> The simulator should include:
> - Three workflow lanes: Patient, Provider, and Payer.
> - Interactive drag-and-drop movement of cases between stages.
> - Multiple patient scenarios (elective surgery, MRI, specialty medication, inpatient admission).
> - Medical necessity evaluation.
> - Prior Authorization document collection.
> - Submission to payer.
> - Review outcomes including Approval, Pend, Denial, Appeal, and Peer-to-Peer Review.
> - Educational explanations after every step.
> - Progress tracker across the top.
> - Days elapsed counter.
> - Efficiency score.
> - Celebration animation on approval.
> - Workflow summary on completion.
> - Responsive modern UI using shades of blue with black text.
> - Working Restart / New Patient button.
> - Fully functional buttons and interactions.
>
> **Technical Requirements:**
> - Single HTML file.
> - HTML, CSS and Vanilla JavaScript only.
> - No frameworks.
> - No CDNs.
> - No localStorage.
> - All workflow state managed in JavaScript memory.
> - Well-commented code.
> - Scenario data stored in an editable array near the top.
> - Output only the complete HTML file without truncation.

**Claude effort level used:** Low
**Output:** One complete, working `pa_simulator.html` file, generated in a single pass.

---

## 🛠️ What Claude actually built

| Requirement | How it's implemented |
|---|---|
| 3 workflow lanes | `Patient` / `Provider` / `Payer` swimlanes rendered as distinct colored sections |
| Drag-and-drop | Native HTML5 Drag & Drop API — drag the case folder card into the highlighted lane, or click the drop-slot button |
| 4 patient scenarios | Elective Surgery, MRI Imaging, Specialty Medication, Inpatient Admission — stored in an editable `SCENARIOS` array at the top of the file |
| Medical necessity evaluation | A dedicated workflow stage in the Provider lane, with educational context on payer policy matching |
| Document collection | An interactive checklist modal — incomplete documentation measurably lowers approval odds, mirroring real PA behavior |
| Submission to payer | A stage that hands the case from Provider → Payer lane |
| Review outcomes | Weighted-random **Approval / Pend / Denial**, plus branching **Appeal** and **Peer-to-Peer Review** paths after a denial |
| Educational explanations | Every single action logs a 💡 "what this means" explanation in the workflow log |
| Progress tracker | A top rail showing all 6 stages with a moving case-folder marker |
| Days elapsed counter | Increments realistically per stage (e.g., payer review takes longer than submission) |
| Efficiency score | Rewards complete documentation and fast pend responses; penalizes incomplete submissions and denials |
| Celebration animation | DOM-based confetti burst fires on approval |
| Workflow summary | Final modal recapping outcome, total days, efficiency score, pend count, and whether appeal/P2P were used |
| Blue UI, black text | Custom token system: navy/blue palette with near-black ink text throughout |
| Restart / New Patient | Picks a fresh random scenario and resets all in-memory state |
| No localStorage | All state lives in a single in-memory JavaScript object, exactly as required |

---

## 🖼️ Screenshot walkthrough

<img width="1021" height="871" alt="New case started" src="https://github.com/user-attachments/assets/56e125b2-a9c6-4b66-b20e-36ae24190d63" />

<img width="995" height="912" alt="2" src="https://github.com/user-attachments/assets/d2c7f7b3-048c-4a42-b497-9edbe5f3fc55" />

<img width="981" height="497" alt="collecting documents" src="https://github.com/user-attachments/assets/4ea2d97a-82dc-4001-9a36-75bc2613e379" />

<img width="982" height="912" alt="4" src="https://github.com/user-attachments/assets/d16b18fd-e709-4e4b-8520-d2be425a8687" />

<img width="972" height="382" alt="additional info request" src="https://github.com/user-attachments/assets/72efff55-58cd-44ef-b2f1-ef9faababba4" />

<img width="1020" height="370" alt="approved" src="https://github.com/user-attachments/assets/4f950a0d-653f-4133-9a5d-04d82354129e" />

<img width="426" height="447" alt="workflow summary" src="https://github.com/user-attachments/assets/cae9dc93-9a44-4434-80d4-90193e92811f" />

<img width="977" height="292" alt="complete workflow" src="https://github.com/user-attachments/assets/9734fca2-baf3-47e3-8ac0-df471e6d6931" />

---

## 📊 Sample completed run

| Metric | Result |
|---|---|
| Scenario | Specialty Medication — Biologic Therapy (Adalimumab) |
| Final Outcome | ✅ Approved |
| Total Days Elapsed | 16 |
| Efficiency Score | 100 |
| Times Pended | 1 |
| Peer-to-Peer Used | No |
| Appeal Filed | No |

This run shows a realistic pattern: the case was **pended once** (the payer asked for more clinical detail), the provider responded promptly with the missing information, and the case was ultimately **approved** — all logged step-by-step in the workflow log with plain-English explanations of *why* each thing happened.

---

## 💡 Key learnings

**On the Prior Authorization process itself:**
- PA isn't one step — it's a relay race across three different organizations (patient, provider, payer), each with their own clock, their own paperwork, and their own incentives.
- **Documentation completeness is the single biggest lever** in the entire process. An incomplete packet doesn't just risk a denial — it usually triggers a "Pend," which silently adds days back onto a case while everyone waits.
- A "Pend" is not a denial. It's a request for more information, and responding quickly is one of the few things a provider's office can fully control in an otherwise slow, opaque system.
- A denial isn't the end of the road. **Peer-to-Peer Review** (a direct doctor-to-medical-director conversation) and **formal Appeals** exist specifically because paperwork alone often fails to capture clinical nuance — and many denials *do* get overturned at this stage.
- Regulated review windows (commonly 72 hours for urgent requests, up to 14 days for standard ones) exist, but the clock effectively pauses during a pend — which is exactly why turnaround times vary so wildly in the real world.

**On building this with Claude / AI-assisted development:**
- A single, well-structured prompt — with explicit technical constraints (single file, no frameworks, no localStorage, commented code, editable data array) — produced a fully working, dependency-free interactive application in one pass.
- Keeping all scenario data in one editable array near the top of the file makes the simulator trivially extensible — new patient scenarios (e.g., behavioral health, durable medical equipment) could be added without touching any rendering logic.
- Gamification elements (progress rail, efficiency score, confetti, stamped outcome cards) made a genuinely dry back-office workflow feel tactile and engaging — proof that AI-assisted UI generation can make compliance-heavy, B2B-style processes approachable for a general audience, not just healthcare insiders.
- This kind of rapid, interactive prototyping is directly relevant to **healthcare operations + AI roles**: turning a process SME's mental model into something a non-expert can explore hands-on is exactly the kind of artifact product, ops, and L&D teams need.

---

## 🚀 How to run it

1. Download [`pa_simulator.html`](./pa_simulator.html)
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari) — no server, no install
3. Pick a patient scenario, drag the case folder through each lane, and play through to a final outcome
4. Click **Restart / New Patient** to try a different scenario

---

## 🔗 Project links

- **Generated HTML file:** [`pa_simulator.html`](./pa_simulator.html)
