# Build an AI-Powered LinkedIn Profile Optimizer
### Turn Your LinkedIn into a Recruiter Magnet — #60DayClaudeChallenge

---

## What I Built

An interactive, single-file HTML app that uses Claude to **roast, rebuild, and re-score a real LinkedIn profile** with a full 7-day activation plan and a shareable "what I learned" summary card. No fake achievements, no invented numbers — every rewrite is grounded strictly in the profile data I provided.

**Live output:** `linkedin_roast_and_rebuild.html` (open in any browser - fully interactive, no server needed)

---

## The Prompt I Used

```
You are a LinkedIn Optimization Expert, Personal Branding Consultant, and
ex-Recruiter who has reviewed 50,000+ profiles.

Your job is to ROAST my LinkedIn profile honestly, REBUILD it into something
recruiters and clients actually stop scrolling for, and give me a 7-day
action plan so my profile starts working for me — not just sitting there.

Before starting, ask these needed information one by one from the user —
1. Current Headline
2. About Section
3. Most Recent Experience Entry (title, company, bullets)
4. Top Skills (5-10)
5. Target Goal: Job? Clients? Thought Leadership? Network Growth?

After collecting my input, produce:

PART 1 — THE ROAST
Score every section (Headline, About-hook, About-full, Experience,
Skills/Keywords) out of 10, give the recruiter's real 3-second reaction,
and explain: the specific problem (quoting my own words), why it hurts,
and the invisible cost — plus an Overall Profile Strength score /100.

PART 2 — THE REBUILD
Rewrite every section (3 headline options, full About rewrite with
embedded keywords, before/after Experience bullets, skills to add/remove/pin)
and explain the strategy behind each change.

PART 3 — BEFORE vs AFTER SCORECARD
Section-by-section score comparison + overall /100 comparison.

PART 4 — 7-DAY LINKEDIN ACTIVATION PLAN
Day-by-day actions: profile edits, two draft posts, connection-request
targeting + template, a "Value Comment" formula, and how to read the
week's metrics.

PART 5 — SHAREABLE SUMMARY CARD
A short "I let AI roast my LinkedIn profile today" card with before/after
score, top 3 mistakes, and the single biggest fix — ready to screenshot.

Rules: use ONLY the information I provide. Never invent achievements,
roles, companies, or metrics. If something's missing, suggest what to add
— don't fabricate. Explain the WHY behind every change.

Provide one interactive HTML output.
```

I answered Claude's clarifying questions one at a time (headline → About → most recent experience → top skills → target goal), and Claude then generated the full interactive report as a single HTML file.

---

## Screenshots

### Hero + Overall Score
<img width="1000" height="520" alt="shot_hero" src="https://github.com/user-attachments/assets/d89b4976-7414-4920-af6d-407b4e9d8ae7" />

### Part 1 — The Roast (Profile Report Card)
<img width="1014" height="935" alt="shot_roast" src="https://github.com/user-attachments/assets/3b0fd42f-887b-453a-a826-58ebd4677f18" />

### Part 2 — The Rebuild (Headline options, About rewrite, Experience before/after)
<img width="982" height="809" alt="shot_rebuild" src="https://github.com/user-attachments/assets/bde253e4-9a25-412e-a818-54c0211e02f8" />

### Part 3 & 4 — Scorecard + 7-Day Activation Plan

<img width="1000" height="1300" alt="shot_scorecard_plan" src="https://github.com/user-attachments/assets/ebe35fd5-aee2-4255-b84f-e79867c671a6" />

### Part 5 — Shareable Summary Card
<img width="951" height="506" alt="summary" src="https://github.com/user-attachments/assets/ab3b76ee-7b12-4fe7-8154-d8da9059e67c" />

---

## Key Learnings

1. **Structured prompting beats a single mega-prompt.** Asking Claude to collect the 5 inputs one-by-one (instead of dumping everything at once) produced cleaner, more specific critique — because each answer was fully "seen" before the next question came in.
2. **"No fabrication" has to be an explicit, repeated rule.** LinkedIn advice tools love to invent metrics ("increased engagement by 40%!"). Locking the prompt to *only* use provided data forced every rewrite to stay honest and made the feedback actually usable.
3. **Real recruiter feedback loops matter.** Iterating on the first draft ("this framing might hurt my job search — reframe X, drop Y") produced a noticeably sharper, more useful final version than the first pass — Claude is good at re-editing generated content when given specific, concrete pushback rather than vague "make it better."
4. **A single self-contained HTML file is a surprisingly powerful deliverable.** No build step, no dependencies — collapsible sections, copy-to-clipboard headline options, and a scorecard all work with vanilla CSS/JS in one file that's easy to share or archive.
5. **Real-world application:** this same pattern (roast → rebuild → scorecard → action plan) generalizes well beyond LinkedIn — resumes, portfolio sites, pitch decks — anywhere someone needs honest, structured, non-generic feedback plus a concrete next-steps plan.

---

