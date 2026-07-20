# Defend Your Experience (AI-Powered Adaptive Interview Defense Simulator)

An interview-prep tool that doesn't review your resume, it interrogates it. Upload a resume, LinkedIn profile, portfolio, or project, and the app extracts every meaningful claim and challenges you to defend it with a skeptical, adaptive AI interviewer.

---

## 🎯 What I Built

An adaptive interview simulator, built as a single self-contained HTML file, that:

1. **Adaptive Interviews** : generates personalized interview questions based on the uploaded experience (not generic templates).
2. **Experience Validation** : challenges every meaningful claim on the resume with intelligent, follow-up-driven questioning. Each answer shapes the next question, so the conversation gets deeper and more specific over time.
3. **Defense Report** : a final readiness score (e.g. 85/100) with a breakdown of which claims were well-defended, which were weak, and concrete next steps to strengthen them.
4. **Premium UX** : dark, editorial "case file" theme with orange accents, responsive layout, drag-and-drop upload, local storage/session history, and graceful handling of API errors.

---

## 🧠 Raw Prompt

```
# Defend Your Experience

You are an expert interviewer, recruiter, hiring manager, behavioral psychologist, communication coach, UX designer, and senior frontend developer.

Interview the user first, asking one question at a time and using MCQs whenever possible. Understand what they want to defend, why they are preparing, and the type of audience they expect to face. They may upload a resume, LinkedIn profile, portfolio, bio, project, research, performance review, startup story, freelance work, or any document describing their experience.

Before building the application, determine the user's preferred visual style. If previous conversation memory already indicates their design preferences, use those automatically. Otherwise, ask using an MCQ. Adapt the entire interface, typography, layout, animations, and interactions to that style instead of using a default design.

Generate a premium, fully interactive Defend Your Experience application as a single self-contained HTML file using only HTML, CSS, and JavaScript.

The application should use the Anthropic Messages API directly from the HTML application. Assume it runs inside Anthropic's HTML artifact environment where authentication is handled automatically. Never ask for an API key or build a backend.

Instead of reviewing the uploaded document, extract every meaningful claim and treat it as something that must be defended. Become an intelligent skeptic that continuously challenges the user with personalized follow-up questions generated specifically from their own experience. Every answer should influence the next question, allowing the conversation to naturally become deeper, more specific, and more realistic over time.

The application should feel like an adaptive interview rather than a fixed questionnaire. It should identify weak claims, missing evidence, vague statements, and opportunities to tell stronger stories while helping the user build confidence in defending their own experience. Every challenge and every recommendation should be unique to the uploaded content rather than based on generic interview templates.

Provide meaningful visualizations, progress tracking, confidence indicators, and a final Defense Report that clearly shows which experiences are well defended, which need improvement, and how the user can strengthen them before facing a real interviewer.

Make the purpose immediately obvious to first-time users with clear explanations, intuitive navigation, and helpful empty states. Support drag-and-drop uploads, local storage, session history, exports, responsive design, and graceful fallback handling for temporary API errors such as rate limits.

The objective is not to improve a resume. The objective is to help users confidently defend every claim they make about themselves.

Return only the complete HTML file.
```

---

## ❓ Interview Questions the App Asked Me (MCQ-driven onboarding)

1. **What are you preparing to defend?** → *A resume / job experience (interview prep)*
2. **Who's the audience you're preparing to face?** → *All (Technical interviewer / Hiring manager / HR-recruiter / Full panel)*
3. **How would you like to provide your experience?** → *Upload a resume/document now*
4. **Which visual style fits you best?** → *Let the AI decide based on my goals*

After onboarding, the interviewer moved into the real cross-examination asking targeted, claim-specific questions like *"You listed RAG systems on your resume, walk me through a specific failure case and how you debugged it,"* rather than generic behavioral questions.

---

## 🖼️ Screenshots

### Landing page

<img width="1327" height="853" alt="interface" src="https://github.com/user-attachments/assets/a21d3d8a-fce9-4dd6-83e6-103e5f7c1e88" />

### Upload & configuration screen

<img width="682" height="937" alt="upload and selection" src="https://github.com/user-attachments/assets/00554b52-0e88-41ef-bd2c-c2703e91e866" />

### *Defense Report

<img width="886" height="864" alt="Defence report" src="https://github.com/user-attachments/assets/53e4e0c8-28c1-42de-a72b-da699404e0d4" />

---

## 📄 Tool 

[`defend-your-experience.html`](./defend-your-experience.html)

---

## 💡 Key Learnings

- **Specific claims beat confident claims.** The biggest gap the tool surfaced wasn't in the resume's phrasing, it was in the missing *numbers*. "Built a RAG system" is a claim; "reduced retrieval latency by 40% for a 50k-document corpus" is a defense.
- **Adaptive follow-ups reveal depth better than static question banks.** Because each answer fed the next question, shallow answers got probed harder and strong answers moved on faster, much closer to how a real interviewer behaves than a fixed list of "tell me about a time when..." questions.
- **Preparing to defend > preparing to present.** Rehearsing a pitch is different from being cross-examined on it. This tool made me realize how much of interview readiness is really about anticipating "prove it" moments, not polishing delivery.
- **Building this also reinforced good AI-app fundamentals**: keeping the whole experience in a single self-contained HTML file, handling API errors gracefully (rate limits, retries), and using MCQs during onboarding kept the UX fast without sacrificing personalization.
