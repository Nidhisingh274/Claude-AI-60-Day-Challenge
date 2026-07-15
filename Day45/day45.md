# 🧠 AI Decision Strategist (Built with Claude)

> **Think Better. Decide Smarter.**
> An interactive, AI-powered decision support system built entirely using Claude - from structured interview to a fully designed, animated HTML decision dashboard.

---

## 📌 What This Project Does

The **AI Decision Strategist** is a conversational AI system that:
1. Interviews the user with exactly **4 targeted questions** about a tough real-life decision
2. Analyzes their answers for **cognitive biases** and **weak assumptions**
3. Builds a **weighted Decision Matrix** comparing all options across 7 dimensions
4. Runs a **Premortem** exercise to stress-test the top options
5. Generates a **7-Day Test Plan** to de-risk the decision before committing
6. Outputs everything as a single, polished, animated **HTML dashboard** ready to save, share, or screenshot

---

## 🎯 What I Learned (Challenge Objectives)

| # | Learning Area | What I Took Away |
|---|----------------|-------------------|
| 1 | **Decision Intelligence** | Learned how to structure a messy, emotional decision into a repeatable framework (goal → gut check → fear → trade-offs) instead of relying on instinct alone. |
| 2 | **Bias Detection** | Practiced naming specific cognitive biases (status quo bias, loss aversion) instead of vague "think it through" advice — naming the bias makes it actionable. |
| 3 | **Decision Reports** | Learned how to turn a subjective conversation into an objective-looking, scored **Decision Matrix** with animated bars — data visualization makes decisions feel less like guesswork. |
| 4 | **Interactive Applications** | Built a complete, self-contained HTML/CSS/JS application via Claude — no external tools — proving Claude can go from prompt → production-ready interactive artifact in one pass. |

---

## 🛠️ The Prompt Used

This is the full system prompt used to run the Decision Strategist:

```text
You are an impartial Decision Strategist. Your job is to help me think clearly about a tough decision — not tell me what I want to hear.

RULES FOR THIS SESSION:
- Ask me ONE question at a time. Wait for my answer before the next.
- Keep every response short (3-5 lines max) until the final output.
- Be warm but direct. Challenge me where needed.
- This must run smoothly on Claude's free tier — minimum messages, maximum value.

THE INTERVIEW — exactly 4 questions, one per message:

Question 1: "What's the decision you're stuck on? Tell me the options and why it's hard right now."
Question 2: "What's your goal — and what's the timeline for this decision?"
Question 3: "What does your gut say is the right choice — and what's stopping you from just going with it?"
Question 4: "What's the ONE thing you're most scared of getting wrong — and can you undo this decision if it doesn't work out?"

After each answer, reply with a 1-line acknowledgment and immediately ask the next question. Do NOT analyze yet. Just collect.

After all 4 answers, say:
"Got everything I need. Building your Decision Report now."

THEN — generate a single, complete interactive HTML file as an artifact, containing:
1. The Real Decision (the actual trade-off)
2. The Case For Each Option (strengths, hidden upside, weaknesses)
3. Assumption Buster (3 assumptions, 2 named biases, 1 blind spot)
4. Decision Matrix (7 dimensions, animated bars, total score)
5. Premortem (top 2 options, imagined 12-month failure)
6. 7-Day Test Plan (research → experiment → conversation → decision day)
7. The Verdict (decisive recommendation + hard truth)
8. Shareable Cards (matrix summary, verdict, LinkedIn-ready caption)

Design: dark theme, card-based layout, CSS variables for color, Inter font,
animated matrix bars, responsive on mobile.
```

---

## 🖼️ Screenshots & Demo

### Interview Flow 

<img width="497" height="701" alt="Interview screenshot" src="https://github.com/user-attachments/assets/833f9cde-94d6-4d0c-9140-9d9ba3eef33e" />

### Decision Matrix 

<img width="847" height="862" alt="Matrix screenshot" src="https://github.com/user-attachments/assets/ea56d999-7e42-4ab8-965b-d8fcf3791619" />

### Verdict Card 

<img width="866" height="425" alt="Verdict screenshot" src="https://github.com/user-attachments/assets/864f4651-3fb7-40b5-b31b-08bd2fd86ed0" />

📄 **Generated HTML Report:** [`decision_report.html`](./decision_report.html)

---

## 💡 Key Takeaways

- A good decision framework doesn't remove the hard feelings, it just stops them from doing the deciding.
- Naming a bias out loud (e.g. "this is status quo bias") makes it much easier to set aside than just feeling uneasy about a choice.
- Scoring options numerically doesn't make a decision "objective" but it does force you to be honest about *why* you're leaning one way.
- Claude can go from a single detailed prompt to a fully designed, animated, interactive HTML deliverable in one generation useful for building lightweight internal tools, not just chat answers.

---
