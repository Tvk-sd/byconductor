---
name: user-story-creation
description: Generate implementation-ready user stories with acceptance criteria, edge cases, and complexity estimates. Use when the user needs to write user stories, acceptance criteria, or break down a feature for engineering. Trigger phrases include: "write user stories", "break this into stories", "acceptance criteria", "story map", "tickets for this feature".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces engineering-ready user stories — not formulaic shells. It forces edge case reasoning before writing acceptance criteria, producing stories QA can test directly.

## Required inputs

Ask the user for:
- Feature name and description or PRD section
- Target user types
- Technical stack or constraints (if known)

---

## Process — for each story

**1. Write the story**
Format: As a [user type], I want [action] so that [outcome]

**2. Reason through edge cases first** (before writing ACs)
- Error and failure states
- Boundary conditions
- Permissions and access controls
- Interactions with existing features

**3. Write acceptance criteria**
Format: Given / When / Then
- Must be specific enough for a QA engineer to write test cases directly
- No ambiguous language ("appropriate", "reasonable")
- Include at least one negative test case (what should NOT happen)

**4. Assign complexity** (S/M/L) with brief justification

**5. List dependencies** on other stories or systems

---

## Grouping and prioritisation

Group stories by user journey phase:
- Discovery → Activation → Core usage → Edge cases

Prioritise each group: Must / Should / Could

---

## Constraints

- Each story must be independently deliverable and testable
- If a story is too large for a single sprint, flag it and suggest how to split
- Do not generate stories for functionality not described — instead, list gaps under "Suggested additions"

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
