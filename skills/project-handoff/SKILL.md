---
name: project-handoff
description: Create or update HANDOFF.md — a living technical state document for any project. Captures what's built, stack, deployment, pending tasks, and update rules. Created at concept stage, updated at every milestone. Use when starting a project, reaching a milestone, onboarding a collaborator, or pausing work. Trigger phrases include: "update handoff", "milestone reached", "project state", "handoff update", "onboard collaborator", "pause project", "update project status".
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
| `[slug]-CONCEPT.md` | ✅ / ❌ |
| `[slug]-PRD.md` | ✅ / ❌ |
| `HANDOFF.md` | ✅ |

---

## What's built
_Nothing yet — updated after first build._

---

## Stack
_Not yet defined._

---

## Deployment
_Not yet deployed._

---

## Pending tasks
| Priority | Task | Notes |
|---|---|---|
| 🔴 | … | … |

---

## Update rules
| Change type | Update this file |
|---|---|
| Strategy / vision / positioning | `[slug]-CONCEPT.md` |
| Feature scope / spec / metrics | `[slug]-PRD.md` |
| Feature shipped / task done / milestone | `HANDOFF.md` |
```

---

## Create mode

When no HANDOFF.md exists, build the skeleton using whatever context is available:

- **Project name** — from CONCEPT.md, PRD.md, or ask
- **Status** — `Planning` if no code exists, `In Progress` if build has started
- **Artifacts** — scan working directory for known files and mark ✅ or ❌
- **What's built** — leave as placeholder if nothing is built yet
- **Stack** — leave as placeholder if not yet defined
- **Deployment** — leave as placeholder if not yet deployed
- **Pending tasks** — derive from PRD open questions, concept brief, or ask the user for the top 3

---

## Update mode

When HANDOFF.md already exists:

1. Read the current file
2. Identify what has changed since last update (ask if unclear)
3. Update only the affected sections:
   - New artifact created → mark ✅ in Artifacts table
   - Build completed → fill in What's built and Stack
   - Deployed → fill in Deployment, set Status to Shipped
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

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
