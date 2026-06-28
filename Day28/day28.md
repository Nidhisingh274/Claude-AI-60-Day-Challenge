# Day 28 — Hospital Admission Readiness Simulator

An interactive, browser-based healthcare workflow simulation built entirely from a single Claude prompt exploring how hospital admissions are coordinated between providers, insurance, utilization review, and nursing teams.

## 🎯 What I Learned

1. **Admission Readiness** — the operational checklist (PA, documentation, orders, insurance, consent, bed) that has to clear before a patient can be admitted.
2. **Healthcare Operations** — how Prior Authorization status, documentation completeness, and payer verification each carry different weight toward an admission decision.
3. **Risk Management** — how to track and reduce administrative risk (insurance, bed, documentation) separately from clinical risk (diagnosis severity, ICU/Acute MI/CHF cases).
4. **Interactive Simulation Design** — how Claude can generate a complete, stateful, browser-based workflow app — scoring engine, branching logic, and all — from one structured prompt.

## 🧠 The Prompt Used

```
Hospital Admission Readiness Simulator
Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
style: same as previously established
Healthcare simulation design system. Task-first — no dashboard on load.
User plays Hospital Admission Coordinator.
Setup — collect:
- Provider, Attending Physician
- Diagnosis: Acute MI / CHF / Pneumonia / Elective Surgery / Hip Fracture
- Admission Type: Inpatient / Observation / Emergency / ICU / Same-Day Surgery
- PA Status, Admission Date
Observation Status must always show: 'CMS 2-Midnight Rule applies — different cost-sharing, SNF eligibility, and billing than inpatient. Medicare patients require written MOON notification.'
Label all provider/payer names as illustrative training data.
Button: 🏥 Analyze Admission Readiness

Initial Analysis
Generate status for: PA, Insurance, Bed, Documentation, Physician Orders, Consent.
Readiness Score 30–60%. Do not reveal final decision yet.
Score Weighting:
PA Status 25% · Clinical Documentation 20% · Physician Orders 20% · Insurance 15% · Consent 10% · Bed 10%
Denied PA + ICU admission cannot reach 70% from admin tasks alone.

PA Branches:
Approved → continue.
Pending → Follow Up, Upload Docs, Contact Physician.
Denied → Review Reason, Contact Insurance, Submit Appeal.
Successful appeal converts to Approved.

Workflow Actions:
Assign Bed / Verify Insurance / Upload Documentation / Complete Consent / Contact Physician / Notify Nursing / Prepare Patient Arrival

Acute MI and CHF trigger a criteria note:
'InterQual/Milliman thresholds apply — ensure documentation meets medical necessity standards before UR review.'

Timeline milestones:
PA Review → Insurance Verification → Bed Assignment → Documentation → Consent → Patient Arrival → Registration → Clinical Assessment → Admission Complete

Care Coordination Cards:
Attending / Case Manager / Nursing / Utilization Review / Discharge Planner
UR card must name: concurrent review, denial risk identification, InterQual, Milliman.

Risk Tracking:
Documentation Risk / Insurance Risk / Bed Risk / Clinical Risk
Clinical Risk weighted higher for Acute MI, CHF, ICU.

At Readiness ≥ 75% show Governance Snapshot:
'Industry benchmarks (estimates only): PA turnaround 3–5 days · Inpatient denial rate ~8–10% (CMS) · PA rework cost ~$11/transaction (CAQH)'

Final Decision:
≥ 90% → ✅ Admit — full summary.
< 90% → ⚠ Not Ready — missing items, required actions, remaining risks.
```

## 🛠️ What I Built

A fully interactive single-file HTML/Tailwind/vanilla-JS simulator with:
- A task-first intake screen (no dashboard until a case is opened)
- A live weighted readiness scoring engine (PA 25% · Documentation 20% · Orders 20% · Insurance 15% · Consent 10% · Bed 10%)
- Branching Prior Authorization workflows (Approved / Pending / Denied → Appeal)
- A 9-step admission timeline, Care Coordination roster, and Risk Tracking panel
- A Governance Snapshot that appears once readiness crosses 75%
- A final Admit / Not Ready decision screen

📄 **Generated app file:** `hospital-admission-readiness-simulator.html` (in this folder)

## ✅ Completed Admission Scenarios

| | Case 1 | Case 2 |
|---|---|---|
| Diagnosis | Hip Fracture | Pneumonia |
| Admission Type | Same-Day Surgery | Inpatient |
| Attending (illustrative) | Dr. Nikita | Dr. Tanu |
| Starting PA Status | Pending | Denied |
| PA Path Taken | Follow Up → Upload Docs → Contact Physician | Review Reason → Contact Insurance → Submit Appeal → **Approved** |
| Final Readiness Score | **91%** | **100%** |
| Final Decision | ✅ Admit — Readiness Confirmed | ✅ Admit — Readiness Confirmed |

Between the two cases, both non-Approved PA branches (Pending and Denied → Appeal) were fully exercised, along with every workflow action (bed, insurance, documentation, consent, physician contact, nursing notification, patient arrival).

## 💡 Key Learnings & Real-World Application

- **Prior Authorization is the single heaviest lever (25%)** in the readiness score — far more than bed assignment or consent. In real hospital ops, this matches reality: PA delays are consistently cited as the top driver of admission/discharge bottlenecks.
- **A "Pending" PA can still clear the 90% admit threshold** through other completed tasks — in Case 1, the simulator admitted the patient at 91% while PA status was still showing "Pending," because the Pending branch's actions (Follow Up, Upload Docs, Contact Physician) raise the *score* without ever converting the *status* to Approved. This is a useful real-world parallel: administrative throughput on other fronts can mask an unresolved payer-side gap if a system isn't designed to hard-block on it.
- **Denial isn't terminal** — the Denied → Review Reason → Contact Insurance → Submit Appeal path shows how a denial can be fully reversed and still reach a clean 100% readiness score, mirroring how UR teams use InterQual/Milliman criteria to build appeal cases.
- **Clinical risk vs. administrative risk are tracked separately** — and clinical risk is explicitly weighted higher for Acute MI, CHF, and ICU admissions, reflecting how medical necessity scrutiny is sharper for higher-acuity cases.

## 📸 Screenshots

### Intake / Setup screen

<img width="706" height="541" alt="Setup screen" src="https://github.com/user-attachments/assets/4595d373-5944-455d-8a96-912d635fe6d6" />

### Initial Analysis

<img width="767" height="277" alt="Initial Analysis" src="https://github.com/user-attachments/assets/1dbcae3d-097d-4ee2-9952-36041926de73" />

### PA Branch in progress

<img width="772" height="162" alt="PA Branch in progress" src="https://github.com/user-attachments/assets/09c85469-ee0a-4c00-a8a2-1f40e6a60a46" />

### Workflow Actions completed

<img width="801" height="407" alt="Workflow Actions completed" src="https://github.com/user-attachments/assets/0458c87c-7de3-4001-b8bd-a031b97482ae" />

### Governance Snapshot visible 

<img width="776" height="185" alt="Governance Snapshot visible" src="https://github.com/user-attachments/assets/a290f6a4-345a-4a54-af7c-7baccf8a1562" />

### Final Decision — Case 1 

<img width="767" height="342" alt="Final Decision — Case 1 " src="https://github.com/user-attachments/assets/e4b35c11-9cae-4ea6-ae86-e1c105d62ce2" />

### Final Decision — Case 2

<img width="896" height="412" alt="Final Decision — Case 2" src="https://github.com/user-attachments/assets/8493beca-3249-4829-8da4-eeebedadc400" />
