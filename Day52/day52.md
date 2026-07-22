# MedGuide AI — Day 2: System Design & Environment Setup

**AB Talks 60-Day Claude AI Challenge · Day 2 of 10**

## What Happened Today

Continuing from Day 1's approved PRD, Implementation Blueprint, and Pitch Deck, today locked in the complete technical design for MedGuide AI — an agentic clinical research & lab-value validation assistant.

## Tech Stack (Finalized, 100% Free)

| Layer | Choice |
|---|---|
| Frontend | Streamlit |
| LLM | Groq API (Llama 3.3 70B) |
| Orchestration | LangChain + LangGraph (StateGraph) |
| Embeddings | HuggingFace `sentence-transformers/all-MiniLM-L6-v2` |
| Vector Store | Chroma (embedded, local persistence) |
| Hosting | Streamlit Community Cloud |
| Version Control | Git + GitHub |

## System Architecture

```
User query
   │
   ▼
Streamlit UI (app.py)
   │
   ▼
LangGraph Agent (agent/graph.py)
   │
   ├──▶ Retriever Tool ──▶ Chroma + HuggingFace embeddings ──┐
   │                                                          │
   ├──▶ Groq API (external LLM reasoning)                    ├──▶ Cited Answer + Anomaly Flags
   │                                                          │
   └──▶ Validator Tool ──▶ lab_reference.csv lookup ──────────┘
```

The agent visibly plans and executes multi-step reasoning: **🔍 Search → 🧪 Validate → ✍️ Synthesize**, shown live in the UI.

## Data Schema

**Chroma collection — `medguide_docs`**
- `id` — auto string
- `page_content` — text chunk
- `metadata.source` — source filename
- `embedding` — vector(384)

**`lab_reference.csv`**
- `test_name` (PK), `unit`, `low`, `high`, `notes`

**`synthetic_labs.csv`**
- `patient_id` (format: `SYN-*`), `test_name` (FK), `value` — no real patient data, ever

## Project Folder Structure

```
medguide-ai/
├── app.py                  # Streamlit entrypoint
├── agent/
│   ├── graph.py             # LangGraph StateGraph
│   ├── tools.py              # retriever + validator tools
│   └── prompts.py            # prompt templates
├── ingestion/
│   └── build_index.py        # PDF → chunks → embeddings → Chroma
├── data/
│   ├── raw_pdfs/              # source guideline PDFs
│   ├── lab_reference.csv
│   └── synthetic_labs.csv
├── chroma_store/               # persisted vector DB (gitignored)
├── docs/                        # design artifacts (this design)
├── tests/
├── requirements.txt
├── .env / .gitignore
└── README.md
```

## GitHub Repository

🔗 **[https://github.com/Nidhisingh274/medguide-ai/commit/2caa0d2ddd5476a73d6aaa2e80bf36b393d7c658]**

## Day 3 Readiness

- ✅ No unnecessary scope has crept in — design matches the locked Day 1 PRD exactly
- ✅ Tech stack, schema, and folder structure are fully decided — no re-litigating needed
- ➡️ Day 3 starts implementation immediately: sourcing PDFs + building the ingestion pipeline
