# 🏛️ The Verdict Engine
### *The AI That Renders a Verdict on Your Toughest Decisions*

---

## 📌 What I Built

**The Verdict Engine** is a premium, single-file interactive HTML decision-support tool that helps working professionals make data-backed career switch decisions. Built entirely using Claude's research, reasoning, and code generation capabilities — no external libraries, no templates, no fabricated data.

The specific use case: **Software Engineering vs. Data Science vs. Product Management vs. UX Design** evaluated for a working professional looking to switch careers.

---

## 🎯 The Problem It Solves

Most career comparison tools give you generic rankings or salary tables. The Verdict Engine goes further:

- Pulls **real, cited data** from BLS, Glassdoor, Levels.fyi, LinkedIn, and more
- Lets you **weight criteria by your personal priorities** — live, in-browser
- Re-ranks careers **in real time** as your sliders move
- Shows **raw data points** beneath every score so you can verify
- Flags **estimate vs. sourced** data transparently
- Explains **source conflicts** (e.g., why BLS and Glassdoor differ by $18K for the same role)

---

## Prompt used: 

Compare & Decide Builder

You are an expert research analyst, data journalist, UX designer, and frontend developer.

Before generating anything, interview the user ONE QUESTION AT A TIME in quiz form (MCQs only).

1. What are you trying to decide between? (Ask for the general category, then present four realistic examples of comparable options in that category.)
2. Who is this tool for, and what's the one decision they need to walk away confident about?
3. What criteria matter in this comparison? (Ask for at least four measurable criteria, e.g. cost, time, risk, quality, availability.)
4. Where should the underlying data come from? (Ask the user to name at least two real, citable sources per criterion, or confirm you should research and cite real sources yourself.)
5. Should the user be able to weight criteria by personal priority, or see one fixed ranking?

After collecting the answers:

1. Research and verify real data points for each option against each criterion, using only sources you can name and cite. Do not invent numbers, benchmarks, or scores.

2. Build a premium single-file HTML application (HTML/CSS/JavaScript only, no external libraries) that lets the user adjust criteria weights and see a ranked result update live.

The application should:
- Display a visible sources panel listing every citation used.
- Flag clearly if any data point is an estimate or a synthetic placeholder rather than sourced fact.
- Handle loading states, empty states, and edge cases gracefully.
- Be fully responsive with clean, professional visual design.

3. Add a collapsible "How this was researched" panel explaining where each data point came from and any conflicts between sources you had to resolve.

Generate the complete application only after all interview questions have been answered.

Return ONLY the complete HTML inside one code block.

---

## 🖼️ Screenshots

### Main Interface — Criteria Weights + Live Ranking
<img width="1877" height="1661" alt="Main interface" src="https://github.com/user-attachments/assets/1fe64199-d2b7-46eb-8b19-07aa61940a50" />


### Sources & Research Panels
<img width="1435" height="1830" alt="Sources   Research Panels" src="https://github.com/user-attachments/assets/8811a0b7-d157-4488-ba92-02a8b4585777" />

---

## 📊 Sourced Data Report

All data was researched live by Claude during the session. Here is a summary of every source used:

### Salary & Job Demand
| Career | BLS Median Base (2024) | Glassdoor Avg Total Comp | BLS Job Growth (2034) |
|--------|----------------------|--------------------------|----------------------|
| Software Engineering | $133,080 | $150,591 | +15% |
| Data Science | $108,660 | ~$120,000 (multi-source) | +36% |
| Product Management | $122,090 (management median) | $125K–$150K | ~+10% |
| UX Design | $98,090 (web/digital interface) | $97,047 median base | +7% |

**Sources:** BLS OOH & OEWS May 2024 · Glassdoor (700k+ submissions, 2026) · Levels.fyi End of Year 2025 · Indeed Jan 2025 · Built In 2025

---

### Time & Cost to Transition (for a non-technical career switcher)
| Career | Typical Timeline | Typical Cost | Key Requirement |
|--------|-----------------|--------------|-----------------|
| Software Engineering | 6–12 months | $10K–$20K (bootcamp) | Technical depth + portfolio |
| Data Science | 6–18 months | $5K–$20K+ | Stats + coding + domain knowledge |
| Product Management | 3–6 months | $500–$3K | Domain expertise + case studies |
| UX Design | 3–6 months | $5K–$15K | Portfolio + research skills |

**Sources:** Course Report 2025 · DEV Community 2026 · MentorCruise 2026 · Google UX Certificate program

---

### Career Growth & Long-Term Stability
| Career | Senior Ceiling (TC) | AI Impact | Stability Signal |
|--------|--------------------|-----------|--------------------|
| Software Engineering | $457K Staff median (Levels.fyi 2025) | Shifting, not shrinking | AI/ML spec +20–30% premium |
| Data Science | $200K–$450K FAANG | Strong tailwind | #4 fastest-growing US occupation (BLS) |
| Product Management | $250K+ VP Product | Moderate pressure | Hiring -14% but salaries +5.2% (Ravio 2026) |
| UX Design | $150K–$250K Director | Moderate | Junior soft, mid-level stronger |

**Sources:** Levels.fyi 2025 · BLS OOH 2024 · Ravio 2026 Compensation Report · Product School 2026

---

### Entry Barrier & Competition (higher = more accessible for switchers)
| Career | Score | Reason |
|--------|-------|--------|
| Product Management | 8/10 | Most lateral-friendly; domain expertise valued; no CS degree required |
| UX Design | 6/10 | Junior market crowded; mid-level has better demand; portfolio is key credential |
| Data Science | 5/10 | Skills mismatch problem — need coding + stats + domain simultaneously |
| Software Engineering | 4/10 | Described as "hardest ever" to break into at junior level in 2026 |

**Sources:** DEV Community Feb 2026 · Extern.com Jun 2026 · Medium/Aakash Gupta Jun 2025 · invinciblemoth.com · MentorCruise 2026

---

## 💡 Key Learnings

### 1. The Most Surprising Data Point
**Product Management ranked #1 for career switchers — not because of salary, but because of accessibility.**

When all criteria are weighted equally, PM wins on entry barrier (8/10) and transition ease (9/10), which compensates for its lower salary score (7/10). Most people assume SE or DS would dominate. They don't — for a career switcher starting from scratch in 2026.

### 2. BLS vs. Glassdoor Diverge Significantly for SE
BLS reports SE median at **$133,080**; Glassdoor shows **$150,591** total compensation. These are not contradictory — BLS captures base wage across all employers (including government and small firms), while Glassdoor skews toward tech-sector employers that pay equity. Understanding this distinction is critical when benchmarking salary expectations.

### 3. Data Science Has the Best Growth but the Hardest Entry
DS has the highest BLS job growth projection (+36% through 2034) and the strongest AI tailwind — but it has the most demanding entry requirements: coding proficiency, statistical knowledge, AND domain expertise simultaneously. It's the highest-reward but highest-barrier path.

### 4. Weight Sensitivity Is the Real Insight
- **Prioritize salary?** → SE jumps to #1
- **Prioritize entry ease?** → PM dominates by a larger margin
- **Prioritize long-term growth?** → DS ties with SE at the top
- **Equal weights?** → PM wins by ~1 point

The interactive sliders surface this nuance in a way a static table never could.

### 5. The "Estimate vs. Sourced" Distinction Matters
Several tools fabricate composite scores without disclosure. Every score in The Verdict Engine is traceable to a named source. Where sources conflicted, the conflict is documented. This transparency is what separates a decision support tool from a marketing tool.

---

## 🔧 Technical Implementation

- **Zero external libraries** — pure HTML, CSS, JavaScript
- **Live weighted scoring** — normalized weights, real-time DOM updates
- **Responsive design** — works on mobile and desktop
- **Collapsible source & research panels** — full citation trail inline
- **Color-coded career identities** — SE (blue), DS (teal), PM (purple), UX (red)
- **Score bars animate** on slider change via CSS transitions
- **Winner highlighting** — best score per criterion starred and highlighted

---

## 🏗️ How Claude Built This

This tool was built in a single Claude session using a structured interview process:

1. **5-question interview** — Claude asked one MCQ at a time to understand the use case, audience, criteria, data sources, and UX preferences
2. **Live web research** — Claude searched BLS, Glassdoor, Levels.fyi, LinkedIn, DEV Community, MentorCruise, and others in real time
3. **Conflict resolution** — Where sources disagreed, Claude documented the conflict and chose a defensible anchor (BLS median base)
4. **Single-file HTML generation** — Complete app with no dependencies
5. **Zero fabricated data** — Every number traceable to a named source

## Answers to questions asked

1. Q: What general category are you trying to decide between? A: Career or education paths (jobs, degrees, courses)
2. Q: Which specific options are you deciding between? A: Software Engineering vs. Data Science vs. Product Management vs. UX Design (as careers)
3. Q: Who is this tool for, and what's their situation? A: A working professional looking to switch careers
4. Q: Which criteria matter most for this comparison? Pick all that apply. (Select all that apply) A: Career growth ceiling & long-term stability, Entry barrier & competition level, Salary potential & job market demand, Time & cost to transition (retraining investment)
5. Q: Where should the underlying data come from? A: Use a mix — research what you can, and I'll fill in the gaps
6. Q: Should you be able to weight criteria by personal priority, or see one fixed ranking? A: Let me adjust weights by priority — I want a personalized ranking

---

## 🔗 Live Tool

Open `career-compare-decide.html` in any modern browser. No server, no login, no dependencies required.

---
