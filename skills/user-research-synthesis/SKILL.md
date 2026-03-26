---
version: 1.0.0
name: user-research-synthesis
description: Synthesises interviews, surveys, feedback logs into themes, patterns, contradictions, and product implications — not summaries. Triggers: "synthesise my research", "analyse these interviews", "what does this research tell us", "find patterns in this feedback", "research synthesis", "what are users saying", "analyse this feedback", "make sense of these interviews".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces genuine synthesis from raw research data — not summaries. It grounds every insight in direct quotes, surfaces contradictions, and produces prioritised product implications.

Accepts: interview transcripts, survey responses, support tickets, feedback logs, analytics summaries. Claude's context window handles 50+ pages of transcripts.

---

## Process

### Step 1 — Quote Extraction
Extract the most significant direct quotes from the data. For each:
- Note the source
- State why it matters

### Step 2 — Pattern Identification
Identify recurring themes. For each theme:
- Name it specifically ("Notification fatigue during onboarding" not "UX issues")
- Count how many participants expressed it
- Note sentiment strength (mild frustration vs. dealbreaker)
- Include 2–3 supporting quotes with attribution

### Step 3 — Contradiction Mapping
Identify where participants disagreed or gave contradictory signals. Analyse what might explain each contradiction — these often contain the most valuable insights.

### Step 4 — Insight Hierarchy
Prioritise findings into three tiers:
- **Critical**: Affects core value proposition or retention
- **Important**: Significant pain point with clear solution path
- **Interesting**: Worth tracking but not immediately actionable

### Step 5 — Product Implications
For each Critical and Important insight, suggest a specific product response — not a vague recommendation.

---

## Constraints

- Ground every claim in direct quotes — no insights without evidence
- If sample size is too small for confident conclusions, say so explicitly
- Distinguish between what participants SAID they want and what their behaviour suggests they actually need
- Flag any interviewer bias detectable in the questions asked
- Mark any inference without direct support as `[INFERRED]`

---

## File output

Save the completed synthesis as `[project-slug]-RESEARCH.md` in the current working directory.

Confirm save with: `Saved: [filename]`

Display the full document inline after saving.

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
