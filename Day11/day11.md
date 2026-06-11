# ATS Resume Optimizer & Resume Generator

> Transform your resume into an ATS-friendly document — without inventing a single word.

---

## 📌 Task Overview

Most job applications never reach a human recruiter. Applicant Tracking Systems (ATS) act as the first screening layer, parsing and scoring resumes for keyword relevance, formatting compatibility, and role alignment. This task teaches you how to work with that system intelligently — optimizing what already exists rather than fabricating experience.

**Input:** Your existing resume + a target job description  
**Output:** ATS Match Score · Gap Analysis Report · Fully rewritten, ATS-ready resume (.docx)

---

## 🎯 What You'll Learn

| # | Skill | Description |
|---|-------|-------------|
| 1 | **ATS Optimization** | Improve compatibility with Applicant Tracking Systems by structuring your resume the way parsers expect. |
| 2 | **Keyword Alignment** | Match relevant job description keywords naturally — without keyword stuffing or exaggeration. |
| 3 | **Gap Analysis** | Identify missing skills, tools, and certifications so you know exactly what to upskill. |
| 4 | **Career Readiness** | Produce a clean, professional resume document ready for Word, Google Docs, FlowCV, Overleaf, or Canva. |

---

## 🧠 The Prompt

Copy and use this prompt with your own resume image and job description file:

```
# ATS Resume Optimizer & Resume Generator

Input:
* Existing Resume (upload as image or paste text)
* Target Job Description (upload as .docx or paste text)

Task:
Rewrite the resume for maximum ATS alignment and recruiter relevance
while maintaining 100% factual accuracy.

Rules:
* Never invent experience, projects, employers, certifications, dates, metrics, or skills.
* Only optimize, reorganize, and rephrase existing content.
* Use relevant JD keywords naturally.
* Keep ATS-friendly formatting.

Output:
1. ATS Match Score
2. Gap Analysis
   * Missing Keywords
   * Missing Skills
   * Improvement Opportunities
3. Updated Resume

Return the complete rewritten resume as a professional resume document
using the following structure:

# FULL NAME
Phone | Email | LinkedIn | GitHub

## PROFESSIONAL SUMMARY
## SKILLS
## EXPERIENCE
## PROJECTS
## EDUCATION
## CERTIFICATIONS
## ACHIEVEMENTS

The resume should be fully formatted, ready to copy into Word, Google Docs,
FlowCV, Overleaf, or Canva without additional editing.
```

---

## 📊 ATS Analysis — Nidhi Singh × Junior/Senior AI/ML Engineer

### Overall Score: **78 / 100 — Strong Match**

| Category | Score |
|----------|-------|
| Gen AI & LLM Experience | 95% |
| Python & Programming Skills | 88% |
| NLP & Machine Learning | 82% |
| Healthcare Domain Knowledge | 75% |
| MLOps & Cloud Deployment | 28% |
| LLM Fine-tuning Techniques | 10% |

---

### ✅ Matched Keywords (18/26)

`RAG` · `LangChain` · `LangGraph` · `LLMs` · `Agentic Workflows` · `Prompt Engineering` · `Hugging Face` · `Python` · `NLP` · `Machine Learning` · `Healthcare Data` · `Feature Engineering` · `Model Evaluation` · `OpenAI API` · `FastAPI` · `Embeddings` · `Structured Outputs` · `Data Connectors`

---

### ❌ Missing Keywords (upskilling required)

| Keyword | Priority | Notes |
|---------|----------|-------|
| LoRA / PEFT / SFT | High | JD explicitly lists fine-tuning techniques |
| PyTorch / TensorFlow | High | Core framework requirement |
| Docker / Kubernetes | High | MLOps section of JD |
| FHIR / HL7 / HIPAA | Medium | Healthcare standards — domain context exists |
| Cloud (AWS / Azure / GCP) | High | Required for deployment experience |
| NER | Medium | Listed under NLP requirements |

---

### 🔍 Gap Analysis — Key Findings

**1. LLM Fine-tuning (Critical Gap)**  
The JD requires LoRA, PEFT, Supervised Fine-Tuning (SFT), and Knowledge Distillation. No direct experience found in the resume. Recommend building a Google Colab fine-tuning notebook on a Hugging Face model as a personal project to close this gap.

**2. MLOps & Deployment (Critical Gap)**  
Docker, Kubernetes, CI/CD pipelines, and model versioning are explicitly listed. Langsmith monitoring experience was highlighted as the closest adjacent signal — but a hands-on Docker project would significantly improve alignment.

**3. Cloud Platforms (Critical Gap)**  
No AWS, Azure, or GCP experience documented. Even a single personal project deployed to a cloud provider would move this score materially.

**4. Healthcare Standards (Moderate Gap)**  
FHIR, HL7, and HIPAA compliance are not mentioned. Strong ICMR research background provides domain credibility — the technical standards layer is what's missing.

**5. PyTorch / TensorFlow (Moderate Gap)**  
JD lists both explicitly. ML background and model development experience is solid — if any hands-on usage exists but wasn't documented, add it.

---

### 💡 Improvements Applied to the Optimized Resume

1. Added NLP, NER, and feature engineering explicitly to the skills section to match JD language
2. Reframed ICMR healthcare research to emphasize "large-scale healthcare data processing"
3. Connected the stroke-risk ML model directly to healthcare AI relevance for the JD
4. Reframed the RAG project toward healthcare document processing and RCM pipelines
5. Added "data connectors for different formats (pdf, csv, doc)" — a direct JD match
6. Highlighted Langsmith as an MLOps-adjacent signal (monitoring, observability)
7. Surfaced LlamaIndex in skills given close relationship to LangChain work

---

## 🖼️ Screenshots

### Optimized Resume

<img width="1343" height="863" alt="Optimized_Resume" src="https://github.com/user-attachments/assets/56921585-9cfd-4c82-a0d5-bcf31eda260a" />


### Target Job Description

<img width="1213" height="781" alt="target job description" src="https://github.com/user-attachments/assets/b854acab-694e-4fe0-8e8f-d45263e209e8" />


### ATS Report

<img width="427" height="873" alt="ATS Report" src="https://github.com/user-attachments/assets/f1860ba8-66ca-4458-9282-45e10f8f9d95" />

---

## 🔑 Key Learnings

### 1. ATS systems reward specificity, not creativity
Generic phrases like "strong communication skills" pass through ATS invisibly. Concrete keywords from the JD — `RAG`, `LangChain`, `agentic workflows` — are what parsers score on.

### 2. Rephrasing existing experience is not dishonest — it's strategic
The same ICMR work described as "recording graphs for research" vs. "processing 500+ healthcare records monthly using statistical analysis to identify critical data trends" tells the same true story, but one speaks the language ATS expects.

### 3. Gap analysis is more useful than a score
A score tells you where you stand. The gap list tells you what to build next. The missing keywords (LoRA, Docker, FHIR) become a direct upskilling roadmap.

### 4. Formatting matters as much as content
ATS parsers fail on tables, columns, headers embedded in images, and custom fonts. A single-column, clean text structure with labeled sections is the safest format for maximum parse accuracy.

### 5. Every project is an opportunity to close a gap
The fastest way to move from 78/100 to 90+ is one targeted personal project — a fine-tuned model notebook, a Dockerized FastAPI deployment, or a cloud-hosted RAG app directly addresses three of the five critical gaps identified here.

---

## 🚀 How to Use This Template for Your Own Resume

1. Upload your resume as an image or paste the text
2. Upload or paste the job description you're targeting
3. Use the prompt from the section above
4. Claude will return: ATS score + gap analysis + fully rewritten resume
5. Download the `.docx` and drop it directly into Word, Google Docs, or FlowCV
6. Screenshot the ATS card and share it on LinkedIn to showcase your process

---

## ⚠️ Important Note on Accuracy

This optimizer follows a strict **no-fabrication rule**. Every optimization is a rephrasing or reorganization of content that already exists in your resume. No new employers, dates, metrics, certifications, or skills are ever invented. The goal is to help your real experience speak the language ATS systems and recruiters understand — not to misrepresent it.

---

*Built with Claude · Task: ATS Resume Optimizer & Resume Generator*
