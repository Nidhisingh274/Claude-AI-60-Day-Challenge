# Day 13 — AI-Powered Job Search Assistant with Claude + Indeed

> **Challenge:** #60DayClaudeChallenge | Day 13  
> **Task:** Build an AI Job Search Assistant using Claude Connectors + Indeed MCP

---

## 🎯 What I Built

An end-to-end AI-powered job search pipeline using **Claude** (claude.ai) with the **Indeed MCP Connector**, turning my professional profile into a fully personalized job discovery, match scoring, and career analysis system — all in one conversation.

---

## 🛠️ Tools & Stack Used

| Tool | Purpose |
|------|---------|
| Claude (Sonnet) | AI reasoning, analysis, job matching |
| Indeed MCP Connector | Live job search via Claude Connectors |
| LangChain | Core framework (my skills) |
| LangGraph | Agentic workflow (my skills) |
| FAISS + RAG | Retrieval pipelines (my skills) |
| Groq LLM + OpenAI | LLM providers (my skills) |

---

## 👩‍💻 Prompt used

```
PROMPT 1: Professional Profile

Describe your professional background, including:

Current role
Years of experience
Key skills and technologies
Industry/domain expertise
Current company type
Current location
Notable achievements, certifications, or accomplishments

PROMPT 2: Job Search Criteria

Specify your target job requirements, including:

Desired job titles
Preferred company types
Preferred locations (Remote/Hybrid/Onsite)
Salary expectations
Industries or companies to exclude
Job posting recency requirements
Any additional preferences or constraints

PROMPT 3: Job Discovery & Analysis

Using my professional profile and job search criteria:

Search for matching job opportunities using the available job connector(s)
Prioritize the highest-fit roles
Exclude jobs that do not meet my requirements
Return the top opportunities in a table containing:

Company
Role
Location
Posted Date
Direct Application Link
Match Score
Why It Fits My Profile
CTC

Also provide:

Most commonly required skills across the jobs
Skill gap analysis
Market demand insights
Recommendations to improve my chances of getting interviews
Overall fit assessment for my target roles and compensation goals.
```

---

## 🖼️ Screenshots

### Professional Profile

<img width="647" height="847" alt="Professional profile" src="https://github.com/user-attachments/assets/28548bc5-4249-4ef9-bb01-a0f34ec15beb" />

### Matching job opportunities using Indeed job connector

<img width="698" height="508" alt="Matching job opportunities using Indeed job connector" src="https://github.com/user-attachments/assets/a84df18f-f11d-4b1a-8a90-45b1cb53177f" />

### Top Jobs, Skill analysis, Market insights and Recommendations

<img width="707" height="353" alt="Top jobs, skill analysis, market insights and recommendations" src="https://github.com/user-attachments/assets/a8184960-334f-4b1a-8d2b-0b164b397e26" />

---

## 📊 Market Demand Insights

### 🔥 Agentic AI is the hottest title in India right now
> LinkedIn India data: job postings requiring LangChain, CrewAI, or "AI agent" skills grew **300%+** between Jan 2025 and Mar 2026. NASSCOM projects 50,000+ agentic AI roles by 2027.

### 💰 Salary Reality
- 12–16 LPA: Immediately achievable with current profile
- 18–22 LPA: Unlocked with 1 cloud GenAI credential + 1-2 months more exposure
- Roles above ₹20 LPA typically list 3–5 yrs experience — Gorec (₹20–22 LPA) is a strong benchmark

### 🌐 Remote Dominates
4 of 6 top-matching roles are fully remote — strong advantage for candidates outside metro cities.

### 🏥 Healthcare AI = Rare Differentiator
ICMR / COVID-19 national health data background is rare in the Gen AI engineer pool. Health-tech companies (Practo, Eka Care, Niramai) pay a premium for this combination.

---

## 🎯 Recommendations to Improve Interview Chances

1. **Lead with project portfolio** — Create a GitHub Pages / Notion portfolio with 5–6 best Gen AI projects including demo GIFs or live links
2. **Add one cloud GenAI credential** — AWS Certified ML Specialty or Azure AI Engineer Associate in the next 4 weeks
3. **Quantify resume bullets** — Replace "Used LangChain and FAISS" with "Built RAG pipeline using FAISS + LangChain reducing response latency by X%"
4. **Set daily job alerts** — "LangGraph agentic AI remote" + "RAG LLM engineer India" on Naukri + LinkedIn
5. **Target Healthcare AI startups specifically** — ICMR experience is a genuine differentiator
6. **Apply this weekend** — Talent Vision Services (Noida, 96% match) and EC-Council (Remote, 93% match) are top priority

---

## 🏆 Overall Fit Assessment

| Dimension | Score |
|-----------|-------|
| Skill-to-market alignment | ⭐⭐⭐⭐⭐ |
| Role availability | ⭐⭐⭐⭐½ |
| Salary target feasibility | ⭐⭐⭐⭐ |
| Remote opportunities | ⭐⭐⭐⭐⭐ |
| **Overall Market Fit** | **8 / 10** |

> Core strengths — LangChain, LangGraph, RAG, Agentic AI, 30+ projects — are excellent fit for the current Gen AI wave. Primary friction: 2 vs 3–5 yr experience gap, and absence of cloud credentials. Immediate ₹12–16 LPA range is realistic; ₹18–22 LPA is achievable within 3 months of adding cloud exposure.

---

## 💡 Key Learnings

1. **Claude Connectors are genuinely powerful** — Claude pulled live job data from Indeed, scored each role against my actual skill set, and generated contextual recommendations in a single conversation.

2. **Match scoring is only useful if the criteria are precise** — The more detailed Prompt 1 and Prompt 2 were, the more accurate and useful the Prompt 3 output became. Garbage in, garbage out — but quality in, insights out.

3. **The skill gap analysis was the most valuable output** — I knew what I had; I didn't know exactly what was missing relative to the market. Cloud platforms (AWS/Azure) appearing in 4/6 top roles was a clear, actionable signal.

4. **Agentic AI demand is real, not hype** — The number of live roles explicitly asking for LangGraph, multi-agent systems, and autonomous workflows confirmed what I'd been reading — this is the moment for people with this stack.

5. **Domain experience is undersold on most AI resumes** — The ICMR / healthcare angle is a genuine differentiator. Healthcare AI is a specific niche with less competition and higher domain premiums.

6. **AI-assisted job search is the new baseline** — Spending 10 minutes with Claude + Indeed gave more structured, personalized, and actionable output than hours of manual job board scrolling.

