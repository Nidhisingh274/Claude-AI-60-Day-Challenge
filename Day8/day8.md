# Day 8: Personal Environmental Health Analyzer 🌍

## 🚀 Project Overview
Today, I built a fully interactive web dashboard using Claude AI to analyze real-time environmental health data for 10 cities in Uttar Pradesh. The application zeroes in on Saharanpur, visualizing how local air (AQI) and water (TDS) quality directly impact daily human health. 

This project perfectly demonstrates how AI can rapidly develop complex, data-driven frontend applications and translate raw numbers into actionable health insights.

---

## 📊 Key Data Insights & Observations (From the Dashboard)
A deeper analysis of the generated dashboard revealed highly specific and actionable data points for Saharanpur and the surrounding UP region:

* **WHO Guidelines Exceeded:** Saharanpur's primary pollutant is PM2.5 at 61 µg/m³, which is over **8x the WHO annual guideline** (5 µg/m³).
* **The "Capital vs. Industrial" Anomaly:** One of the most surprising observations is that Lucknow (the state capital, AQI 150) matches the pollution levels of Saharanpur (an industrial hub, AQI 149), defying expectations for a better-managed capital city.
* **Global Standing:** While it ranks 4th most polluted among the 10 UP cities analyzed, Saharanpur sits among the world's 130 most polluted cities globally (ranked 129th).
* **The North-South UP Divide:** The visual ranking chart exposes a severe 3x pollution gap. Western UP cities like Meerut Division (AQI 176) dominate the High-Risk category, while Southern UP cities like Sonbhadra (AQI 52) and Mirzapur (AQI 59) remain in the "Satisfactory/Good" range.
* **Tangible Health Mapping:** 
    * **Lungs:** The current AQI of 149 is equivalent to smoking ~2.5 cigarettes daily.
    * **Exercise:** Working out in this air reduces VO₂ max by 5–10%, making morning workouts (6–9 AM) highly risky.
    * **Skin & Scalp:** While the Groundwater TDS is acceptable (189 mg/L), its alkaline nature (pH 7.1–7.8) combined with PM2.5 oxidative stress creates a 🔴 **High Risk** for acne, sensitive skin reactions, and scalp inflammation.
* **Seasonal Extremes:** The insights panel predicts that while the current pre-monsoon reading is 149, winter inversions (Oct–Feb) push Saharanpur's historical AQI to a severe 300–450 range.

---

## 🖥️ UI/UX Learnings (Video Demo Analysis)
As demonstrated in my video recording on linkedin, Claude successfully built a highly responsive, app-like experience in a single HTML file:
* **Live DOM & Chart Filtering:** When clicking the risk filters (e.g., "Good Only" or "Moderate+"), the JavaScript dynamically destroys and redrawn all 5 `Chart.js` graphs instantly without a page reload.
* **Dynamic Donut Charts:** Selecting a specific city like "Lucknow" isolating its data, smoothly animating the AQI Distribution Donut chart and adjusting the City Ranking Bar chart on the fly.
* **Interactive Tooltips:** Hovering over the AQI City Comparison chart triggers detailed tooltips that reveal both the exact PM2.5 µg/m³ value and the AQI text category (e.g., "Moderate" or "Poor") simultaneously.

---

## 📝 Prompt Engineering: Taming AI Hallucinations

### ❌ The Problem
**Original Prompt Snippet:** *"automatically search the web for the latest AQI... for the user's current city/location."*
Because LLMs don't have access to live GPS data, asking it to "auto-detect" my location forced the AI to guess. It confidently hallucinated a completely random city, rendering the data useless.

### ✅ The Solution
I modified the prompt to implement a strict verification gate:
> "📍 DATA & LOCATION RULES:
> 1. Location Confirmation (CRITICAL): Before generating the dashboard... explicitly state the city... and ask them to confirm. 
> 2. Manual Entry: Tell the user: 'If this location is incorrect, please type your correct city...' Do not proceed with generating the artifact until the exact location is confirmed."

**Why it worked:** By shifting from an *assumptive* instruction to a *conditional* constraint, I prevented the AI from rushing to a flawed output. It ensured that the generated dataset was strictly tied to Saharanpur, UP.

---

## 📸 Dashboard Visuals

*(Refer to the html document in the repository to see the live filter animations and hover states!)*

### 1. Main Header & Health Metrics
<img width="1897" height="763" alt="Main Header   Health Metrics" src="https://github.com/user-attachments/assets/0de17d1f-0f8c-4fdd-a3d3-566dbeef1ec8" />

### 2. Interactive Pollution Visualizations
<img width="960" height="867" alt="Interactive Pollution Visualizations" src="https://github.com/user-attachments/assets/54e19ad7-6e32-446c-ac72-804abca10459" />

### 3. Personal Environmental Report Card
<img width="1902" height="577" alt="Personal Environmental Report Card" src="https://github.com/user-attachments/assets/88b4a572-ada7-4cc1-9b5f-a660aa13443c" />

---

## 🔗 Try It Out
* **HTML File:** `index.html` (Available in this repository. Download and open it in any browser to test the interactive filters).
