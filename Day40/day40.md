# Day 40 — Build Your Own AI Assistant: Mental Wellness Guide

## 📌 What I Built

A **Mental Wellness Guide** — an AI assistant that gives people a calm space to process stress and get an immediate, actionable relief technique. Instead of a generic chatbot box, the interface walks through three distinct phases: a welcome screen where the user shares what's bothering them, a breathing-animation processing state, and a structured response screen with validation, clarifying questions, a guided breathing exercise, and next steps.

I built **two versions of the same assistant** — one calling the **Anthropic Claude API** and one calling the **Groq API (Llama 3.3 70B)** to compare a paid setup vs. a free one, so that anyone following along (regardless of which API key they have access to) can still test the assistant without hitting a paywall.

- `mental-wellness-guide-anthropic.html` → uses `https://api.anthropic.com/v1/messages` (needs a key starting with `sk-ant-`)
- `mental-wellness-guide-groq.html` → uses `https://api.groq.com/openai/v1/chat/completions` (needs a free key starting with `gsk_`, from console.groq.com/keys)

I tested the assistant live using the **Groq version**, since it's free and anyone can get a key in under 2 minutes without billing setup.

---

## 🧠 The System Prompt (The Assistant's "Brain")

```
AI Assistant Builder

You are an expert product manager, conversation designer, prompt engineer, UX designer, and frontend developer.

Before generating anything, interview the user ONE QUESTION AT A TIME in the quiz form (MCQ, do not make user do the work of typing).

1. What kind of assistant do you want to build? (Ask their domain and then niche, then give 4 suitable options.)
2. Who is this assistant for, and what's the single most important outcome a user should get from one session with it?
3. What inputs will people give it? (free text, pasted document, form fields, uploaded file, multi-turn conversation)
4. What should the output look like? (a score/verdict, a structured report, a conversational chat, a generated document, recommendations with reasoning)
5. Any tone or personality preference? (professional, friendly, blunt/expert, playful)

Then design and build:

1. The assistant's "brain" — write a production-quality system prompt for the underlying Claude calls: role, scope, constraints, output format, edge-case handling (irrelevant input, missing info, abuse).

2. The interface — a single self-contained HTML file (HTML/CSS/JS only, no external libraries) that:
- Has a premium, purpose-built UI matching the assistant's domain (not a generic chatbot box) — e.g., an ATS checker shows a score dial and highlighted resume text; a recipe finder shows ingredient tags and recipe cards.
- Calls the Claude API live via fetch to https://api.anthropic.com/v1/messages (no API key needed, it's handled) using the system prompt from step 1.
- Handles loading states, errors, and empty states gracefully.
- Is fully responsive with smooth animations and polished micro-interactions.

3. Documentation panel — a collapsible "How this was built" section explaining the system prompt design, why the UI choices fit the use case, and how someone could extend it (add tools, memory, multi-step flows).

Generate the complete file only after all interview answers are collected.
```

---

## 🖼️ Screenshots

I captured 4 screenshots while testing the flow.

1. **Screenshot 1 — Setup Screen**: The "Setup Required" screen asking for the Groq API key (`gsk_...`), with the "stays private in your browser" note. *(Shows the onboarding/setup step.)*
2. **Screenshot 2 — Welcome / Input Screen**: The "Welcome" phase with the textarea where the sample stress input about a work project deadline was typed in. *(Shows the user-input phase.)*
3. **Screenshot 3 — Response Screen**: "What I'm hearing" (validation), "Clarity on your stress" (clarifying questions), "What seems to be the core" (stress root insight), and the start of the "Relief Exercise: Guided Breathing" box-breathing animation. *(Shows the main AI-generated response.)*
4. **Screenshot 4 — Response Screen**: The "Your relief practice" grounding steps (Notice, Focus, Breathe, Relax, Calm) and "Next steps for calm" with the "Start Over" button. *(Shows the rest of the response and next-steps section.)*

<img width="1589" height="739" alt="setup" src="https://github.com/user-attachments/assets/858ae06f-e45b-41a4-8a52-7c677127ea93" />

<img width="1254" height="877" alt="interface" src="https://github.com/user-attachments/assets/d1f589e8-2134-45fa-b05d-80025ec1e14c" />

<img width="539" height="798" alt="guide-page1" src="https://github.com/user-attachments/assets/ada25d0f-51eb-4b57-87bf-c3264784036f" />

<img width="531" height="585" alt="guide-page2" src="https://github.com/user-attachments/assets/ee8fabed-049b-4dbd-845d-2cd1e0f4ea67" />

---

## 💡 Key Learnings

- **Structured JSON output turns a chatbot into a product.** By forcing the model to always return a fixed JSON schema, the frontend could render distinct, purpose-built UI sections (validation card, questions list, breathing animation, next-steps list) instead of a plain chat bubble.
- **Prompt constraints matter as much as instructions.** Explicitly telling the model *not* to diagnose, *not* to offer toxic positivity, and to cap clarifying questions at 3 kept responses safe, focused, and usable.
- **Testing with a free API (Groq) removed friction.** Since Anthropic API access requires billing, having a Groq fallback with an identical system prompt and JSON contract meant the assistant could be fully tested end-to-end without any paid key — useful for anyone following the same tutorial.
- **UI phases (welcome → processing → response) matter for perceived trust.** A breathing-circle loading animation on a wellness app feels appropriate to the domain, rather than a generic spinner — small UX choices reinforce the assistant's purpose.
- **Real-world application:** This pattern (interview → system prompt → structured JSON → custom UI) generalizes to any narrow-domain assistant — an ATS resume checker, a recipe finder, a journaling companion — by swapping the JSON schema and the rendering logic while keeping the same architecture.
