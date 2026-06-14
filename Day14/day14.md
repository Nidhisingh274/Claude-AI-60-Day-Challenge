# Day 14 – AI Job Red Flag Detector 🚩
## 60-Day Claude Challenge

---

## 🎯 What I Built

An **AI-powered Job Red Flag Detector** using Claude that analyzes job descriptions and company information to generate a complete risk analysis report before I waste time applying.

---

## 🛠️ Prompt Used

```
You are an AI Red Flag Detector for job seekers.

Analyze the Job Description and Company Information.

Identify:

1. Unrealistic Requirements
- Excessive experience for the role
- Too many skills/responsibilities
- Contradictory expectations

2. Toxic Workplace Signals
- Burnout indicators
- 'Wear many hats'
- 'Fast-paced', 'rockstar', 'hustle culture'
- Poor work-life balance signals

3. Remote Job Authenticity
- Hidden office requirements
- Relocation expectations
- Misleading remote claims

4. Hiring Risks
- Missing salary information
- Vague responsibilities
- Excessive qualifications
- Suspicious hiring practices

5. Company Risks
- Reputation concerns
- Stability concerns
- Growth or layoff indicators

Output:

## Overall Risk Score (0-100)

### Top Red Flags
- List with severity (1-10)

### Positive Signals
- List positives

### Risk Breakdown
| Category | Risk Level |
|-----------|-----------|
| Requirements | |
| Culture | |
| Remote | |
| Hiring | |
| Company | |

### Final Verdict
 Apply /  Apply with Caution /  Avoid

### 5 Smart Interview Questions
Generate questions that help validate the identified risks.

Job Description: [PASTE JD HERE]
Company Information: [PASTE COMPANY INFO HERE]
```

---

## 📊 Generated Risk Analysis Report

### Overall Risk Score: **70 / 100** ⚠️ HIGH RISK

---

### 🚩 Top Red Flags

| # | Red Flag | Severity |
|---|----------|----------|
| 1 | **Catastrophic salary discrepancy** — JD says ₹1.2L–₹2.4L/year but company's other public posts show ₹6L–₹12L/month | 9/10 |
| 2 | **Severe skill overload** — PyTorch, TensorFlow, spaCy, HuggingFace, LangChain, Neo4j, SPARQL, Docker, MLflow, cloud all at once = 3-4 specialist roles bundled into one | 8/10 |
| 3 | **Micro company with big ambitions** — Annual revenue ₹81.7L (~$98K), paid-up capital only ₹1L; can't realistically fund senior AI talent | 8/10 |
| 4 | **Zero employee reviews anywhere** — No Glassdoor, AmbitionBox, or LinkedIn culture signals for a company incorporated in 2020 | 7/10 |
| 5 | **"Cross-functional, hands-on" coded language** — Classic signal for "you'll do everything alone with no team or support" | 6/10 |
| 6 | **Domain mismatch** — Pharmacovigilance CRO firm asking for cutting-edge LLM research; no evidence of AI infrastructure or culture | 5/10 |
| 7 | **Relocation requirement, no support mentioned** — Must relocate to Chennai before starting; no relocation package offered | 3/10 |

---

### ✅ Positive Signals

- Salary range is disclosed (unusual for many listings)
- ISO 9001:2015 certified — some process maturity
- Clear, specific tech stack mentioned (NLP, Knowledge Graphs, FastAPI, LLMs)
- Niche domain (pharmacovigilance + NLP) — meaningful real-world application

---

### 📈 Risk Breakdown

| Category | Risk Level |
|-----------|------------|
| Requirements | 🔴 High |
| Culture | 🟡 Medium |
| Remote / Location | 🟡 Medium |
| Hiring | 🔴 High |
| Company | 🔴 High |

---

### 🏁 Final Verdict

> ⚠️ **Apply with Extreme Caution**
> Only proceed if you receive written clarity on actual salary AND can verify company financial stability during the interview process.

---

### ❓ 5 Smart Interview Questions Generated

1. The posted salary is ₹1.2L–₹2.4L per year, but your other public listings mention ₹6L–₹12L per month for similar roles. Can you clarify the actual compensation package?

2. How many data scientists or ML engineers are currently on the team, and who would I collaborate with day-to-day on the NLP pipeline?

3. What annotated datasets, compute resources (GPUs/cloud budget), and existing infrastructure does the company have for LLM fine-tuning and knowledge graph work?

4. Can you share an example of an NLP or AI project delivered in the last 12 months, and what was the business outcome?

5. What does the roadmap look like for this role over 6–12 months — is there a plan to grow the data science team, or will I be the primary AI practitioner?

---

## 📸 Screenshots

<img width="728" height="817" alt="Red flag analysis report-1" src="https://github.com/user-attachments/assets/712f1a06-3245-474c-9ef3-b7a893eb9918" />

<img width="722" height="483" alt="Red flag analysis report-2" src="https://github.com/user-attachments/assets/39fd61dc-7345-46fd-bcc7-8fd90cfb76d4" />

<img width="682" height="317" alt="Red flag analysis report-3" src="https://github.com/user-attachments/assets/ffe48316-f299-490d-80d4-b9584962b288" />

---

## 💡 Key Learnings

1. **A job application is a two-way street.** Claude helped me flip the script — instead of just hoping a company picks me, I'm now evaluating them first.

2. **Salary discrepancies are a critical red flag.** The gap between ₹2.4L/year (JD) vs ₹12L/month (other posts) is massive and might never surface without this kind of analysis.

3. **Small companies with outsized skill requirements = wear many hats, no team.** The JD asked for 10+ specialist skills — a sign you'll be doing the work of an entire department alone.

4. **Zero reviews = giant red flag.** A company with 5 years in business and zero Glassdoor/AmbitionBox reviews isn't a hidden gem — it's a warning sign.

5. **Prompt engineering for analysis tasks works best with structured output.** Breaking the prompt into numbered categories + a scoring rubric made Claude's output immediately actionable.

---

## 🔗 Tools Used

- **Claude** (claude.ai) — AI Red Flag Detector
- **Effort Level:** Low (as instructed)
- **Input:** Job Description (text) + Company Information (text)

---

*Day 14 of #60DayClaudeChallenge | #BuildInPublic*
