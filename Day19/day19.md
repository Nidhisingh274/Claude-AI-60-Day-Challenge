# Day 19 — Football Intelligence Hub

## 🎯 What I Built

Used Claude to turn a football data workbook (historical team performance, current contender form, star players, and **live 2026 World Cup group-stage results**) into a 3-stage interactive experience:

1. **FIFA World Cup 2026 Prediction Report** — winner, runner-up, dark horse, and players to watch, each with a confidence score, supporting evidence, and key risks.
2. **Football IQ Quiz** — adaptive 5-question quiz → Football Awareness Score + fan classification.
3. **Messi vs Ronaldo Personality Match** — 12-question personality assessment → compatibility %, archetype, and recommendations.

## 🧰 Tools Used
- Claude.ai (Sonnet, effort: Low)
- Uploaded workbook: `ABTalks_WorldCup_Intelligence_Master.xlsx`
- Built-in interactive question widgets for the quiz stages
- Inline charts for the prediction data and Messi/Ronaldo comparison

## 📋 Prompt Used

```
Football Intelligence Hub Prompt
You are a Football Intelligence Analyst, Sports Educator, and Personality Assessor. Use the uploaded workbook as your primary data source to guide the user through three stages of a Football Intelligence Experience.

Stage 0 — Knowledge Level Check
First, ask: 'How familiar are you with football?' with options from 'I know almost nothing' to 'I actively follow football and major tournaments.' Wait for their response and use it only to adjust your explanation depth, terminology, and examples throughout. Do not calculate scores yet.

Stage 1 — FIFA World Cup 2026 Prediction Report
Analyze the workbook's historical performance, current tournament results, contender strength, and player information to identify patterns influencing outcomes. Then deliver: the most likely winner, runner-up, a dark horse nation, and players to watch. For each prediction include a 0–100% confidence score, supporting evidence, key risks, and factors working against it. Adapt depth to the user's knowledge level, then automatically move to Stage 2.

Stage 2 — Football IQ Quiz
Create an interactive 4–5 question multiple-choice quiz with a mix of beginner, intermediate, and advanced questions adapted to their knowledge level. Present all questions before scoring. After collecting answers, calculate a Football Awareness Score (0–100), assign a classification (Beginner Fan, Casual Viewer, Football Follower, Football Enthusiast, or Football Expert), and highlight their strongest knowledge areas, weakest areas, and key gaps. Then automatically move to Stage 3.

Stage 3 — Messi vs Ronaldo Personality Match
Build a 10–15 question interactive quiz using workbook traits, mixing multiple-choice and rating-scale questions without asking direct Messi vs Ronaldo questions. Evaluate ambition, discipline, leadership, teamwork, creativity, competitiveness, confidence, work ethic, learning style, and decision-making style. After responses, calculate Messi and Ronaldo compatibility percentages, explain why they match each legend, state which legend they resemble more and why, assign one football personality archetype with description and key traits, and recommend one player, one club, one national team, and one rivalry to explore.

Final Output — Football Intelligence Profile
Generate a single profile containing: the World Cup 2026 prediction report, Football Awareness Score, fan classification, Messi and Ronaldo compatibility scores, personality archetype, recommended players/teams/rivalries, and a key insights summary.
```

## 📊 Output Summary

| Metric | Result |
|---|---|
| Self-rated knowledge level | "I follow football casually" |
| WC2026 winner prediction | Argentina (35% confidence) |
| Runner-up prediction | Spain (28% confidence) |
| Dark horse | Morocco (18% confidence) |
| **Football Awareness Score** | **100 / 100 — Football Expert** |
| **Messi compatibility** | **27%** |
| **Ronaldo compatibility** | **73%** |
| **Personality archetype** | **Strategic Commander** |
| Recommended player / club / team / rivalry | Jude Bellingham / Real Madrid / Germany / El Clásico |

## 📸 Screenshots

<img width="725" height="820" alt="stage-1 A" src="https://github.com/user-attachments/assets/cc2bb0d4-b2ca-40bf-a0fc-7c0453c73104" />

<img width="657" height="390" alt="stage-1 B" src="https://github.com/user-attachments/assets/dd10da43-b15b-432e-96d0-903085523f27" />

<img width="727" height="345" alt="stage-1 C" src="https://github.com/user-attachments/assets/0bc6596c-b1a8-4eb4-ac94-86c25818287b" />

<img width="737" height="412" alt="stage-2" src="https://github.com/user-attachments/assets/ce6907b5-55cb-4733-8c41-55f2c5f92dd0" />

<img width="726" height="420" alt="stage-3" src="https://github.com/user-attachments/assets/90c1f50b-7a74-4560-a1b3-0dc45bf29454" />

<img width="651" height="675" alt="stage-2   3" src="https://github.com/user-attachments/assets/e8cbdbb3-a58d-4c35-bbc9-a20f1ba742dd" />

<img width="732" height="532" alt="final round" src="https://github.com/user-attachments/assets/e4faa15d-ef95-4566-9178-2b81fbb7be68" />

<img width="597" height="252" alt="Output-1" src="https://github.com/user-attachments/assets/144315cf-a2c3-435c-9fa7-e681393743fc" />

<img width="591" height="597" alt="Output-2" src="https://github.com/user-attachments/assets/0cd76a72-e674-40fd-84b1-3b0c879acd9e" />

<img width="605" height="545" alt="Output-3" src="https://github.com/user-attachments/assets/61a70d45-c0ad-46f4-a746-4d65487a7bd5" />


## 💡 Key Learnings

- Claude can blend **structured data analysis** (historical win %, live tournament tables) with **probabilistic reasoning** (confidence-scored predictions) in one workflow.
- Multi-stage prompts work well when each stage explicitly says "automatically move to the next stage" — it keeps the experience flowing without extra prompting.
- Interactive quizzes (MCQ + rating scales) turn a static prediction report into an engaging, personalized experience.
- A simple weighted-trait scoring rubric let Claude convert subjective personality answers into objective-feeling compatibility percentages — useful pattern for any "which X are you" style assessment.
- Pairing text analysis with small inline charts (form score comparison, compatibility bars) made the data easier to scan than plain numbers.
