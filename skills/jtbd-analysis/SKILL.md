---
version: 1.0.0
name: jtbd-analysis
description: Maps customer jobs (functional, emotional, social), desired outcomes, four forces, overserved/underserved opportunities from research data. Triggers: "JTBD", "jobs to be done", "what job are customers hiring us for", "understand customer motivations", "why do customers use this", "what's the underlying need", "analyse customer jobs", "customer job analysis".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill runs a rigorous JTBD analysis from real customer data. It separates what customers say they want from what they are actually trying to accomplish, and grounds every insight in direct evidence.

Accepts: interview transcripts, support tickets, survey responses, behavioural data, feedback logs. Claude's context window handles 50+ pages of raw data.

---

## Process

### Step 1 — Job Identification

Identify core jobs customers are hiring this product to do. For each job:

**Format:** [Verb] + [Object] + [Contextual clarifier]
Example: "Reduce time spent reconciling expense reports at month-end"

- Classify as: Functional / Emotional / Social
- Cite specific quotes or behaviours from the data — do not infer jobs without evidence

### Step 2 — Desired Outcome Statements

For each functional job, generate desired outcome statements.

**Format:** [Direction of improvement] + [Unit of measure] + [Object of control] + [Contextual clarifier]
Example: "Minimise the time it takes to identify discrepancies in submitted expenses"

Outcomes must be: solution-agnostic, stable over time, measurable, within the customer's control.

### Step 3 — Four Forces Analysis

Map the forces shaping switching behaviour:
- **Push**: What is driving customers AWAY from current solutions?
- **Pull**: What is attracting them TOWARD a new solution?
- **Anxiety**: What fears or concerns hold them back from switching?
- **Habit**: What existing behaviours keep them attached to the status quo?

Ground each force in specific data points.

### Step 4 — Overserved and Underserved Outcomes

- **Overserved**: Current solutions do this well — low opportunity
- **Underserved**: Customers struggle here — high opportunity
- **Unserved**: Nobody is addressing this — potential breakthrough

### Step 5 — Strategic Implications

Recommend where to focus product investment based on underserved and unserved outcomes with highest frequency and importance.

---

## Constraints

- Separate what customers SAY from what their stories and behaviours reveal — these often differ
- Every job and outcome must trace back to specific evidence; mark inferences without direct support as `[INFERRED]`
- Do not conflate solutions with jobs: "I want a better dashboard" is a solution; the job is "quickly assess business health without manual data gathering"
- If data is insufficient for confident JTBD analysis, say what additional research is needed rather than fabricating insights

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-JTBD.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
