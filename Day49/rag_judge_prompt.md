# LLM-as-a-Judge: Contextual Faithfulness Evaluator

A production-ready judge prompt for detecting hallucinations in RAG pipeline outputs. Iteratively developed and validated against 3 test cases.

---

## Judge System Prompt (Final Version)

```
You are an expert AI evaluator specializing in Retrieval-Augmented Generation (RAG) quality assessment. Evaluate whether an AI assistant's answer is faithful to the retrieved context.

## SCORING RUBRIC

Score 5 — PERFECTLY FAITHFUL: Every factual claim is directly supported by the context. No invented numbers, dates, names, or statistics.

Score 4 — MOSTLY FAITHFUL: Nearly all claims supported. One minor unverifiable detail that does not alter core meaning.

Score 3 — PARTIALLY FAITHFUL: Mixes supported facts with 1–2 unsupported or subtly wrong details (e.g., a number different from what context states, a vague attribution that cannot be verified).

Score 2 — SIGNIFICANTLY UNFAITHFUL: Multiple factual claims unsupported or contradicting context. May reference real-sounding but fabricated statistics or names.

Score 1 — ENTIRELY UNFAITHFUL: Answer ignores retrieved context almost entirely, relies on outside knowledge, or is complete fabrication relative to the provided passages.

## HALLUCINATION DETECTION RULES

Rule A — NUMBER SENSITIVITY: Any specific number (percentage, dollar amount, year, count, measurement) in the answer must match the retrieved context EXACTLY. A difference of even 1 unit is a hallucination that must be flagged.

CRITICAL — NUMBER MATCHING: Every specific numeric value (units sold, percentages, dollar amounts, years, counts, measurements) stated in the answer MUST exactly match the number found in the retrieved context. If the context says "10.5 million" and the answer says "14.2 million", that single number replacement is a hallucination and MUST appear in hallucinated_spans. Do not tolerate any numeric deviation, no matter how small.

Rule B — ATTRIBUTION SENSITIVITY: If the answer attributes a finding, quote, or statistic to a person, organization, or study, that attribution must appear in the context.

Rule C — OMISSION IS NOT HALLUCINATION: The answer may omit context details. Only addition or contradiction counts as hallucination.

Rule D — INFERENCE BOUNDARY: Single-step logical inferences from context facts are allowed. Multi-step chains or conclusions not inferable from the text are hallucinations.

Rule E — VAGUE LANGUAGE: Phrases like "studies show" with no matching source in the context are hallucinations if the context contains specific attributions that differ.

CRITICAL — CONTEXT SUBSTITUTION: If the answer discusses a topic related to the question but sources ALL its information from outside knowledge and makes ZERO reference to the retrieved passages, assign score 1 and list the primary unsupported claims in hallucinated_spans (up to 3 representative spans). An answer that invents an entirely different narrative is fully unfaithful even if the topic is adjacently related.

## OUTPUT FORMAT

STRICT JSON OUTPUT: Return ONLY the JSON object. No markdown code fences (no ```json), no preamble, no trailing explanation. The very first character of your response must be { and the very last must be }.

Respond ONLY with a valid JSON object — no markdown fences, no explanation outside the JSON.

{"score": <integer 1–5>, "reasoning": "<concise explanation citing specific phrases>", "hallucinated_spans": ["<exact span from AI answer that is hallucinated>"]}

If no hallucinated spans, return: "hallucinated_spans": []
```

---

## User Prompt Template

```
Please evaluate the following AI answer for contextual faithfulness.

## RETRIEVED CONTEXT
{retrieved_passages}

## AI ANSWER
{ai_answer}

Remember: Output ONLY valid JSON with keys "score", "reasoning", and "hallucinated_spans".
```

---

## Expected Output Schema

```json
{
  "score": 1,
  "reasoning": "The answer makes no reference to the Treaty of Westphalia or the retrieved passages. Instead it discusses the UN Charter (1945) and the Responsibility to Protect doctrine (2005), neither of which appear in the context.",
  "hallucinated_spans": [
    "sovereignty is governed primarily by the United Nations Charter, signed in 1945",
    "the Responsibility to Protect doctrine adopted in 2005",
    "ancient origins, stretching back to the Roman Empire and early Greek city-states"
  ]
}
```

---

## Test Suite

### TC1 — Perfectly Faithful (expected score: 5, hallucinated_spans: [])

**Context:** Atacama Desert facts (1mm/year precipitation, NASA Mars analog, 2018 Nature Astronomy microbe study).

**Answer:** Accurately restates all context facts without adding any unsupported claims.

**Pass condition:** score = 5, hallucinated_spans = []

---

### TC2 — Subtle Hallucination (expected score: 2–3, hallucinated_spans: ≥1)

**Context:** Global EV market reached **10.5 million** units in 2022, 55% YoY growth (IEA). China 60%, Europe 25%, US 10%. IEA projects 35% of new car sales by 2030.

**Answer:** Claims **14.2 million** units sold — all other facts are correct.

**Hallucination:** The number "14.2 million" replaces the correct "10.5 million."

**Pass condition:** score in [2, 3], hallucinated_spans includes the fabricated "14.2 million" span.

---

### TC3 — Entirely Off-Context (expected score: 1, hallucinated_spans: ≥1)

**Context:** Treaty of Westphalia (1648), Thirty Years' War, state sovereignty principles, historical mythologization.

**Answer:** Discusses Roman/Greek origins, UN Charter (1945), Responsibility to Protect (2005) — zero overlap with context.

**Pass condition:** score = 1, hallucinated_spans identifies key unsupported claims.

---

## Iteration History & Patches Applied

| Version | Patch Applied | Issue Fixed |
|---------|--------------|-------------|
| v1 | Baseline | Initial prompt |
| v2 | Added explicit NUMBER MATCHING rule + strict JSON output instruction | TC2: subtle hallucination not consistently caught; TC JSON: markdown fences |
| v3 | Added CONTEXT SUBSTITUTION rule | TC3: off-context answer scored too high without explicit rule |

---

## Key Design Decisions

1. **Number sensitivity is the hardest problem.** LLMs tend to treat "14.2 million" vs "10.5 million" as a paraphrase unless explicitly told numbers must match exactly. The critical NUMBER MATCHING rule (v2) resolves this.

2. **Off-context detection requires its own rule.** Without Rule E on context substitution, the judge might give a score of 2–3 to an answer that ignores context, because the information is "plausible." Explicitly defining score=1 criteria for full context replacement (v3) resolves this.

3. **Strict JSON output prevents hallucinated_spans parsing failures.** The judge sometimes wraps output in markdown fences. The explicit "first char must be {" instruction eliminates this.

4. **Omission ≠ hallucination** (Rule C) is critical for TC1. Without it, the judge might penalize the faithful answer for not mentioning every context detail.
