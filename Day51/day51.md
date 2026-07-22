# Day 1 — Product Discovery & Sprint Planning
### AB Talks 60-Day Claude AI Challenge (10-Day Capstone)

**Participant:** Nidhi Singh
**Task:** Kick off the 10-day capstone — go from no idea to a fully scoped, deployable v1.0 plan using Claude as a structured product-discovery partner.

---

## 🎯 What This Task Was About

- **Guided Discovery** : Let Claude interview me one question at a time to surface the strongest project I could realistically ship, instead of jumping to the most ambitious idea.
- **Scope Discipline** : Explicitly define what v1.0 includes, what's deliberately excluded, and what "done" looks like on Day 10.
- **Professional PRD** : Produce a complete Product Requirements Document as the single source of truth.
- **Self-Contained Daily Blueprint** : Generate a Days 2–10 plan detailed enough that a fresh AI conversation each day can continue building without re-planning.

---

## 📝 The Kickoff Prompt I Used

```
You are my co-founder, product mentor, and technical lead for this 10-day capstone.
Your goal is to help me go from no idea to a deployed v1.0 product. Help me discover
the right problem, shape the best solution, and guide me through the entire journey
over the next 10 days (including today).

I'm participating in the AB Talks 60-Day Claude AI Challenge. This capstone follows a
real software development lifecycle:
Requirements → Design → Setup → Implementation → Testing → Deployment → Maintenance

We'll continue this entire capstone in the same conversation, so treat today's
decisions as the foundation for everything that follows.

Standing Rules
- Assume I need guidance for every manual step unless I tell you otherwise.
- Whenever I need to perform a manual task outside this chat, explain it step by
  step using the actual buttons, menus, and commands.
- Wait for my confirmation and a screenshot before continuing.
- Never assume I've completed a step.
- Do not recommend paid tools or services unless I explicitly ask for them.

Today's Goal
- Interview me one question at a time. Keep every question simple, and briefly
  explain why you're asking it.
- If I don't already have a project idea, interview me to discover one — my
  interests, goals, skills, strengths, and constraints — then suggest, compare,
  refine, combine, and challenge ideas until we've chosen the strongest project I
  can realistically build in 10 days.
- Don't optimize for the most ambitious project. Optimize for the most impressive
  project that can be fully completed within the available time.
- Once selected, define: what v1.0 includes, what's intentionally left out, and
  what success on Day 10 looks like.
- Summarize the finalized project in one paragraph and ask for approval before
  generating any documents.

Deliverables (only after approval)
1. Product Requirements Document (PRD)
2. Implementation Blueprint (Days 2–10) — daily objective, what I'll learn,
   features, step-by-step plan, files/folders, integrations, testing, debugging
   tips, checklist, expected screenshots, handoff notes for the next day
3. Project Pitch Deck — Problem, Target Users, Solution, Key Features,
   Technical Approach, Future Scope, Vision

Important: Do not choose the tech stack or write code today.
```

---

## 💬 The Interview — Questions & My Answers

| # | Question (why Claude asked it) | My Answer |
|---|---|---|
| 1 | Current coding skill level? *(calibrates technical ambition)* | Advanced |
| 2 | Primary goal for this capstone? *(shapes what "success" optimizes for)* | Portfolio piece to show employers/clients |
| 3 | Strongest technical skills? *(steers ideas toward my real strengths)* | Agentic/GenAI (LangChain, LangGraph, MCP, OpenAI/Groq/Claude APIs), RAG & vector systems (FAISS, Chroma, Pinecone), Cloud/DevOps (AWS Bedrock), ML/Data Science (Python, scikit-learn, Hugging Face), Healthcare AI & bioinformatics domain expertise |
| 4 | Already have an idea, or brainstorm from scratch? | Brainstorm from scratch |
| 5 | Focused hours/day available for 10 days? *(biggest scope lever)* | 1–2 hours/day |
| 6 | Specific data/domain already in mind? | Pushed back — asked to raise the ambition instead of only picking a number |
| 7 | Realistic, sustainable daily time budget? | landed on **3–4 hrs/day** (~30–40 hrs total) |
| 8 | Which domain excites you most (Healthcare AI / Bioinformatics / Supply Chain / cross-cutting)? | Claude recommended **Healthcare AI**, backed by my real ICMR background |
| 9 | Which angle within Healthcare AI (research assistant / diagnostic tool / data validation agent)? | Let Claude pick the most impressive combination — it merged **research Q&A + data validation** into one product |
| 10 | Target role for this portfolio piece? | AI/ML Engineer (general) **and** Applied AI/GenAI Engineer at a healthcare-tech company |
| 11 | What documents should the agent ingest for the demo? | a **mix**: public clinical guidelines/research papers (RAG Q&A) + synthetic lab reports (validation feature) |
| 12 | Should the agent show visible multi-step reasoning in the UI? | chose **visible step-by-step reasoning** (bigger "wow" factor, plays to LangGraph strength) |
| 13 | How should someone experience the demo (live app vs. video)? | **Live deployed web app**, using only free-tier hosting |
| 14 | GitHub account / Git installed? | Yes, but cluade will keep guiding
| 15 | LLM API key already available? | Yes — **Groq API key** |
| 16 | Vector DB preference? | Free and best — Claude chose **Chroma** (embedded, zero setup, free) |
| 17 | Deployment platform preference? | Let Claude decide — chose **Streamlit Community Cloud** |
| 18 | OK using a free local Hugging Face embedding model instead of paid OpenAI embeddings? | Yes |

---

## ✅ Approved Project Summary

> **MedGuide AI — Agentic Clinical Research & Validation Assistant.** A live, deployed agentic AI assistant that helps clinicians and researchers get fast, trustworthy answers from medical literature while flagging abnormal lab values against reference ranges, built to mirror my real ICMR experience. A visible, multi-step LangGraph agent (search guidelines/papers → check lab values → synthesize a cited answer) ingests public clinical guidelines/research PDFs into a Chroma vector store (via free Hugging Face embeddings), answers natural-language medical questions with source citations, and separately validates synthetic lab report values against known reference ranges. Powered by Groq's free-tier LLM API, orchestrated with LangChain/LangGraph, and deployed free on Streamlit Community Cloud — a single-purpose, portfolio-grade demo of agentic RAG applied to a real healthcare workflow.

**I confirmed with "yes"** — Claude then generated all three deliverables.

---

## 📦 Deliverables Generated

| Deliverable | Contents |
|---|---|
| **Product Requirements Document (PRD)** | Overview, problem statement, target users, goals & success metrics, in/out-of-scope v1.0, key features, locked technical approach, risks & mitigations, assumptions/constraints, glossary |
| **Implementation Blueprint (Days 2–10)** | 31 pages — project-specific, day-by-day objectives, what I'll learn, features to build, step-by-step implementation, files/folders, integrations, testing tasks, debugging tips, end-of-day checklists, expected screenshots, and handoff notes so a fresh AI conversation each day can continue without re-planning |
| **Pitch Deck** | 8 slides — Problem, Target Users, Solution, Key Features, Technical Approach, Future Scope, Vision |

---

## 🔑 Key Learnings

- **Structured interviewing beats jumping straight to a tech stack.** Answering 18 focused questions — one at a time, each with a stated reason - surfaced a much sharper project than I would have picked on day one.
- **Scope discipline is the real product.** Locking a realistic time budget (3–4 hrs/day) *before* choosing features kept the project small enough to actually finish, instead of ambitious enough to stall.
- **Your own experience is your strongest differentiator.** Tying the project directly to my real ICMR work turned a generic "RAG chatbot" into a credible, story-backed portfolio piece.
- **A single source of truth prevents drift.** Because the Implementation Blueprint contains full daily context (objectives, code direction, files, checklists, handoff notes), each remaining day can start in a *fresh* conversation without me having to re-explain the whole project.
