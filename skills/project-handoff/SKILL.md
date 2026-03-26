---
version: 1.0.0
name: project-handoff
description: Creates or updates HANDOFF.md — living technical state for the current project. Triggers: "update handoff", "project state", "handoff update", "milestone reached", "onboard a collaborator", "pause this project", "update project status", "what's the state of this project", "document what's been built".
---

Detect whether `HANDOFF.md` exists in the working directory:
- **Not found → Create mode:** build a skeleton from available context
- **Found → Update mode:** read the file, update only what changed, preserve everything else

Never overwrite sections that haven't changed. Never truncate existing content.

---

## HANDOFF.md template

```markdown
# [Project name] — Handoff
Last updated: [date] · Status: [Planning | In Progress | Shipped]

---

## Artifacts
| File | Status |
|---|---|
| `[slug]-CONCEPT.md` | yes / no |
| `[slug]-PRD.md` | yes / no |
| `HANDOFF.md` | yes |

---

## Where to look
| Topic | Source |
|---|---|
| Stack & conventions | `CLAUDE.md` |
| Deploy history | git log / changelog |

---

## What's built
_Nothing yet — updated after first build._

---

## Pending tasks
| Priority | Task | Notes |
|---|---|---|
| high | … | … |

---

## Update rules
| Change type | Update this file |
|---|---|
| Strategy / vision / positioning | `[slug]-CONCEPT.md` |
| Feature scope / spec / metrics | `[slug]-PRD.md` |
| Stack or conventions | `CLAUDE.md` |
| Deploy history | git log / changelog |
| Feature shipped / task done / milestone | `HANDOFF.md` |
```

---

## Create mode

When no HANDOFF.md exists, build the skeleton using whatever context is available:

- **Project name** — from CONCEPT.md, PRD.md, or ask
- **Status** — `Planning` if no code exists, `In Progress` if build has started
- **Artifacts** — scan working directory for known files and mark yes or no
- **What's built** — leave as placeholder if nothing is built yet
- **Pending tasks** — derive from PRD open questions, concept brief, or ask the user for the top 3

---

## Update mode

When HANDOFF.md already exists:

1. Read the current file
2. Identify what has changed since last update (ask if unclear)
3. Update only the affected sections:
   - New artifact created → mark yes in Artifacts table
   - Build completed → fill in What's built
   - Status change → update Planning / In Progress / Shipped
   - Task completed → mark done or remove from Pending tasks
   - New task identified → add to Pending tasks
4. Update the `Last updated` date
5. Leave everything else untouched

---

## File output

Save as `HANDOFF.md` in the current working directory.

Confirm save with: `Updated: HANDOFF.md`

Display the full file inline after saving.

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
