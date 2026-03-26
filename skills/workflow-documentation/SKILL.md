---
name: workflow-documentation
description: Create comprehensive, living process documentation that people will actually follow — including exception handling, handoff protocols, and review triggers. Use when the user needs to document a workflow, process, or operational procedure. Trigger phrases include: "document this process", "write a workflow", "process documentation", "how should we document this", "create a runbook".
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

Document the top 5 most common exceptions or edge cases:
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

- Document the process as it SHOULD work, but call out where current reality deviates
- Flag inefficiencies and unnecessary steps with `[OPTIMISATION OPPORTUNITY]`
- Every step must have a clear owner — if ownership is ambiguous, flag it as a problem
- Write for someone new to this process — no assumed knowledge or undefined tribal terminology

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
