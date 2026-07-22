# Day 52 — System Design: Turn Yesterday's Plan Into a Technical Blueprint

**AB Talks 60-Day Claude AI Challenge — Capstone Day 2 of 10**
**Project:** MedGuide AI — Agentic Clinical Research & Validation Assistant
**Task:** System Design — turn PRD into complete technical blueprint before writing any code

---

## 🔗 GitHub Commit Links

| Repo | Commit URL |
|------|-----------|
| Project repo (`medguide-ai`) | *(https://github.com/Nidhisingh274/medguide-ai/commit/2a0f9694c40a4dab1d66f2d9553ae9515636df2c)* |

---

## 📁 Files in This Day52 Folder

| File | What it contains | 
|------|-----------------|
| `ARCHITECTURE.md` | Component diagram, data flows, request lifecycle, agent state machine, external services |
| `SCHEMA.md` | Chroma collection + 2 CSV schemas, validated against every PRD user story | 
| `API.md` | Internal Python function contracts (why no REST layer + 4 function signatures) | 
| `UI-WIREFRAMES.md` | User flow, 4 screen states, low-fidelity wireframes |
| `PROJECT-STRUCTURE.md` | Full folder tree with rationale for every folder |

---

## 📸 Screenshots

**GitHub docs/ folder (medguide-ai repo)**
<img width="1502" height="512" alt="medguide-ai repo" src="https://github.com/user-attachments/assets/2088a5c7-7bc4-4619-be18-03417a3d63f0" />

**System Design Poster**
<img width="2760" height="3960" alt="medguide_ai_day2_system_design_poster" src="https://github.com/user-attachments/assets/fc6a9303-6832-4c22-8fe5-7cf1279abf0d" />

---

## 💬 The Prompt Used (Day 2)

```
System Design
Today is Day 2, continuing our chat from Day 1. Read the PRD, Implementation
Blueprint, and Pitch Deck created yesterday. These are now the source of truth
for the project. Do not redesign or rethink the project unless a critical issue
is discovered.

[Full Day 2 System Design prompt attached]
```

**What Claude did before proposing anything:**
Re-read the PRD, Implementation Blueprint, and Pitch Deck from Day 1 — confirmed no
conflicts before designing anything.

---

## 🛠️ What Was Completed Today

### 0. Repository Setup
- Created `medguide-ai` GitHub repo (public, correct description)
- Cloned locally to `Desktop\medguide-ai`
- Configured Git identity
- Created full project folder structure with all placeholder files

### 1. Tech Stack Finalized

| Layer | Choice | Why |
|-------|--------|-----|
| Frontend | Streamlit | Pure Python, fastest path to chat UI, no separate JS build step |
| Backend | None (Streamlit IS the backend) | Monolith = right call for single-user demo |
| Database | Chroma + flat CSVs | No user accounts = no relational DB needed |
| Auth | None | Explicitly out of scope in PRD |
| LLM | Groq (Llama 3.3 70B) | Already confirmed, free tier, fast inference |
| Embeddings | HuggingFace all-MiniLM-L6-v2 | Free, local, no API cost |
| Vector Store | Chroma (embedded) | Free, zero external signup |
| Hosting | Streamlit Community Cloud | Free, deploys from GitHub directly |
| Version Control | Git + GitHub | Already set up today |

**No conflicts with Day 1 PRD.** Every choice matches what was locked on Day 1.

### 2. System Architecture
- Monolithic Streamlit app — no separate backend server
- `app.py` → LangGraph agent → 2 tools (retriever + validator) + Groq API (external)
- `ingestion/build_index.py` runs ONCE at setup, never at runtime
- **Key decision: rejected FastAPI layer** — scope creep with zero portfolio benefit

### 3. Database Schema
- **Chroma collection `medguide_docs`:** chunks with `metadata.source` enabling citations
- **`lab_reference.csv`:** reference ranges (test_name, unit, low, high, notes)
- **`synthetic_labs.csv`:** fake patient data with `SYN-` prefix (no real PHI)
- Referential integrity enforced at application layer inside `validate_labs()`

### 4. API Design
- No REST endpoints (monolithic Streamlit app has no HTTP routes)
- 4 internal Python function contracts documented:
  - `get_retriever(k=4)` — returns configured Chroma retriever
  - `validate_labs(test_values: dict)` — validates lab values vs reference ranges
  - `build_graph()` — compiles LangGraph agent
  - `app.invoke(state)` — runs full agent for one query

### 5. UI & User Flow
- Single page, 4 states: Landing → Loading → Results → Error
- No routing, no login, no multi-page navigation (matches PRD out-of-scope)
- Visible agent step tracker: 🧭 Classify → 🔍 Search → 🧪 Validate → ✍️ Synthesize

### 6. Project Structure
- Each folder maps exactly to one architecture component
- `agent/` = brain, `ingestion/` = setup-only, `data/` = pure content, `docs/` = design artifacts

### 7. Day 3 Readiness Check
- ✅ No scope creep added
- ✅ No architecture changes from Day 1 PRD
- ✅ Day 3 starts immediately: PDF sourcing + ingestion pipeline

---

## 🧠 Key Learnings

1. **Design before code saves more time than it costs.** Every folder, function signature, and data field is decided before a line of code is written — Days 3–7 start with clarity, not confusion.

2. **Saying no is a design decision.** Rejecting the FastAPI backend layer was deliberate — it protected the time budget and kept the architecture right-sized for a 10-day solo build.

3. **Schema validation against user stories catches gaps early.** Checking every Chroma field and CSV column against PRD features confirmed zero missing pieces before implementation begins.

4. **"API design" in a monolith means function contracts.** No REST endpoints doesn't mean no API discipline — internal functions deserve the same rigor: purpose, inputs, outputs, validation, error cases.

5. **Folder structure is architecture made visible.** Each folder maps to exactly one component diagram box — anyone reading the repo understands the system without reading code.

---

*Day 3: First real code — PDF sourcing and ingestion pipeline.*
