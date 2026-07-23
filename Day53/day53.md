# Day 53 — Project Setup & Foundation: From System Design to Running Hello World

**AB Talks 60-Day Claude AI Challenge — Capstone Day 3 of 10**
**Project:** MedGuide AI — Agentic Clinical Research & Validation Assistant
**Task:** Project Setup & Foundation — translate system design into a real, running project

---

## 📌 GitHub Commit URL

> **Commit URL:** *(https://github.com/Nidhisingh274/medguide-ai/commit/4c3bbf24d8e37e7b8e6c9788a61a30056e56c236)*

---

## 📸 Screenshots

### **Hello World Running**

<img width="1495" height="806" alt="hello world" src="https://github.com/user-attachments/assets/f0b724ea-462b-4d3c-847c-786cce8b4641" />

### **Ingestion Pipeline Output**

<img width="1297" height="381" alt="ingestion pipeline output" src="https://github.com/user-attachments/assets/783bb150-858b-455e-9b21-1137320d3c37" />

### GitHub Repo After Push**

<img width="1137" height="595" alt="github repo after push" src="https://github.com/user-attachments/assets/181f2530-66ea-48d1-8462-709e227a951d" />

---

## 💬 The Prompt Used (Day 3)

```
Day 3: Project Setup & Foundation

Today is Day 3, continuing the same capstone. Before doing anything, read the following documents from the previous days:

* Product Requirements Document (PRD)
* 10-Day Blueprint
* System Design Documents
* Architecture
* Database Design
* API Design
* Project Structure

These documents are now the source of truth. Do not redesign the project unless a critical issue is discovered. If any document is unavailable, ask me to upload it.

Standing Rules

* Assume I need guidance for every manual step unless I tell you otherwise.
* Whenever I need to perform a task outside this chat, explain it using the exact buttons, menus, commands, and terminal instructions.
* Wait for my confirmation and a screenshot before continuing.
* Never assume I've completed a manual step.
* Explain every technical concept in beginner-friendly language before using it.

Today's Goal

Today's objective is to build the project's foundation. By the end of today I should have:

* Development environment fully configured
* Project running locally
* Complete folder structure
* Git repository initialized and connected
* Dependencies installed
* Configuration files completed
* Database connected (if required)
* Authentication scaffolded (if required)
* Basic navigation/routing working
* A working "Hello World" version of the application running successfully

Do not begin implementing the core features yet unless the Day 2 blueprint specifically schedules a small foundation feature. Follow the Day 3 section of the 10-Day Blueprint while adapting to any issues that arise.

Complete the Following

1. Environment Setup
Guide me through installing and configuring everything required for this project. Examples include:

* Runtime
* IDE extensions
* Package managers
* Framework CLI
* SDKs
* Environment variables

Explain why each tool is needed.

2. Project Initialization
Walk me through:

* Creating the project
* Installing dependencies
* Initializing configuration
* Running the project
* Verifying everything works

3. Repository Setup
If not already completed:

* Connect local project to GitHub
* Create appropriate branches
* Explain the branching strategy
* Make the initial commit

4. Build the Foundation
Implement only the foundational pieces required before feature development. Examples:

* Routing
* Layout
* Navigation
* Authentication scaffold
* Database connection
* API client setup
* Shared components
* State management
* Configuration

Explain every major file that is created.

5. Verify the Project
Confirm that:

* The application builds successfully.
* There are no errors.
* The project structure matches the System Design.
* Everything is ready for feature development tomorrow.

If problems occur, help me debug them before moving on.

Deliverables

Generate downloadable versions of:

* SETUP.md (installation and setup guide)
* PROJECT-STRUCTURE.md (updated if necessary)
* ENVIRONMENT.md (all environment variables, tools, and configuration)
* DAY3-SUMMARY.md

Update the 10-Day Blueprint if today's implementation required any changes.

End of Day

Help me:

* Commit today's work using a meaningful commit message.
* Push it to GitHub.
* Update the project log.
* Write a LinkedIn post summarizing today's progress.

Finally, summarize:

* ✅ What was completed today
* 🚧 What's ready to build tomorrow
* 🎯 What tomorrow's objective will be

Tomorrow should begin implementing the first major user-facing feature, with no additional setup or planning required.
```

---

## 🛠️ What Was Completed Today (Day 3)

### 1. Environment Setup
**Installed 2 new Python packages:**
- `pypdf` — extracts text from PDF files (used in ingestion pipeline)
- `langchain-text-splitters` — chunks extracted text into ~1000-char pieces

**Added to `requirements.txt`:**
```
pypdf
langchain-text-splitters
```

**Full dependencies list (total: 13 packages):**
- `streamlit` — UI framework
- `langchain`, `langgraph` — agent orchestration
- `langchain-groq` — connects to Groq LLM
- `langchain-community`, `langchain-huggingface` — embeddings + Chroma
- `chromadb` — vector store
- `sentence-transformers` — local embedding model
- `pypdf` — PDF text extraction
- `langchain-text-splitters` — text chunking
- `python-dotenv` — env variable loading
- `pandas` — CSV handling
- `groq` — Groq SDK

### 2. Project Initialization
**Hello World Streamlit App:**
- File: `app.py` (now contains working Streamlit foundation)
- Runs at `http://localhost:8501`
- Shows title, welcome message, and caption
- Verified: no errors, displays correctly

**Why this matters:** Real running app milestone before feature development starts.

### 3. Clinical Topic & PDF Sourcing
**Topic chosen: Type 2 Diabetes management**
- Pairs naturally with lab tests (glucose, HbA1c, cholesterol) for Day 5's validation
- 3 peer-reviewed PDFs sourced from CDC, BMC, and Frontiers

**PDFs sourced:**
| PDF | Characters | Status |
|-----|-----------|--------|
| bmc_diabetes_clinical_practice.pdf | 44,326 | ✅ Well above 500-char minimum |
| cdc_diabetes_referral_strategies.pdf | 109,427 | ✅ Strong |
| frontiers_diabetes_cardiovascular_care.pdf | 101,929 | ✅ Strong |
| **Total** | **~256,000** | ✅ More content than 5 shorter docs |

### 4. Ingestion & Chunking Pipeline
**File created:** `ingestion/build_index.py`

**What it does:**
1. Loads all PDFs from `data/raw_pdfs/`
2. Extracts raw text from each PDF (using `pypdf`)
3. Splits text into overlapping chunks (~1000 characters each, 150-char overlap)
4. Returns list of 302 chunks, each with `source`, `chunk_id`, and `text`

**Why chunking matters:** PDFs are too big to feed to an AI at once. Smaller chunks (1000 chars) work much better for similarity search later.

**Output verified:**
- ✅ 302 total chunks across 3 documents
- ✅ All chunk text is clean English (no garbled encoding)
- ✅ Character counts all well above minimum threshold
- ✅ Exactly matches Day 1 architecture diagram (Ingestion-time flow, Section 3.1)

### 5. Documentation Generated
Four new setup/reference documents created:

| File | Purpose |
|------|---------|
| **SETUP.md** | Step-by-step installation guide — venv, pip install, env vars, running the app |
| **ENVIRONMENT.md** | Reference for all environment variables, tools, Python packages, config files |
| **PROJECT-STRUCTURE.md** | Updated to reflect actual state: Hello World app, ingestion pipeline, 3 PDFs in place |
| **DAY3-SUMMARY.md** | Quick recap of what was done, what's ready for Day 4, and tomorrow's objective |

### 6. Git & Repository
**Commit made:**
```bash
git add .
git commit -m "Day 3: foundation complete - Hello World app, PDF ingestion pipeline (302 chunks), setup docs"
git push
```

**Status:** ✅ Pushed to GitHub, commit hash obtained

---

## 🚧 What's Ready to Build Tomorrow (Day 4)

- ✅ `chunks` list (302 entries, each with source, chunk_id, text) is production-ready
- ✅ HuggingFace embedding model (`all-MiniLM-L6-v2`) will be downloaded on first Day 4 run
- ✅ Chroma vector store will be built from chunks on Day 4
- ✅ Day 4's `agent/tools.py` `get_retriever()` function will consume the Chroma store

**No rework needed** — everything today feeds directly into Day 4's embedding step.

---

## 🎯 Tomorrow's Objective (Day 4)

**Embed all 302 chunks using free local HuggingFace model and store in Chroma vector store.**

Day 4 will:
1. Extend `ingestion/build_index.py` to add embedding step
2. Create `chroma_store/` directory with embedded vectors
3. Test retrieval with a sample similarity query
4. Confirm the RAG half of the product works

**No UI changes.** No agent yet. Just data pipeline → embeddings → vector store.

---

## 📂 File Placement Guide

### **In `medguide-ai` project repo** (already committed):
```
medguide-ai/
├── app.py                    # ✅ Hello World Streamlit app
├── ingestion/
│   └── build_index.py        # ✅ PDF loading + chunking pipeline
├── data/
│   └── raw_pdfs/
│       ├── bmc_diabetes_clinical_practice.pdf
│       ├── cdc_diabetes_referral_strategies.pdf
│       └── frontiers_diabetes_cardiovascular_care.pdf
└── docs/
    ├── SETUP.md              # ✅ NEW today
    ├── ENVIRONMENT.md        # ✅ NEW today
    ├── PROJECT-STRUCTURE.md  # ✅ UPDATED today
    └── DAY3-SUMMARY.md       # ✅ NEW today
```

---

## 🧠 Key Learnings

1. **Environment setup first, always.** Installing the right packages before writing any code prevents "missing library" errors later. `requirements.txt` is your safety net.

2. **Chunking is the foundation of RAG.** The 302 chunks created today are what tomorrow's embeddings will work with. Bigger PDFs = more chunks = more thorough retrieval, but also more compute time on Day 4.

3. **PDF quality matters.** Text-based PDFs (like CDC guidelines) extract cleanly; scanned image-PDFs don't. We verified all 3 PDFs extracted clean text before moving on.

4. **A running "Hello World" validates the entire toolchain.** By getting Streamlit running today, we confirmed Python, venv, all dependencies, and the dev environment work — before building features on top of it.

5. **Monolithic architecture simplifies Day 3.** No database migration, no auth setup, no API scaffolding — just Python packages, a Streamlit page, and a data pipeline. Everything runs locally.

6. **Blueprint alignment = confidence.** Every piece built today (Hello World, ingestion pipeline, folder structure) matches exactly what was designed in Days 1–2. No surprises, no rework.

---

## 📝 Project Log Entry (for docs/PROJECT-LOG.md)

```
Day 3 — Foundation Complete. 
Installed remaining dependencies (pypdf, langchain-text-splitters). 
Built and verified Hello World Streamlit app running at localhost:8501. 
Locked clinical topic: Type 2 Diabetes. 
Sourced 3 clinical PDFs (~256,000 characters combined). 
Built and tested ingestion/chunking pipeline — 302 chunks produced, all verified clean. 
Updated SETUP.md, ENVIRONMENT.md, PROJECT-STRUCTURE.md; added DAY3-SUMMARY.md. 
No architectural changes from Day 1/2 design. 
Day 4 (embeddings + Chroma vector store) ready to begin immediately.
```

---

*Day 4: Embed 302 chunks using HuggingFace + Chroma. RAG pipeline complete. 7 days left to shipping.*
