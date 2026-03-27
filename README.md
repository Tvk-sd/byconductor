# Conductor

A PM operating system for Claude Code. Validate the opportunity first, then design, then build.

Built for senior PMs who want a system that thinks like they do — not a chatbot, not a terminal tool.

---

## The problem

AI-assisted product work drifts. Sessions produce conversation, documents, and artifacts — but no forward movement. The opportunity never gets validated. Skills feel disconnected. Context disappears between sessions. You ship a PRD nobody reads because the problem wasn't worth solving in the first place.

This is session drift. It happens because most AI tools optimise for output, not progress.

## The goal

Eliminate session drift. Every session starts with a validated opportunity, advances through explicit gates, and ends with a committed next step or a shipped output. If it doesn't — Conductor failed.

## How it works

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

Gates move in one direction — you cannot re-enter a previous gate without a checkpoint. Loops iterate until exit conditions are met.

**Scope Zero is not a phase — it is an entry condition.** You cannot enter Specify without a one-sentence outcome and a framed opportunity. Everything downstream has a validated reason to exist.

---

## Usage

Run the conductor:
```
/conductor a user onboarding flow for a B2B SaaS product
```

What you see:
```
Conductor session: User onboarding flow

Path I'll run:
  1. Scope Zero    — frame the opportunity
  2. Specify       — scope, slices, staging
  3. Design        — prototype or mockup
  4. Three Amigos  — alignment before code
  5. Build         — feature by feature
  6. Ship          — deliver and handoff

Any phases to skip? Or shall I start?
```

Trigger a skill by phrase:
```
Write a PRD for the notifications feature
Prioritise this backlog using RICE scoring
Think through this with me — I'm trying to decide if we should...
```

---

## 23 Skills

| Conductor phase | Skills |
|---|---|
| Scope Zero | Concept brief, JTBD analysis, OST (evidence + exploration), AI decision framework, PM thinking partner, Competitor analysis, AI market research, Brainstorming |
| Specify | PRD writing, User stories, Metrics definition, Feature prioritisation, AI feature scoping |
| Design | UI/UX direction, Art direction, Figma Make prompt generator |
| Three Amigos | Stakeholder communication, Workflow documentation |
| Build | Build workflow |
| Ship | Launch planning, Project handoff |

All 23 skills are also directly invocable by phrase — no conductor overhead required.

---

## vs other frameworks

| | GSD | BMAD | Superpowers | Conductor |
|---|---|---|---|---|
| **Core philosophy** | Ship fast, learn from output | Document everything upfront, then build | Test-first, edge-case extraction | Validate the opportunity first, then design, then build |
| **Entry point** | Idea → MVP immediately | Idea → documentation → build | Idea → test suite → build | Idea → opportunity framing → everything else |
| **Planning rigidity** | Low — requirements evolve | High upfront, rigid after | Rigid via test definitions | Gate-rigid, loop-flexible |
| **Design phase** | None | Captured in docs | None | Dedicated loop + Three Amigos gate |
| **Human role** | Sets direction, approves output | Owns docs, delegates build | Confirms edge cases | Drives every loop — Claude proposes, human decides |
| **PM fit** | Moderate | Low — assumes dev literacy | Low — test-oriented | Native — designed for PMs |
| **Best for** | Unproven ideas, MVPs | Stable systems, known requirements | High-stakes agentic actions | PM-led work with fuzzy starting points |

### When to choose which

| Situation | Best fit |
|---|---|
| Scratching your own itch, speed matters | GSD |
| Known requirements, stable system, regulated context | BMAD |
| High-stakes action where edge cases must be exhaustive | Superpowers (or Conductor + Superpowers in Build) |
| Fuzzy idea, PM-led, need to validate before building | Conductor |
| Building for users who aren't you | Conductor — Scope Zero earns its cost |
| Team already owns the design, just needs to build | Conductor skip:design or BMAD |
| Agentic action with real-world side effects | Superpowers |

The underlying pattern: these frameworks differ most in where they put the validation cost. GSD defers it entirely. BMAD pays it upfront in documentation. Superpowers pays it in test definitions. Conductor pays it in gates — progressively, at the moments when it's cheapest to change course.

---

## Install

```bash
claude plugins install --url https://github.com/Tvk-sd/byconductor
```

Restart Claude Code. Type `/conductor` to start.

**Requirements:** Claude Code (any recent version) + Claude API subscription or Anthropic API key.

---

## Repository structure

```
byconductor/
├── commands/     Conductor script (/conductor)
├── skills/       23 PM skill folders
└── CLAUDE.md     Plugin manifest — loaded by Claude Code on install
```

---

## License

MIT — use it, fork it, build on it.
