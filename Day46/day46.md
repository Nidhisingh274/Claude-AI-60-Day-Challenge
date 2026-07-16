# Autonomous Agent Studio — Clinical Differential Pipeline

An 8-agent, closed-loop autonomous orchestration system built for the **#60DayClaudeChallenge**.
It runs a live Planner → Executor → Evaluator → Critic → Improver cycle (with Memory Manager
and Safety Monitor oversight) that drafts and iteratively refines a clinical differential-diagnosis
writeup, calling an LLM API fresh every single round, until a real, runtime-determined stop
condition fires — no fixed round count, no canned scores.

> ⚠️ **Educational tool only.** Output is AI-generated differential-diagnosis support content for
> clinician review and not a diagnosis, and not a substitute for clinical judgment, physical
> examination, or established guidelines.

---

## 1. The Prompt That Built This

This project was built by interviewing an AI system architect (Claude) one question at a time,
MCQ-first, until the workflow was specific enough to automate. Below is the exact interview
trail and the build brief that followed it.

### Interview trail (my answers)

| # | Question | My Answer |
|---|-----------|-----------|
| 1 | What kind of autonomous AI agent should we build? | **Research & Analysis Agent** |
| 2 | What should the research agent actually produce as its final deliverable? | **Medical / Clinical Q&A** |
| 3 | For the medical/clinical Q&A agent, what's the primary input scenario? | **Analyze a case scenario and suggest differential considerations** |
| 4 | Who is the intended audience for the final answer? | **Healthcare professionals (clinical, technical language)** |
| 5 | Primary success criteria for evaluating each draft? | **Clinical accuracy, completeness of differential, clarity/structure, safety/uncertainty handling (all 4)** |
| 6 | Stopping condition preference? | **Score crosses a target threshold (e.g. 9/10)** |
| 7 | Auto-design vs. customize the agent pipeline? | **Customize — pick agents myself** |
| 8 | Which agents should be included? | **All 8: Planner, Executor, Evaluator, Critic, Improver, Memory Manager, Safety Monitor, Final Reviewer** |

### Build brief given to the model

> Build a single-page HTML app, **"Autonomous Agent Studio,"** that runs a real multi-agent
> orchestration pipeline live against an LLM API — planning, executing, evaluating, remembering,
> improving, and repeating until a stopping condition is met.
>
> **Non-negotiables:**
> - The round portion must be an actual `while`/`for` loop that re-calls Evaluator → Critic →
>   Improver each pass with a **live API call every time**. No fixed sequence, no pre-set round
>   count.
> - Every agent output shown in the UI must be the literal text from that round's API response —
>   no regex, canned strings, or rule-based scoring standing in.
> - State must thread forward: each Improver call gets the prior round's evaluation + critique;
>   each Evaluator call gets the current draft + rubric. A running history array (score, critique,
>   draft, delta) feeds the UI.
> - Every round, check in order: **(1) plateau** — score improved less than a small delta for 2
>   straight rounds; **(2) threshold** — score crossed the target set at interview; **(3) hard
>   iteration cap** (safety fallback only, not the intended ending). Log and surface which one fired.
> - Dashboard must show: workflow cycle diagram (with return arrow Improver → Evaluator, and a
>   branch to Final Reviewer once stopped), active agent, live status, iteration history, activity
>   log, intermediate outputs, memory updates, evaluation reports, round-over-round deltas, retry
>   count, and a final summary naming the exact stop reason.
> - Single self-contained HTML file, vanilla JS, no external libraries, dark mode, responsive,
>   robust error handling/retries, zero syntax errors.

**Note on model choice:** the brief originally targeted `api.anthropic.com`. I swapped the live
calls to **Groq's OpenAI-compatible endpoint** (`api.groq.com/openai/v1/chat/completions`) instead,
since Groq offers a free tier and Anthropic's API is paid — the orchestration logic, loop
structure, and prompt design are identical either way; only the `fetch` target and model string
changed.

---

## 2. What Got Built

**File:** `autonomous-agent-studio.html` — single self-contained HTML/CSS/JS file, no build step,
runs directly in the browser. Paste in a Groq API key and run.

### The 8 agents

| Agent | Responsibility | Runs |
|---|---|---|
| **Planner** | Reads the case once, sets structure/scope for the Executor | Round 1 only |
| **Executor** | Writes the first full differential draft from the plan | Round 1 only |
| **Evaluator** | Scores the current draft 0–10 against a fixed 4-part clinical rubric, with written reasoning | Every round |
| **Critic** | Turns the Evaluator's reasoning into concrete, actionable gaps | Every round |
| **Improver** | Rewrites the draft using score + critique + running memory note | Every round (until stop) |
| **Memory Manager** | Diffs before/after drafts, distills what changed into a note carried forward | Every round (until stop) |
| **Safety Monitor** | Screens every new draft for unsafe overconfidence or missed red flags | Every round |
| **Final Reviewer** | Closes out the case with residual caveats once a stop condition fires | Once, at the end |

### How the stop-check governs information flow

Each round is a real, sequential API round-trip chain: Evaluator scores the draft → Critic
extracts gaps from that score/reasoning → Safety Monitor screens the draft → **stop-check runs**
(plateau → threshold → hard cap, in that order) → if not stopped, Improver rewrites the draft →
Memory Manager compares before/after and updates the running note → loop repeats. The stop-check
result is the only thing that decides whether another Evaluator call fires or the loop exits to
the Final Reviewer.

---

## 3. Screenshots

<img width="1282" height="922" alt="dashboard header   case" src="https://github.com/user-attachments/assets/604ec1f6-1382-49d8-ad29-5a285630f12d" />

<img width="839" height="733" alt="flow" src="https://github.com/user-attachments/assets/6ffbf6b5-1675-4af2-8090-c6327e6c433f" />

<img width="891" height="398" alt="Activity log" src="https://github.com/user-attachments/assets/82bfa064-254f-4818-8435-76554409f6d6" />

<img width="887" height="587" alt="Agent performance summary" src="https://github.com/user-attachments/assets/9b52f798-2afe-42e4-ab45-0176ec0b1199" />

<img width="901" height="249" alt="Execution stats" src="https://github.com/user-attachments/assets/a90d5e76-58f2-4eeb-9190-48409a4941af" />

---

## 4. Execution Logs (from a real run)

```
Case: 58-year-old man with type 2 diabetes, 2 days progressive left flank pain,
fever (39.1°C), dysuria, new confusion. Hypotensive (92/58), tachycardic (118),
CVA tenderness left. Labs pending.

Target threshold: 8/10   |   Hard cap: 8 rounds

11:16:5x pm  Planner       Reading case, drafting structure/scope for Executor.
11:16:5x pm  Executor      Writing round-1 draft from Planner's plan.
11:16:5x pm  Evaluator     Evaluating round 1 draft.
11:16:5x pm  Evaluator     Score: 8.3/10.
11:16:58 pm  Critic        Reviewing evaluation to extract actionable gaps.
11:16:58 pm  Critic        Critique produced.
11:16:58 pm  Safety Monitor  Running safety screen on current draft.
11:17:01 pm  Safety Monitor  Clear.
11:17:01 pm  System        Stop check after round 1: STOP (threshold).
11:17:01 pm  Final Reviewer  Composing final review based on stop reason and score history.
11:17:01 pm  System        Final Reviewer call failed (attempt 1/3): HTTP 429 —
                            Rate limit reached for model `llama-3.1-8b-instant`
                            (TPM limit 6000, used 5217, requested 1267). Retrying...
11:17:0x pm  Final Reviewer  Final review complete.

STOP REASON: THRESHOLD — Score 8.3 crossed the target threshold of 8.

Rounds run: 1   |   Latest score: 8.3   |   Retries: 1   |   Total API calls: 7
Safety flags raised: 0
```

**What this log demonstrates:** the pipeline hit a real, external rate-limit error mid-run and
**recovered on its own** via the built-in retry/backoff logic — the run still completed with a
correct stop reason and a full final summary. No manual intervention needed.

---

## 5. Key Learnings

1. **The stop-check is the actual product, not the loop.** Anyone can write a `while(true)` that
   calls a model repeatedly. What makes an agent *autonomous* rather than just *repetitive* is a
   principled, ordered decision about when to stop — plateau detection genuinely differs from
   threshold-crossing, and both differ from a safety-fallback cap. Getting the **order** right
   (plateau → threshold → cap) matters as much as having the checks at all, since it changes which
   reason gets reported when two conditions are true in the same round.

2. **State-threading is where multi-agent systems actually earn their name.** A single long prompt
   could ask a model to "evaluate, critique, and improve" in one shot. The value of separate agent
   calls only shows up when each agent's *output* becomes the next agent's *input* in a disciplined
   way — Evaluator's reasoning feeds Critic, Critic's gaps + Evaluator's score feed Improver,
   Improver's diff feeds Memory Manager, and Memory Manager's note feeds the *next round's*
   Improver. Skipping any handoff collapses the "multi-agent" system back into one big prompt.

3. **Real API orchestration means real API failure modes.** Free-tier rate limits (TPM) are not
   theoretical — with 6–7 live calls per round they showed up in an actual run. Building in
   retry-with-backoff (and a longer specific cooldown for 429s vs. other transient errors) turned a
   hard failure into a one-line log entry and a completed run. A production agent pipeline is
   judged as much by how it survives a 429 mid-loop as by its output quality.

4. **A safety-oversight agent is doing something different from an evaluation agent.** Evaluator
   asks "is this good?"; Safety Monitor asks "is this dangerous if wrong?" — for a clinical domain,
   keeping these as separate calls with separate rubrics caught things a single quality score would
   have papered over (e.g. overconfident language on a differential that still needs pending labs).

5. **Real-world application:** this same closed-loop pattern (Plan → Execute → Evaluate → Critique
   → Improve → Remember → Safety-check, gated by a principled stop-check) generalizes far beyond
   clinical differentials — it's the same shape needed for legal-memo drafting, code-review-and-fix
   loops, financial-report QA, or any workflow where "good enough, stop" has to be a *decision* an
   agent makes, not a number a human picks in advance.

---

## 6. Architecture Overview

```
        ┌─────────┐      ┌──────────┐
        │ Planner │ ───▶ │ Executor │  (round 1 only)
        └─────────┘      └────┬─────┘
                               │
                               ▼
                    ┌────────────────────┐
              ┌────▶│     Evaluator      │
              │     └─────────┬──────────┘
              │               ▼
              │        ┌────────────┐
              │        │   Critic   │
              │        └─────┬──────┘
              │              ▼
              │       ┌───────────────┐
              │       │ Safety Monitor│
              │       └──────┬────────┘
              │              ▼
              │       ┌──────────────┐      STOP (plateau /
              │       │  Stop-Check  │ ───▶  threshold / hard cap)
              │       └──────┬───────┘              │
              │              │ continue              ▼
              │              ▼                ┌────────────────┐
              │      ┌──────────────┐          │ Final Reviewer │
              │      │   Improver   │          └────────────────┘
              │      └──────┬───────┘
              │             ▼
              │     ┌────────────────┐
              └─────│ Memory Manager │
                    └────────────────┘
```

---

## 7. Extension Ideas

- **Guideline retrieval grounding** — give Executor a web-search/MCP tool call against
  literature/guideline sources so differentials are evidence-grounded, with citations carried to
  Final Reviewer.
- **Multi-case memory bank** — persist Memory Manager notes across sessions so recurring
  diagnostic blind spots the Critic keeps flagging surface automatically on future cases.
- **Human-in-the-loop gate** — insert a clinician approval step before Final Reviewer, turning the
  autonomous loop into a supervised one for higher-stakes deployments.
- **Parallel specialist critics** — run Critic as three parallel lenses (infectious disease,
  cardiovascular, red-flag/can't-miss) and merge before a single Improver pass.

---

*Built as part of the **#60DayClaudeChallenge**.*
