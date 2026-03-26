---
version: 1.0.0
name: brainstorming-ideation
description: Diverge-then-converge ideation — genuine novelty, not obvious lists. Triggers: "brainstorm ideas", "help me ideate", "what could we try", "generate ideas for", "I need ideas", "creative solutions", "explore the problem space", "what are our options", "let's brainstorm".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill uses a diverge-then-converge structure with forced perspective shifts and a challenge round to produce genuinely novel ideas rather than obvious lists.

## Required inputs

Ask for:
- Problem to solve (clear problem statement)
- Who it affects (user segments and context)
- Why existing solutions fall short
- Constraints (budget, timeline, technical, regulatory)
- Ideas already considered (so they are not repeated)

---

## Phase 1 — Reframe the Problem (3 ways)

Before generating solutions, restate the problem from three angles:
- **Emotional framing**: "I feel..." (user's emotional experience)
- **10x version**: What if this problem were 10 times worse?
- **Adjacent domain analog**: What industry has solved something similar, and how?

This often unlocks solution spaces that direct brainstorming misses.

---

## Phase 2 — Divergent Ideation

Generate ideas across these categories (no fixed count — go as deep as the problem warrants):
- **Incremental**: Improve what exists (low risk, fast)
- **Adjacent**: Apply approaches from other domains
- **Transformative**: Fundamentally change the paradigm
- **Subtractive**: What if you REMOVED something instead of adding?
- **Constraint-flipping**: What if the biggest constraint didn't exist?

For each idea: one sentence describing it, one sentence on why it could work.

---

## Phase 3 — Challenge the Best

Select the 5 most promising ideas. For each:
- Make the strongest argument AGAINST it
- Identify the riskiest assumption it depends on
- Describe who would hate this idea and why

---

## Phase 4 — Refined Shortlist

Present the top 3 recommendations:
- Why it survived the challenge round
- Rough feasibility given stated constraints
- Suggested first step to validate (under 1 week)

---

## Constraints

- Do not include ideas already listed as "considered" unless you have a genuinely different angle
- Every "transformative" idea must have a plausible path from here to there — no innovation theatre
- If the problem statement itself is flawed, say so before brainstorming solutions to the wrong problem

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-IDEATION.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---

## Gotchas

- **The obvious idea will be in the list — make it visible.** The solution everyone is already thinking about needs to appear and be explicitly labelled as "the default path." This lets it be consciously chosen or rejected, instead of sneaking in through the back door.

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
