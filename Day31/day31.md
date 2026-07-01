# Day 31 — AI Supply Chain Control Tower 🚛📡
### #60DayClaudeChallenge

---

## 🎯 What I Built

An **AI Supply Chain Control Tower** — a fully interactive, single-file HTML/CSS/JavaScript simulation that puts you in the seat of the **Head of Operations** at a global logistics company.

The app simulates a live control-tower dashboard where random operational disruptions (port congestion, supplier delays, truck breakdowns, demand spikes, customs holds, damaged shipments, etc.) stream in real time. Every decision I make — expedite a shipment, switch to a backup supplier, reroute trucks, approve air freight, or ignore the alert — directly moves live KPIs: **Service Level, Customer Satisfaction, Inventory Health, Transportation Efficiency, Operating Cost, and Revenue Protected**.

The entire simulation runs for a 3-minute "shift," gets harder as time goes on (more alerts, overlapping incidents), and ends with a full performance report card, a letter grade (A+ to D), and a shareable score.


---

## 🧠 Prompt

```
Act as an expert Product Designer, Operations Consultant, UX Designer, and Frontend Developer.

Build a complete interactive web application called:

# AI Supply Chain Control Tower

The goal is to simulate the experience of being the Head of Operations in a global supply chain company.

The entire project must be contained inside ONE self-contained HTML file using HTML, CSS, and vanilla JavaScript only.

Do NOT use React, Vue, Angular, Tailwind, Bootstrap, external libraries, APIs, or backend services.

Everything should work offline after opening the HTML file.

--------------------------------------------------
THEME
--------------------------------------------------
Create a premium dark Operations Control Center inspired by modern logistics dashboards.

Use:
• Dark background
• Blue and cyan highlights
• Red warning alerts
• Green success indicators
• Orange medium priority alerts

Animated glowing cards
Modern dashboard layout
Professional typography
Smooth transitions

--------------------------------------------------
GAMEPLAY
--------------------------------------------------
The player becomes: Head of Operations

A stream of operational alerts appears.
The player must decide which issue to solve first.
Every decision changes business KPIs.
The goal is to maximize operational performance before time runs out.

--------------------------------------------------
KPIs
--------------------------------------------------
Display these live metrics at the top:
Service Level %
Customer Satisfaction
Inventory Health
Transportation Efficiency
Operating Cost
Revenue Protected
Score
Remaining Time

--------------------------------------------------
ALERT TYPES
--------------------------------------------------
Randomly generate alerts like:
🚨 Port Congestion
🚨 Supplier Delay
🚨 Truck Breakdown
🚨 Warehouse Running Out of Stock
🚨 Customs Inspection
🚨 Demand Spike
🚨 Factory Machine Failure
🚨 Weather Disruption
🚨 Wrong Inventory Count
🚨 Damaged Shipment

Each alert should include:
Title, Short description, Priority, Time remaining, Business impact

--------------------------------------------------
PLAYER ACTIONS
--------------------------------------------------
Each alert should provide action buttons such as:
Expedite Shipment
Use Backup Supplier
Reroute Trucks
Increase Production
Transfer Inventory
Approve Air Freight
Ignore
Delay Decision

Each action should have different consequences.

--------------------------------------------------
GAME LOGIC
--------------------------------------------------
Choosing the best action:
Increase score, Improve KPIs, Reduce future risk

Wrong decisions should:
Reduce KPIs, Increase operating cost, Lower customer satisfaction

Some decisions should have delayed consequences after several seconds.

--------------------------------------------------
DIFFICULTY
--------------------------------------------------
Game lasts 3 minutes.
As time progresses: more alerts appear, alert frequency increases, multiple alerts stay active simultaneously.

--------------------------------------------------
VISUALS
--------------------------------------------------
Include:
Animated KPI cards, Live scrolling event log, Countdown timer, Priority color coding,
Small pulse animation for critical alerts, Hover effects, Professional dashboard layout

--------------------------------------------------
END OF GAME
--------------------------------------------------
When time ends show:
Final Score, Performance Grade (A+, A, B, C, D), Final KPI values,
Total Alerts Resolved, Correct Decisions, Wrong Decisions,
A short operational summary based on performance, Play Again button

--------------------------------------------------
EXTRA FEATURES
--------------------------------------------------
Add: Sound toggle (visual only), Pause button, Help / Instructions modal, Responsive layout for desktop and mobile

--------------------------------------------------
CODE QUALITY
--------------------------------------------------
Write clean, well-commented code. Keep CSS organized. Keep JavaScript modular using functions.
Everything must remain inside ONE HTML file.

Return only the complete HTML document.
```

---

## 📸 Screenshots

### 1️⃣ Start Screen

<img width="977" height="647" alt="start-screen" src="https://github.com/user-attachments/assets/8981bdc1-4799-4847-a80d-aa3c26c5f0fe" />


### 2️⃣ Live Dashboard

<img width="1887" height="657" alt="live-dashboard" src="https://github.com/user-attachments/assets/bcfb5448-e359-43c7-bc96-6b76b122a50e" />

### 3️⃣ Multiple Alerts

<img width="1867" height="876" alt="multiple-alerts" src="https://github.com/user-attachments/assets/c1a282f1-b59f-4662-b3e8-b7aafdca666a" />


### 4️⃣ Final Score Screen

<img width="992" height="816" alt="final-score" src="https://github.com/user-attachments/assets/1d7a7ba8-8baa-47f7-b528-059a5a1d7fc8" />

---

## 🏆 My Result

- **Final Score:** 3,513
- **Grade:** A+
- **Alerts Resolved:** 31
- **Correct Decisions:** 29
- **Wrong Decisions:** 2
- **Revenue Protected:** $397.2K
- **Final KPIs:** Service Level 100% · Customer Satisfaction 100% · Inventory Health 100% · Transport Efficiency 100%
- **Operating Cost:** $64K

> *"Exceptional shift. Barely felt the pressure. Made the right call on 94% of resolved decisions (29 correct, 2 wrong) across 31 total alerts."*

---

## 💡 Key Learnings

1. **Control towers exist to compress reaction time.** Real supply chain control towers work because they surface every disruption (port, supplier, transport, inventory) on one live screen instead of scattered across systems and teams — the same principle this simulation is built on.
2. **Every operational decision is a trade-off.** Choosing "Expedite Shipment" over "Ignore" isn't free — it costs money (Operating Cost) to protect Service Level and Customer Satisfaction. Good operations leadership is about which trade-offs to accept, not avoiding trade-offs altogether.
3. **Speed of decision matters as much as the decision itself.** Delaying a call didn't remove the problem — it just meant the consequence hit later, often bigger. This mirrors how unresolved supply chain issues compound instead of disappearing.
4. **Multiple simultaneous incidents test prioritization, not just knowledge.** As alert frequency increased, the real skill wasn't knowing the "correct" action for each alert type — it was correctly triaging which fire to fight first under time pressure.
5. **Prompt engineering for simulations needs explicit systems thinking.** To get Claude to build a coherent "game," I had to specify not just visuals but the *underlying logic system*: KPIs, scoring rules, consequence timing, and difficulty scaling — proof that good AI-generated apps need well-structured, systems-level prompts, not just feature lists.
6. **One-file vanilla JS builds are still powerful.** No frameworks, no backend, no APIs — and yet Claude generated a fully animated, stateful, real-time dashboard simulation that runs entirely offline in a browser.

---

## 🔗 Real-World Application

This exercise mirrors how enterprises like retailers, manufacturers, and 3PLs use actual Control Tower software (e.g., visibility platforms tracking ocean freight, trucking, warehouse inventory, and supplier performance) to make faster, KPI-informed operational decisions. Understanding this loop — **alert → prioritize → decide → measure impact** is directly transferable to real operations, logistics, and supply chain management roles.

📁 **Generated File:** `ai-supply-chain-control-tower` is included in this repository. Just click to open it locally in your browser!
