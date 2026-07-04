# Day 34 — Marketing Detective: Solve Marketing Mysteries Through Interactive Investigation

## 🕵️ What I Built

A fully interactive **Marketing Detective** application game where you investigate fictional marketing campaigns like a detective, gather evidence from a corkboard, identify the primary marketing mistake, and receive a detailed learning report.

---

## 📸 Screenshots

### Case 1

<img width="1886" height="896" alt="briefing" src="https://github.com/user-attachments/assets/d8fa57b1-9255-475c-a14c-ec28483410bf" />

<img width="1881" height="897" alt="board" src="https://github.com/user-attachments/assets/e47c4de7-f680-4312-af0b-7c69e96e595d" />

<img width="1882" height="762" alt="evidence_modal" src="https://github.com/user-attachments/assets/c4395779-edf8-4de7-85c4-d38687e62f38" />

<img width="1882" height="762" alt="suspect_lineup" src="https://github.com/user-attachments/assets/560c76b6-19c5-47e8-bf28-d190ce3dc90a" />

<img width="1891" height="897" alt="learning-report" src="https://github.com/user-attachments/assets/443b0155-c11f-460c-b8d8-48da6623a42c" />

### Case 2

<img width="1872" height="822" alt="board-2" src="https://github.com/user-attachments/assets/9d7e1c6e-9762-4c1e-806b-6d04602cab3b" />

<img width="1872" height="677" alt="suspect-lineup-2" src="https://github.com/user-attachments/assets/3fab0460-9fa2-4da8-a935-ed646411d282" />

<img width="697" height="862" alt="learning-report-2" src="https://github.com/user-attachments/assets/cd06cc62-16cb-412a-8288-b1c615826200" />

---

## 🎯 Prompt Used

```
You are an expert frontend developer, UX designer, instructional designer, and marketing strategist.

Create a beautiful single-file HTML application called 'Marketing Detective'.
Use React via CDN + Babel. However, if React/Babel would prevent the app from running 
reliably as a standalone local HTML file, automatically switch to an equivalent 
implementation using pure HTML, CSS and vanilla JavaScript. 
Do not use Tailwind, npm, backend, APIs, databases, images or external assets.

The application should feel like a polished detective game, not a business dashboard. 
Every interaction should create curiosity before revealing the next clue.

Generate 10 detailed fictional marketing cases. If output quota allows, expand to 15–20 cases. 
Store them inside a JavaScript array and randomly load a new case each replay.

Each case must contain:
• Company Name
• Industry
• Campaign Objective
• Target Audience
• Marketing Channels
• Budget Allocation
• Campaign Metrics (Reach, CTR, Engagement, Conversions, Sales)
• Customer Comments
• Social Media Performance
• One Primary Marketing Mistake
• Three Supporting Clues
• Correct Explanation
• Suggested Improvements

User Flow:
1. Case Assignment
2. Investigation Board
3. Interactive Investigation with draggable evidence
4. Solve the Case
5. Case Closed animation
6. Learning Report

Design a premium dark detective aesthetic using corkboards, folders, sticky notes, 
push pins, paper textures, glowing accents, smooth transitions, hover effects, 
progress indicators, animated charts, and responsive layout.

Return ONLY the complete HTML file.
```

---

## 🧠 Key Learnings

*Based on the two cases I personally investigated: StreamVerse and NeonByte.*

### Case 1 — StreamVerse (Video Streaming Service)

**Objective:** Convert free-trial sign-ups into paying annual subscribers.
**Metrics:** Reach 7.9M · CTR 2.1% · 52,000 trial starts · Sales $0.6M ARR (target missed)

#### What went wrong:
The marketing team promoted upcoming and in-development titles as if they were already streaming. Podcast sponsorships and teaser trailers blurred the line between "available now" and "coming soon." Users signed up expecting the catalog they saw advertised — and when they found several flagship shows weren't available yet, they cancelled.

Trial-to-paid conversion was the lowest in company history, even though trial starts hit a company record.

#### Key Lesson:
**Top-of-funnel success means nothing if the product can't deliver on the promise at conversion time.** Reach and trial starts are vanity metrics if the experience behind them breaks trust. Marketing must match reality — not aspiration.

#### Suggested Improvements:
- Clearly separate "available now" from "coming soon" content in all ads
- Align campaign launch timing with actual content availability, not production milestones
- Use current catalog previews in ads rather than aspirational reels
- Set expectations early in the trial with an in-app content calendar

### Case 2 — NeonByte (Mobile Gaming)

**Objective:** Sustain install volume and in-app purchase revenue for a hit mobile puzzle game over a 6-week campaign.
**Metrics:** Reach 12.4M · CTR 0.6% (week 1) → 0.09% (week 6) · Installs down 71% by week 6 · IAP revenue down 44%

#### What went wrong:
NeonByte launched with one strong creative and never rotated new variations. As the same users saw the identical ad dozens of times, performance predictably collapsed. CTR dropped 85% over 6 weeks — a textbook case of creative fatigue. Targeting and budget were sound, but the creative was the silent killer.

#### Key Lesson:
**Creative fatigue is measurable — and predictable.** A steady week-over-week CTR decline with stable targeting is a system warning, not bad luck. Ad frequency per unique user is a leading indicator you must monitor from day one. Once fatigue sets in, installs and revenue follow downward.

#### Suggested Improvements:
- Build a creative rotation calendar with fresh variants every 1–2 weeks
- Monitor frequency-per-user and set automatic alerts when it exceeds a fatigue threshold
- Pre-produce multiple creative concepts before launch, not just one "hero" ad
- Use dynamic creative optimization tools to automatically test and rotate top performers

### Broader Learning — The Detective Format Works

The investigation flow forced a discipline I don't usually apply when reading a marketing case study:

1. Examine raw data first (metrics, budget, channels) before jumping to conclusions
2. Read customer comments as qualitative evidence — not decoration
3. Connect three independent clues before forming a verdict
4. Only then explain the mistake — and suggest improvements

This mirrors how strong marketers actually debug campaigns. One metric anomaly is noise. Three converging clues pointing at the same failure point — that is the real story.

