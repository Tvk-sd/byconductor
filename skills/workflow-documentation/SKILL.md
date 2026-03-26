---
version: 1.0.0
name: workflow-documentation
description: Documents real-world processes: step-by-step, exception handling, handoffs, review triggers. Captures how it actually works, not how it should. Triggers: "document this process", "write a workflow", "process documentation", "document how this works", "create a process doc", "we need a runbook", "document this procedure", "how do we document our process".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces process documentation that captures real-world complexity — not idealised versions. It surfaces implicit knowledge, flags optimisation opportunities, and includes exception handling.

## Required inputs

Ask for:
- Process name and brief description
- Current state — including the messy reality, not the idealised version
- Key roles involved and their responsibilities
- Tools and systems used
- Known pain points and where the process breaks down

---

## Process Analysis (before writing)

Analyse first:
- Where are the bottlenecks and handoff failures?
- Which steps have implicit knowledge that is not documented?
- Where do exceptions occur most frequently?

---

## Documentation Structure

### 1. Process Overview
- **Purpose**: Why this process exists (not just what it does)
- **Trigger**: What initiates it
- **End state**: How you know it is complete
- **Typical duration and cadence**

### 2. Step-by-Step Workflow

For each step:
- **Action**: What specifically happens
- **Owner**: Who is responsible (role, not name)
- **Input**: What they need to start
- **Output**: What they produce
- **Tool**: Where this happens
- **Decision criteria**: If this step involves a judgment call, specify the criteria

### 3. Exception Handling

Document every exception that has actually caused a breakdown, delay, or confusion. There is no target count — as few or as many as genuinely exist:
- What triggers the exception
- Who owns the resolution
- Escalation path if resolution fails

### 4. Handoff Protocol

For each role transition:
- What information transfers
- What format it should be in
- What the receiving party should verify before proceeding

### 5. Review Triggers
- When should this process be revisited?
- What signals indicate the process is broken?
- Recommended review cadence

---

## Constraints

- Document the process as it ACTUALLY works today. If an aspirational version exists, add it as a separate "Target State" section — never blend the two
- Flag inefficiencies and unnecessary steps with `[OPTIMISATION OPPORTUNITY]`
- Every step must have a clear owner — if ownership is ambiguous, flag it as a problem
- Write for someone new to this process — no assumed knowledge or undefined tribal terminology

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-WORKFLOW.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---

## Gotchas

- **Documenting how it should work instead of how it actually works is the most common failure.** Before writing anything, ask: "Is this how the process works today, or how you want it to work?" If the answer is "how we want it to work", stop — document reality first, then add a Target State section separately.

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
