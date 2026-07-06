# Day 36 - Cognitive Pattern Explorer 🧠✨

An interactive app built with Claude that turns self-reflection into a game-like exploration instead of a static quiz.

---

## 🎯 What I Built

**Cognitive Pattern Explorer** is a psychology-inspired self-reflection tool that helps you notice your natural thinking tendencies through short scenarios,
drag-and-drop activities, and a personalized "Reflection Journal" at the end.

It maps responses across five thinking tendencies:
- Analytical Thinker
- Emotional Intuitive
- Overthinking Loop Style
- Action-First Decision Maker
- Balanced Reflective Thinker

### The Flow
1. **Start Screen** — choose Calm Mode or Stress Mode (changes the pacing, color palette, and ambient animation speed).
2. **Chapter 1 – Discover Your Thinking Style** — five everyday scenarios, answered by picking the response closest to you.
3. **Chapter 2 – Choose Your Priorities** — a draggable ranking list (mouse drag, touch drag, or arrow-key keyboard control).
4. **Chapter 3 – Map Your Thinking** — a draggable timeline where you place cards in the order you'd naturally reach for them.
5. **Final Reflection Journal** — a glowing "constellation" visualization plus a percentage breakdown of your tendencies, with a personalized reflective write-up.

📄 **Generated app:** [`cognitive-pattern-explorer.html`](./cognitive-pattern-explorer.html)

---

## 🖼️ Screenshots — Reflection Journal & Thinking Profile (Calm Mode)

**Start Screen**
<img width="831" height="632" alt="start-screen" src="https://github.com/user-attachments/assets/cafd4eb8-3fa7-4147-9bff-1bfae482d0de" />

**Chapter 1 — Discover Your Thinking Style**
<img width="970" height="847" alt="1" src="https://github.com/user-attachments/assets/ab40c824-2215-4972-9ac5-616e7edcdca9" />
<img width="916" height="842" alt="2" src="https://github.com/user-attachments/assets/cd599808-c91f-40dc-afd4-29e5459c35e4" />
<img width="931" height="821" alt="3" src="https://github.com/user-attachments/assets/5fb1bbc4-1de1-4fcd-bebe-2bc01994921e" />
<img width="917" height="805" alt="4" src="https://github.com/user-attachments/assets/06af2ce2-2baa-42db-a084-622614e965a8" />
<img width="892" height="797" alt="5" src="https://github.com/user-attachments/assets/1fcc85d2-7b2e-4fc9-bebf-85ef05eb527a" />


**Final Reflection Journal — Thinking Profile & Percentage Breakdown**
<img width="767" height="855" alt="reflection-journal" src="https://github.com/user-attachments/assets/7e966dfc-bea9-43b8-a240-43870c53e2dc" />

In Calm Mode, my result came out as **Analytical Thinker (32%)** primary, with **Action-First Decision Maker (25%)** as a strong secondary tendency, and the rest fairly evenly spread across Emotional Intuitive, 
Balanced Reflective, and Overthinking Loop Style.

---

## 💡 Key Learnings

- **Prompt structure drives app quality.** Giving Claude a clear chapter-by-chapter flow, named tendencies, and explicit "never diagnose" language produced a coherent, non-clinical experience on the first generation.
- **Interactive ≠ complicated.** Scenario-based multiple choice, a sortable list, and a drag-to-timeline activity were enough to make the reflection feel exploratory rather than like a form.
- **Reusable components matter.** Building one shared drag-and-drop primitive (used by both the ranking list and the timeline) kept the single HTML file clean and consistent, and made the touch/keyboard fallbacks easier to reason about.
- **Small design choices change the feel.** Calm vs. Stress mode — just a palette and animation-speed swap — noticeably changed how the same content felt to go through.
- **Accessibility can't be an afterthought.** Adding keyboard alternatives (arrow keys, number keys) and `prefers-reduced-motion` support from the start was far easier than retrofitting it later.
- **Real-world application:** this kind of pattern — scenario-based reflection + lightweight scoring + a personalized summary could extend well beyond this demo, e.g. onboarding flows, team-culture workshops, or learning-style explainers, always keeping the same non-diagnostic, educational framing.

