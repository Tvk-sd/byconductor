# Conductor

A PM operating system for Claude Code. Install once, get 23 PM skills and the `/conductor` workflow — ready to use immediately.

Built for senior PMs and technical builders who want a system, not just prompts.

---

## What's inside

**1 Conductor** — a structured multi-phase workflow with checkpoints:
- `/conductor` — Scope Zero → Specify → Design → Three Amigos → Build → Ship

**23 Skills** — triggered by natural language phrases:

| Conductor phase | Skills |
|---|---|
| Scope Zero | Concept brief, JTBD analysis, OST (evidence + exploration), AI decision framework, PM thinking partner, Competitor analysis, AI market research, Brainstorming |
| Specify | PRD writing, User stories, Metrics definition, Feature prioritisation, AI feature scoping |
| Design | UI/UX direction, Art direction, Figma Make prompt generator |
| Three Amigos | Stakeholder communication, Workflow documentation |
| Build | Build workflow |
| Ship | Launch planning, Project handoff |

---

## Install

```bash
claude plugins install --url https://github.com/Tvk-sd/byconductor
```

Restart Claude Code. Type `/conductor` to start.

---

## Requirements

- Claude Code (any recent version)
- A Claude API subscription or Anthropic API key

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
