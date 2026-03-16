# PM OS Conductor V2 — Concept

## What this is

A redesign of the PM OS conductor logic. The skills, plugin structure, and distribution model from V1 are unchanged. What changes is the entry point, the organizing principle, and the session continuity mechanism.

V1 conductor: phase-based (`/build` sequences 6 phases)
V2 conductor: opportunity-based (Scope Zero → OST framing → phases)

---

## The problem with V1

The V1 `/build` conductor assumes you already know what you're building and why. It enters directly at Discover and sequences phases. In practice, most sessions don't start with a clear scoped problem — they start with a hunch, an idea, or a vague directive. V1 has no answer for this.

The second problem: V1 optimizes for producing artifacts (PRD, design, code) rather than validating that the artifact is worth producing. Sessions can run all 6 phases and produce nothing usable — proven by the 2026-03-16 session failure (5 artifacts, zero working output).

---

## The organizing principle: Opportunity Framing

Every piece of product work starts with an opportunity. The V2 conductor doesn't ask "which phase are you in?" It asks "do you have a real opportunity, or are we still finding one?"

```
SCOPE ZERO        Gate — is there a real opportunity here?
      ↓
SPECIFY           Gate — what exactly are we solving, for whom?
      ↓
DESIGN            Loop — make → review → refine → approve
      ↓
THREE AMIGOS      Gate — PM + design + build alignment, contract written
      ↓
BUILD             Loop — plan → build → review → approve
      ↓
SHIP              Gate — deploy, communicate, handoff
```

Six moments. Two loops. Four gates.

Gates move in one direction only — you cannot re-enter a previous gate without a conductor-enforced checkpoint. Loops iterate in place until exit conditions are met.

Scope Zero is not a phase — it is an entry condition. You cannot enter Specify without a one-sentence outcome and a framed opportunity. Everything downstream has a validated reason to exist.

---

## Target user

An AI-enabled PM. Comfortable using Claude. Not someone who has memorized 24 skills or manages Claude as a full-time job. They want to describe where they are and get moving — but they want to understand what's happening and approve the next step.

Not: the Claude power user who lives in the terminal.
Not: the non-technical PM who wants a chatbot.
Yes: the senior PM who wants a system that thinks like they do.

---

## Phase principles

### Gates
Linear. One direction. Require explicit human approval to exit. The conductor will not advance past a gate without confirmation.

### Loops
Iterative. Stay in phase until exit condition is met. Design and Build are both loops — this is intentional. Design thinking (think → make → test) and lean build (plan → build → review) are both cyclical by nature.

### The Design → Build boundary
Design changes after Build starts = new Design phase + new Three Amigos checkpoint before any code changes. The conductor enforces this. The Three Amigos gate writes a locked design contract to CLAUDE.md. Build is held against that contract.

### Research fork (in Scope Zero)
When the opportunity is unclear and external signal is needed, the conductor surfaces this explicitly — it does not attempt research inline. It says: "You need a research session before continuing. Run /research as a separate session. Bring the output back here." Session pauses, HANDOFF.md is updated. Research is a different agent, a different session, a different job.

### Design options
Design is always offered, never skipped by default. Three paths:

| Option | When |
|---|---|
| Figma Make | Design quality matters — use figma-make-prompt-generator |
| HTML prototype | Fastest validation — built directly, runs in browser |
| MCP canvas | Claude reads/writes Paper or Figma directly |

Skipping requires an explicit choice, not an absent one.

---

## How Scope Zero works

```
You say anything implying new work
      ↓
Conductor asks one question:
"Do you have a clear outcome and opportunity, or are we still figuring that out?"
      ↓
Fuzzy → Scope Zero activates
  pm-thinking-partner (strategic brain)
  OST skills: ost-exploration, jtbd-analysis, brainstorming-ideation
  Exit condition: one sentence outcome + one framed opportunity
      ↓
Clear → enter at the right phase directly
```

`pm-thinking-partner` is not retired — it becomes the engine of Scope Zero. It is still directly invocable for pure strategic thinking without triggering the full conductor flow.

---

## Session continuity: the three-file pattern

Every project using V2 gets three files written by the conductor:

| File | Written by | Purpose |
|---|---|---|
| `CLAUDE.md` | Conductor (automatic) | Phase state, key decisions, next step — read by Claude at session start |
| `HANDOFF.md` | Conductor (at checkpoints) | Narrative context, decisions and their reasoning — readable by any human |
| `CONCEPT.md` | Human (once) | Strategic framing, vision, why this project exists — rarely updated |

The conductor owns a clearly marked block inside `CLAUDE.md`. Everything outside that block belongs to the human and is never touched.

```
<!-- CONDUCTOR STATE — do not edit manually -->
...
<!-- END CONDUCTOR STATE -->
```

---

## What is not changing from V1

- All 23 skill folders — content unchanged
- Plugin structure (`.claude-plugin/plugin.json`)
- Distribution model (GitHub → `claude plugins install`)
- Direct skill invocation — every skill still triggerable by phrase without going through the conductor
- Landing page — updated to reflect V2 framing, not rebuilt

---

## What "autopilot with control" looks like

| What you say | What happens |
|---|---|
| "I have an idea about X" | Scope Zero runs, conductor frames the opportunity |
| "I want to build Y" | Conductor checks for framed opportunity, routes to Specify if present |
| "Write a PRD for Z" | Lands directly in Specify — no conductor overhead |
| "Start a build" | Conductor runs from current phase |
| "Where are we?" | Conductor reads state, reports phase and next checkpoint |
| "Think through this with me" | pm-thinking-partner activates directly |

---

## What this solves

| Problem | Solution |
|---|---|
| Sessions produce artifacts, not value | Scope Zero gates entry — no phase starts without a validated opportunity |
| Skills feel disconnected | Each phase feeds the next; output of Specify is input to Design |
| "I don't know which skill to invoke" | Describe where you are; conductor routes |
| Context lost between sessions | Conductor writes CLAUDE.md state block; next session resumes from last checkpoint |
| Hard to hand off to a collaborator | HANDOFF.md is narrative, human-readable, shareable |
