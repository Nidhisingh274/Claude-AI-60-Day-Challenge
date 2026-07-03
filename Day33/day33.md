# Day 33 — Build a Media Integrity Analyzer

Learn to evaluate information before believing it.

---

## 🎯 What I Built

An interactive, app called **Media Integrity Analyzer** that teaches media literacy through **guided discovery** instead of quizzes or memorization. Users react to a fake headline and a fake social post *before* seeing the "correct" answer, then get a full breakdown of the manipulation techniques used.

**Theme chosen:** Crimson Press (editorial dark theme with red/gold accents)

---

## 🧠 Concepts Covered

| # | Concept | Description |
|---|---------|-------------|
| 1 | **Headline Analysis** | How headlines influence perception and attention |
| 2 | **Emotional Awareness** | Recognizing language designed to trigger emotional reactions |
| 3 | **Critical Thinking** | Evaluating content objectively before accepting conclusions |
| 4 | **Interactive Learning** | Building educational HTML apps that teach through exploration |

---

## 📝 Prompt Used

```
You are an expert frontend developer, UX designer, instructional designer, and media literacy analyst.

Ask the user to choose a color theme from a few options (including Claude Orange).
Create a beautiful single-file HTML application called 'Media Integrity Analyzer'.
Use pure vanilla CSS and JS. No Tailwind, npm, backend, APIs, images, or external assets. Everything must work offline in one HTML file.
The goal is to teach media literacy through interactive discovery, not test prior knowledge. The experience should feel like a guided lesson where users learn by observing, thinking, and then revealing the answer.
Make it interactive.
Before each challenge, briefly explain the concept in simple language, why it matters, and how it applies to everyday life.

Challenge 1: Headline Detective
- Generate a fictional news headline and matching article.
- Ask: Would you click this? (Yes / Maybe / No)
- Ask the user to identify exaggerated or misleading parts.
- Reveal the Headline Accuracy Score, highlighted mismatches, explanation, fair rewritten headline, and key takeaway.

Challenge 2: Emotion Detector
- Generate a fictional social media post, reel caption, or article excerpt.
- Ask how it made the user feel and which words influenced that feeling.
- Reveal the target audience, intended emotional response, manipulation technique, highlighted emotional phrases, neutral rewrite, and key takeaway.

Display live Media Integrity metrics:
- Headline Accuracy
- Source Reliability
- Emotional Manipulation
- Audience Targeting

Finish with a Media Integrity Dashboard containing:
- Overall Media Integrity Score
- What the user learned
- Biggest red flag
- Three practical media literacy habits
- Replay with completely new scenarios

Design a premium editorial-style dark interface with smooth animations, progress indicators, hover effects, modern cards, and responsive layout.
Ensure there are zero syntax errors.
Return ONLY the complete HTML inside one code block.
```

---

## 🖼️ Screenshots

<img width="1212" height="923" alt="intro" src="https://github.com/user-attachments/assets/3343b152-9a36-4c52-91c9-91a094bcb836" />

<img width="1234" height="887" alt="challenge1-concept" src="https://github.com/user-attachments/assets/5cf73aac-670d-420a-ad2c-b12d549aeebd" />

<img width="1244" height="1239" alt="challenge1-headline" src="https://github.com/user-attachments/assets/cf71eb3a-2e39-42d4-8988-df5a223e986f" />

<img width="1243" height="1509" alt="challenge1-reveal" src="https://github.com/user-attachments/assets/5db9043d-11e2-4bda-87c4-a3383b93a6c6" />

<img width="1269" height="896" alt="challenge2-concept" src="https://github.com/user-attachments/assets/a6e7d212-60f6-4823-a728-93a3b5d5318e" />

<img width="1242" height="1165" alt="challenge2-post" src="https://github.com/user-attachments/assets/8584c8ce-02ae-4431-9c29-a15923cdf2c2" />

<img width="1246" height="1594" alt="challenge2-reveal" src="https://github.com/user-attachments/assets/7838df04-f389-4c46-bf0f-ebd15038bb4d" />

<img width="1248" height="1686" alt="dashboard" src="https://github.com/user-attachments/assets/481e0e86-33d0-4e9a-99d1-abb0040b298d" />

---

## 💡 Key Learnings

- **Quotation marks aren't proof.** Words like `"poisoned"` or `"refuses"` in quotes can imply an accusation while giving the writer deniability — the article underneath was actually a routine, well-explained update.
- **"Proves" and "stunned" are red flags, not facts.** Real researchers hedge their claims; headline writers often don't. If a headline sounds more confident than the study it's citing, that gap is worth noticing.
- **Urgency is a manipulation lever, not a real deadline.** Phrases like "share before this gets deleted" or "sells out again" are designed to make you act before you think — not because the risk is real.
- **Emotional reactions are often the intended product**, not a side effect. Fear, outrage, and FOMO get engineered into content because they drive shares faster than calm, accurate writing does.
- **Source reliability matters as much as the words.** An anonymous account with no named author and no correction policy should lower your trust before you even read the caption.
- **Building this reinforced instructional design principles** — letting the user guess *first* (before revealing the "right" answer) creates a much stronger learning moment than just explaining the concept upfront.

