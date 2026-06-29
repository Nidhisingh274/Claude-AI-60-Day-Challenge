# Day 29: Operation Lifeline - Supply Chain Crisis Lab 🏭

## 📋 Task Overview
**Lead an enterprise through a supply chain crisis.**
Supply chain leaders constantly balance operational efficiency, customer satisfaction, supplier relationships, and business continuity. This project uses AI to generate an interactive simulation that teaches enterprise decision-making through engaging business scenarios.

### What I Learned:
1. **Supply Chain Strategy:** How organizations respond to operational disruptions.
2. **Business Decision Making:** Balancing cost, inventory, and customer satisfaction.
3. **AI in Operations:** Exploring how AI improves forecasting, procurement, and risk management.
4. **Interactive React Apps:** Building complete enterprise simulations using Claude (Single-file HTML/React).

---

## 🚀 The Build: Operation Lifeline
I used Claude to generate a complete, interactive, offline React HTML application. The simulator randomly generates a company, throws a catastrophic supply chain crisis at it, and forces the user to make executive decisions in a War Room, negotiate with suppliers, and invest in AI.

### 💻 The Prompt Used
> You are an expert frontend developer, UX designer, game designer, and supply chain consultant.
> 
> Build it so a complete beginner can play it — plain language, context before every decision, 'why does this matter' explanations, and guidance that makes you feel smart rather than lost.
> 
> Build a complete single-file HTML app named 'Operation Lifeline: Supply Chain Crisis Lab'.
> 
> Requirements:
> • Output ONLY one HTML file.
> • React via CDN + Babel JSX.
> • Plain HTML, CSS, and JavaScript only.
> • No Tailwind, npm, backend, APIs, images, or external assets.
> • Must run offline by opening the HTML file.
> • No placeholders or incomplete features.
> 
> Flow:
> 1. Welcome screen with title, subtitle, and 'Start Simulation'.
> 2. Generate a random fictional company (industry, revenue, factories, warehouses, suppliers, inventory days, lead time, countries) displayed as modern cards.
> 3. Generate one random crisis (factory fire, supplier bankruptcy, port strike, cyberattack, flood, raw material shortage, political conflict, shipping delay) with urgency and business impact.
> 4. War Room: Present six response actions. The player chooses three. Simulate consequences by updating Cost, Inventory, Profit, Delivery Speed, and Customer Satisfaction using animated progress bars.
> 5. Negotiation: Branching supplier negotiation with four rounds. Each choice affects Trust, Price, and Lead Time. Display a negotiation score.
> 6. CEO Boardroom: Five multiple-choice leadership questions. Score executive decision-making.
> 7. AI Strategy: Let the player choose two AI investments from Demand Forecasting, Inventory Optimization, Supplier Risk Monitoring, Warehouse Vision, and Procurement Copilot. Show expected business impact.
> 8. Final Dashboard: Display Overall Crisis Score (0-100), Leadership, Negotiation, Resilience, Cost Control, Risk Management, and Customer Satisfaction. Include personalized feedback, biggest mistake, best decision, expert recommendation, and lessons learned.
> 
> Design: Premium dark theme, responsive, rounded cards, progress bars, modern typography. Every playthrough should randomize companies, crises, values, and outcomes.

---

## 📸 Simulation Walkthrough & Screenshots

### 1. The Welcome & Company Generation

<img width="1072" height="910" alt="Welcome Screen   Company Profile" src="https://github.com/user-attachments/assets/649ae723-84e5-4dc3-bbce-a1d9c54510a8" />

### 2. The Crisis Alert

<img width="957" height="877" alt="The Crisis Alert" src="https://github.com/user-attachments/assets/fd68e96b-6233-444a-a3c9-5ec0c4f3164e" />

### 3. War Room

<img width="997" height="730" alt="War Room" src="https://github.com/user-attachments/assets/c04f4d77-2505-4d69-a5af-9c4f7050cd12" />

### 4. Final Executive Dashboard

<img width="700" height="625" alt="Zenith Dashboard-a" src="https://github.com/user-attachments/assets/178dd35d-f0fa-4636-bd5b-7efe01b66e77" />

<img width="712" height="625" alt="Zenith Dashboard-b" src="https://github.com/user-attachments/assets/028ebb0e-04b8-4c2c-8de0-cf0e969dbd91" />

<img width="962" height="810" alt="Apex Dashboard-a" src="https://github.com/user-attachments/assets/864704bf-1fa9-4808-b767-5f268c4b246d" />

<img width="702" height="846" alt="Apex Dashboard-b" src="https://github.com/user-attachments/assets/ef97d97d-523f-4d42-a3c2-369c51b88eb1" />

---

## 🧠 Key Learnings & Insights
* **Speed vs. Cost:** In a supply chain crisis, fast decisions cost money, but slow decisions cost customers. You have to know when to burn capital to save the relationship.
* **Supplier Trust is Currency:** During the negotiation phase, treating the supplier as a partner rather than a vendor yielded much better long-term pricing and lead times.
* **AI is Proactive, Not Reactive:** Choosing to invest in "Inventory Optimization" and "Supplier Risk Monitoring" at the end of the simulation highlighted how AI shifts supply chains from putting out fires to predicting them before they happen.
* **Prompt Engineering Power:** It is incredible that a highly complex, state-driven, aesthetically premium React application can be generated in a single prompt block without complex build environments.

📁 **Generated File:** `operation-lifeline.html` is included in this repository. Just click to open it locally in your browser!
