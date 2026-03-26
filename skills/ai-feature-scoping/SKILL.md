---
version: 1.0.0
name: ai-feature-scoping
description: Scopes a known AI feature — value prop, accuracy thresholds, failure modes, build/buy, measurement. Triggers: "scope this AI feature", "AI feature feasibility", "plan an AI feature", "how do we build this AI thing", "what could go wrong with this AI", "AI feature design", "spec out this AI feature", "de-risk this AI feature".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill scopes AI features rigorously, covering dimensions traditional feature scoping misses: accuracy thresholds, failure modes, false positive/negative trade-offs, and ongoing operational costs.

## Required inputs

Ask for: product name, proposed AI feature, available data/models, target user and context, current state (how users do this today).

---

## Scoping dimensions

### 1. Value Proposition Clarity
- What specific user outcome does this improve, and by how much?
- Is AI the right solution, or would a deterministic approach (rules, filters, templates) achieve 80% of value at 20% complexity? Be honest.

### 2. Accuracy and Failure Mode Analysis
- What is the minimum accuracy threshold for this to be useful vs. annoying?
- What happens when the AI is wrong? Categorise by severity: embarrassing / costly / dangerous
- What is the cost of a false positive vs. false negative for this use case?
- How will users recover from or correct AI errors?

### 3. Scope — Three Tiers

| Tier | Focus |
|---|---|
| MVP | Minimum viable AI that delivers core value |
| V1 | Confidence and reliability improvements |
| V2 | Full vision with personalisation and learning |

For each tier: capabilities in/out, data requirements, expected accuracy range, key risks.

### 4. Build vs. Buy vs. API
- What is available off-the-shelf?
- What requires custom development?
- Where are the moat / differentiation opportunities?

### 5. Measurement Framework
- How will you know if the AI is actually helping users?
- What leading indicators will you track before outcome metrics?
- How will you detect model degradation over time?

---

## Constraints

- If this is "AI for AI's sake" without clear user value, say so directly
- Do not assume unlimited data availability or quality
- Account for ongoing operational costs — not just build cost
- Consider regulatory and privacy implications explicitly

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
