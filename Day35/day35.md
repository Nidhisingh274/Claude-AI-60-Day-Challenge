# Day 35 — 🧩 Prompt Puzzle: Master AI Prompting Through Play

## 📌 Challenge Overview

Today's task was to use Claude to generate a fully interactive, offline game called **Prompt Puzzle** which is an educational tool that teaches AI prompt engineering through gamified challenges. No tutorials. No memorization. Just play.

<img width="796" height="677" alt="interface" src="https://github.com/user-attachments/assets/60d4c1a5-9a23-4854-8bcb-9e99c8e20adf" />

---

## 🎮 What I Built

An application (`prompt-puzzle.html`) that runs entirely in the browser, no internet required after generation.

### Features
- **Domain & Difficulty Selection** — onboarding questions to personalize the experience
- **7 Randomized Scenarios** per session, drawn from a scenario pool
- **3 Challenge Types:**
  - 🟣 **Build the Prompt** — drag-and-drop prompt blocks (ROLE, CONTEXT, TASK, FORMAT, CONSTRAINTS) into the correct structure
  - 🟢 **Clean the Prompt** — identify and remove hedging/filler language from weak prompts
  - 🟡 **Choose the Best Prompt** — select between Weak, Optimized, and Over-Engineered versions
- **Live Scoring** — Accuracy, Time Bonus, Wrong Placements, Hints Used, Optimization Bonus
- **Prompt Performance Report** — Score, Rating, Rank, Prompt DNA visualization, Personalized Feedback, Next Milestone, Final Optimized Prompt
- **Replay** with fresh randomized scenarios

<img width="712" height="886" alt="performance report" src="https://github.com/user-attachments/assets/19d16dc4-4986-4159-ae96-cc2bff4109d9" />

---

## 🧠 Key Learnings

### 1. Role + Context + Task + Format = Expert Output
The single biggest insight from playing Prompt Puzzle: structuring a prompt with an explicit **role**, **context**, **specific task**, and **output format** dramatically improves AI response quality. Vague prompts get vague answers. Structured prompts get structured, expert-level answers.

### 2. Hedging Language Kills Prompt Authority
Words like *"maybe"*, *"please"*, *"try to"*, *"if possible"*, *"somehow"*, *"I guess"* don't make you polite to the AI — they make your prompt weaker. The Clean the Prompt challenge made this viscerally obvious. Commands, not requests.

### 3. Over-Engineering is as Bad as Under-Specifying
There's a Goldilocks zone. A prompt that asks for "50 years of expertise across 12 frameworks with formal LaTeX proofs" produces noise, not signal. Specificity and conciseness are not opposites — the optimized prompt is always the one that specifies *what matters* without padding.

### 4. Framework Anchoring = Instant Depth
Naming a methodology (STRIDE, OWASP, Big-O, SOLID) anchors the AI to a structured knowledge domain. Instead of "check for security issues," say "apply STRIDE methodology." One word — orders of magnitude better output.

### 5. Prompt DNA Thinking
Breaking prompts into components (Role, Context, Task, Format, Constraints) and tracking which dimensions you habitually neglect is a powerful self-audit tool. My weakest dimension: **Context** — I tend to jump straight to the task without grounding the AI in the scenario.

### 6. Meta-Prompting
Prompting an AI to *write a prompt* (system prompt generation, few-shot example construction) requires you to specify the target model's persona, hard constraints, refusal behaviors, and output format. Prompts all the way down.
