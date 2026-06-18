# Day 18 — Brain Dump Action Planner (Custom Claude Skill)

## #60DayClaudeChallenge

Today's task: build a reusable Custom Skill in Claude that turns messy, unstructured input (meeting transcripts, brainstorm notes, voice memo dumps, class notes) into a clean, interactive HTML dashboard without inventing or assuming anything that wasn't actually said.

---

## 1. What I Built

A Custom Skill named **`brain-dump-action-planner`** that Claude can run on any "brain dump" style text and convert into a structured, Notion/Linear/Asana-style dashboard with:

- Summary
- Key Takeaways
- Action Items (table: Task / Owner / Deadline / Status)
- Open Questions
- Risks / Blockers
- Conflicts
- Additional Notes
- (Transcript Mode) Speaker Summary, Decisions by Speaker, Action Items by Speaker, Attribution Notes
- (Merge Mode) Duplicate Items, Conflict Resolution Review, Source Note

The core rule baked into the skill: **everything in the output must come directly from the source notes** — no invented owners, no guessed deadlines, no filled-in gaps. Anything missing is explicitly labeled `Not specified`.

---

## 2. Skill Setup (Steps Followed)

1. Opened Claude, set effort level to Low/Medium for faster iteration.
2. Went to **Customize → Skills** → Create Custom Skill.
3. **Skill Name:** `brain-dump-action-planner`
4. **Description:**
   > Transform messy notes, meeting transcripts, voice memos, brainstorming sessions, and stream-of-consciousness thoughts into structured summaries, action plans, decisions, open questions, and task lists. Organize information clearly without inventing, assuming, or filling gaps. Preserve all names, dates, numbers, and terminology exactly as provided.
5. **Instructions:** pasted the full instruction block covering Output Requirement, Required Sections, Status Badges, Missing Information rule, Transcript Mode, Merge Mode, and Design Goals (Notion/ClickUp/Linear/Asana/Airtable-style dashboard, self-contained HTML starting with `<style>`, no markdown, mobile responsive, collapsible sections, hover effects, soft shadows).
6. Saved the skill.

<img width="1842" height="847" alt="skill" src="https://github.com/user-attachments/assets/acd486e7-8195-4b55-90ae-00ae39e3ae3e" />

---

## 3. Test Run — Q3 Cross-Functional Meeting Transcript

Used the provided sample: a 5-speaker meeting transcript (CEO, VP Product, CTO, Head of Growth, CFO) discussing a delayed AI Analytics launch, a 40% cloud cost spike, and EU market expansion ahead of the EU AI Act deadline.

Claude automatically detected this was a multi-speaker transcript and ran in **Transcript Mode**, generating the dashboard below without my needing to re-type or re-paste any of the instructions.

<img width="1081" height="817" alt="Summary   Key takeaways" src="https://github.com/user-attachments/assets/1e7512be-3617-4469-9fef-bcf881463d4f" />

<img width="1087" height="371" alt="Action Items" src="https://github.com/user-attachments/assets/73866c04-1af5-4625-bb85-b0d3a258704e" />

<img width="1012" height="860" alt="Open ques and risks" src="https://github.com/user-attachments/assets/92e858eb-ef0d-40ae-82fd-7695929c86da" />

<img width="1020" height="645" alt="Conflicts   Additional notes" src="https://github.com/user-attachments/assets/228e863a-6c6c-4575-83bb-42fa5d995657" />

<img width="1016" height="877" alt="Speaker summary" src="https://github.com/user-attachments/assets/a0301d91-7513-4d8a-aab2-3fc43f7b037f" />

<img width="1360" height="640" alt="Detailed records" src="https://github.com/user-attachments/assets/4cb7c3d3-5494-43de-8867-5d3b6d240e79" />

---

### What the dashboard correctly captured:
- 4 distinct conflicts (engineering bandwidth, budget-vs-contractors, marketing-vs-legal timing, and an unconfirmed cost attribution Rahul raised about Sarah's environment) — all flagged, none resolved by Claude.
- Action items correctly attributed per speaker, including an "Attribution Note" where ownership was ambiguous (Q4 budget requests directed at "everyone," not one named owner).
- Exact figures preserved: $85,000 cloud bill, 40% over budget, $15,000/month target cut, $20,000 marketing spend, 5,000+ waitlist leads, July 1st / June 25th / Tuesday deadlines — nothing rounded or guessed.
- No invented EU compliance answer — the open question about EU server data residency vs. encryption-in-transit was correctly left as "unresolved," since Sarah herself said "I'm not entirely sure" in the transcript.

---

## 4. Reusability Test

Re-ran the same skill on a second, unrelated input (brainstorm-style class notes) in a new chat **without re-entering any instructions**. The skill name alone was enough to trigger the same dashboard format and rules.

---

## 5. Key Learnings

- **Constraint-first skill design works better than freeform prompting.** Explicitly telling the skill "never invent, assume, or fill gaps" and "display 'Not specified' for missing info" produced a dashboard that stayed factually grounded — useful for real meeting notes where hallucinated owners/deadlines would actually cause harm.
- **Mode detection is automatic.** I didn't have to tell Claude "use Transcript Mode" — it inferred that from the presence of labeled speakers and applied the right extra sections (Speaker Summary, Attribution Notes) on its own.
- **Skills remove repetitive prompt engineering.** Once saved, the 60+ line instruction block never needs to be retyped — every future "brain dump" (meeting, voice memo, brainstorm) gets the same consistent, professional dashboard output with a single short prompt.
- **Real-world application:** this is directly usable for actual work — meeting recaps for stakeholders who skipped the call, voice-memo-to-task-list conversion, or merging notes from multiple people on the same project (Merge Mode) while keeping every conflicting detail visible instead of silently "averaging" it away.

