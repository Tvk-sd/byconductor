# Conductor

A PM operating system for Claude Code. Install once, get 23 PM skills and three conductor workflows — `/conductor`, `/build`, and `/research` — ready to use immediately.

Built for senior PMs and technical builders who want a system, not just prompts.

---

## What's inside

**3 Conductors** — structured multi-phase workflows with checkpoints:
- `/conductor` — opportunity-first: Scope Zero → Specify → Design → Three Amigos → Build → Ship
- `/build` — phase-based: Discover → Specify → Design → Build → Review → Ship
- `/research` — frames a question, investigates it thoroughly, delivers a recommendation

**23 Skills** — triggered by natural language phrases:

| Category | Skills |
|---|---|
| Strategy | Concept brief, JTBD analysis, OST (evidence + exploration), AI decision framework |
| Specification | PRD writing, user stories, feature prioritisation, metrics definition, AI feature scoping |
| Research | User research synthesis, competitor analysis, AI market research |
| Execution | Launch planning, workflow documentation, project handoff, build workflow, stakeholder communication |
| Design | UI/UX direction, art direction, Figma Make prompt generator |
| AI | PM thinking partner, brainstorming |

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

Run a conductor:
```
/conductor a user onboarding flow for a B2B SaaS product
/build a user onboarding flow for a B2B SaaS product
/research whether we should build or buy our auth system
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
├── commands/     Conductor scripts (/conductor, /build, /research)
├── skills/       23 PM skill folders
└── CLAUDE.md     Plugin manifest — loaded by Claude Code on install
```

---

## License

MIT — use it, fork it, build on it.
