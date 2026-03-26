---
version: 1.0.0
name: prd-writing
description: Two-phase PRD: strategic challenge first, then structured draft. Flags assumptions and missing input inline. Triggers: "write a PRD", "help me draft a spec", "product requirements", "feature brief", "write up this feature", "write a product spec", "I need a PRD for", "spec this out", "document this feature".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces implementation-ready PRDs through a two-phase process. Phase 1 surfaces critical questions before any drafting begins. Phase 2 produces a structured document with explicit assumption and input markers.

## Required inputs

Ask the user for:
- Company/product context and target users
- Feature or initiative name
- Rough notes or thinking so far
- Their PRD template (always prefer their actual template over a default)

---

## Phase 1 — Strategic Challenge

Before drafting anything, identify the 5 most critical questions the user must answer for the PRD to be strong. For each:
- Explain why it matters
- Flag assumptions in their brief that need validation
- Suggest how to answer it (data source, stakeholder, experiment)

Ask these questions and **wait for responses** before proceeding to Phase 2.

---

## Phase 2 — Structured Draft

Draft the PRD using the user's template. If none provided, use:

1. Problem Statement
2. Goals & Success Metrics
3. User Stories
4. Scope (In / Out)
5. Solution Design
6. Technical Considerations
7. Risks & Mitigations
8. Launch Plan
9. Open Questions

For each section:
- Write substantive content, not placeholders
- Flag assumptions: `[ASSUMPTION: reason]`
- Flag input needed: `[NEEDS INPUT: who and why]`
- Metrics must be quantifiable with a named measurement method

---

## Constraints

- If the problem statement is unclear or solution is premature, say so directly
- Scope must list what's OUT explicitly, not just what's in
- Never fill generic content when context is missing — tell the user what's needed
- Every risk needs a mitigation or explicit ask for help

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-PRD.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
