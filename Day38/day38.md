# Day 38 — Typing Speed Studio 🚀
### Build a Premium Commercial Typing Platform

---

## 🎯 What I Built

**Typing Speed Studio** is a commercial-grade typing practice platform generated end-to-end from a single detailed prompt, refined through a short interview with Claude before code generation.

The app includes:

- **7 typing modes** — Time (15/30/60/120s), Word Count (25/50/100/250), Quote, Programming (JavaScript, Python, HTML, CSS, Java, C++, SQL, TypeScript), Custom Text, Adaptive (auto-adjusts difficulty from rolling accuracy), and Zen (untimed, distraction-free).
- **Focus Mode** — blurs every line except the one currently being typed.
- **6 switchable content topics** — General English, Academic, Business, Medical, Legal, Creative Writing — each generated procedurally from category-specific word banks and sentence templates, so no two sessions repeat the same passage.
- **Live stats bar** — WPM, Raw WPM, CPM, Accuracy, Elapsed Time, Mistake Count, Current Streak, and Remaining Words/Time, all updating in real time as you type.
- **Post-session analytics dashboard** — WPM-over-time graph, accuracy ring, consistency score, character breakdown (correct / incorrect / extra / missed), a per-key error heatmap, a typing-rhythm replay, achievement badges, personal bests, a percentile estimate, and a written strengths/weaknesses summary.
- **Local session history** — stored entirely in `localStorage`, no account or backend required.
- **Premium UI details** — a custom "rhythm scope" waveform in the header that reacts to real keystroke timing, dark/light themes, 4 accent colors, adjustable font size, 3 caret styles, sound effects, keyboard shortcuts (`Tab` restart, `Esc` pause, `Ctrl+Enter` finish in Zen), and accessibility options (reduced motion, high contrast).

---

## 📸 Screenshots

<img width="1160" height="1909" alt="time-mode-results" src="https://github.com/user-attachments/assets/dbe2b600-ec54-4bed-a95a-7e32d047a4e4" />

<img width="1206" height="1882" alt="word-count-results" src="https://github.com/user-attachments/assets/2044d71f-4dcd-4875-a252-06c58ac14a80" />

<img width="1340" height="2308" alt="code-mode-results" src="https://github.com/user-attachments/assets/33d06aca-9664-430a-a3c4-39c9c5b1f2a4" />

---

## 💡 Key Learnings

- **Interviewing before generating matters.** Letting Claude ask 1–2 targeted questions before writing code produced a far more tailored result than a one-shot prompt would have — it directly shaped which modes and features got built.
- **Analytics are a design problem, not just a data problem.** The hardest part wasn't computing WPM or accuracy, it was presenting many simultaneous metrics (consistency, heatmaps, percentile, badges) without the dashboard feeling cluttered.
- **Adaptive difficulty is simpler than it sounds.** A rolling accuracy window nudging a single "difficulty level" variable was enough to make the practice text feel responsive, without needing a complex model.
- **A single HTML file can genuinely feel like a commercial product.** With careful typography, a consistent color system, and one distinctive visual signature (the live rhythm waveform), a no-framework build doesn't read as a "toy" typing test — it reads as a polished tool.
- **Real-world application:** this pattern — interview → single-file generation → iterate from screenshots — is directly reusable for building other self-contained internal tools (dashboards, calculators, mini-trackers) without spinning up a dev environment.
