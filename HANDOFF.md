# Conductor V2 — Handoff

Last updated: 2026-03-16
Status: Design phase — phase structure next

---

## What this project is

A redesign of the PM OS conductor logic (V1: `~/Documents/Conductor Plugin`). The skills and plugin infrastructure from V1 are reused. What changes is the entry point (Scope Zero), the organizing principle (OST / opportunity framing), and the session continuity mechanism (three-file pattern).

---

## Decisions made (2026-03-16 session)

| Decision | Detail | Reason |
|---|---|---|
| Plugin structure | Keep V1 plugin structure | Works, no reason to change |
| Skills | All 23 unchanged | Leaf skills are working as designed |
| Entry point | Scope Zero replaces direct phase entry | V1 assumes a scoped problem; most sessions start fuzzy |
| Organizing principle | OST (outcome → opportunity → solution → build) | Natural to PM thinking; maps to existing OST skills |
| pm-thinking-partner | Stays, becomes engine of Scope Zero | Not retired — given a defined home |
| State mechanism | CLAUDE.md conductor block (auto-written) | Existing infrastructure, human-readable, session-portable |
| Human handoff | HANDOFF.md written at checkpoints | Narrative context for collaborators and future sessions |
| Strategic framing | CONCEPT.md written once by human | Separates vision from operational state |
| Repo location | `~/Documents/Conductor V2/` | Separate from live setup; git-controlled before install |

---

## What exists in V1 (do not rebuild)

Location: `~/Documents/Conductor Plugin/`

- 23 skill folders with full SKILL.md content
- `.claude-plugin/plugin.json`
- `commands/build.md` — current conductor (to be replaced)
- `commands/research.md` — current research conductor (review for V2 fit)
- `CLAUDE.md`, `README.md`, `SETUP.md`
- Landing page (`site/index.html` + Vite/React version in `Figma Make code/`)
- Git initialized, not yet committed or pushed

---

## What V2 adds

- `commands/conductor.md` — new OST-based main conductor replacing `build.md`
- `commands/scope-zero.md` — entry condition phase (optional standalone)
- Three-file pattern written to project directories at checkpoints
- Updated `CLAUDE.md` with V2 trigger phrases and routing logic

---

## Where we stopped

Designed the concept. Next: map the phase structure.

Specifically:
1. Exact phases and their exit conditions
2. Which skills each phase calls and in what order
3. What the human checkpoint looks like per phase
4. What the conductor writes to CLAUDE.md and HANDOFF.md at each boundary

---

## Open questions

- Does the `/research` conductor from V1 survive as-is, or get folded into Scope Zero?
- Does Design phase remain mandatory or become optional (e.g. for non-UI work)?
- V1 landing page: update in place or wait until V2 conductor is built?
- CTA decision still pending from V1: Tally waitlist / GitHub / email?
