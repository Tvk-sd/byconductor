---
version: 1.0.0
name: competitor-analysis
description: Steelman-first competitive analysis — makes the case for why competitors win before assessing your position. Triggers: "competitor analysis", "competitive landscape", "how do we stack up against", "analyse our competition", "competitive positioning", "who are our competitors", "competitive threats", "where's the whitespace", "what's the competition doing".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces competitive analysis that genuinely challenges thinking, not just confirms it. It uses a steelman-first approach — argue for the competition before assessing your own position.

## Required inputs

Ask for:
- Your product: name, positioning, key differentiators
- Competitors to analyse with brief descriptions
- Market segment and target ICP
- Current strategic assumptions (what you believe about your competitive position — including what you're unsure about)
- Any available data: pricing pages, feature comparisons, analyst reports, win/loss notes, review site data

---

## Phase 1 — Steelman the Competition

For each competitor, make the strongest possible case for why they will win against you. Argue from their perspective:
- What is their strategic logic?
- What are they doing right?
- Where do they have genuine advantages?

Be direct. Do not be diplomatic.

---

## Phase 2 — Honest Self-Assessment

Based on the steelman arguments:
- Where is your positioning genuinely vulnerable?
- Which of your strategic assumptions are weakest?

---

## Phase 3 — Comparative Framework

Build a comparison matrix across:
- Core value proposition and target ICP
- Product capabilities (features that matter, not feature count)
- Pricing and packaging strategy
- Go-to-market motion and distribution advantages
- Technical moat or switching costs
- Momentum indicators (funding, hiring, product velocity)

---

## Phase 4 — Strategic Implications

- Where should you double down vs. concede?
- What competitive moves should you anticipate in the next 6–12 months?
- Where is there whitespace no competitor is addressing?

---

## Constraints

- If you lack information about a competitor, flag it as `[INSUFFICIENT DATA]` rather than speculating
- Rank competitors by actual competitive overlap with your ICP — not all threats are equal
- Distinguish between competitors' marketing claims and their actual product capabilities where possible
- If your current positioning has a fundamental flaw, say so directly

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-COMPETITIVE.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
