# Conductor V2 — Handoff

Last updated: 2026-03-17
Status: All six phases drilled ✅ — conductor.md SKILL.md next

---

## What this project is

A redesign of the PM OS conductor logic (V1: `~/Documents/Conductor Plugin`). The skills and plugin infrastructure from V1 are reused. What changes is the entry point (Scope Zero), the organizing principle (OST / opportunity framing), and the session continuity mechanism (three-file pattern).

---

## Decisions made (2026-03-16 session)

| Decision | Detail | Reason |
|---|---|---|
| Scope estimation | Claude estimates and proposes, human approves the cut | Humans are bad at estimation — story points prove it |
| Vertical slices | Every stage must include frontend + backend together | Click-dummy is the minimum testable surface per slice |
| Backlog routing | Simple builds: conductor estimates inline. Complex: route to /plan | Weaves compound-engineering into the flow naturally |
| Fork B language | "Prototype, not a validated product" not "spike" | More natural to PM vocabulary |
| Q3 open prompt | After Q3 in every phase: "Anything else to establish?" | Gives user agency without forcing more questions |
| Phase structure | 6 moments: Scope Zero, Specify, Design, Three Amigos, Build, Ship | Maps to OST + design thinking + lean build |
| Gates vs loops | Gates (4) are linear, Loops (2) iterate in place | Design and Build are inherently cyclical |
| Design is a loop | make → review → refine → approve | Lean UX / design thinking principle |
| Three Amigos gate | Between Design and Build | PM + design + build alignment before code starts |
| Design lock | Changes after Build starts = new Design phase + new checkpoint | Prevents "design in code" drift |
| Research fork | Scope Zero surfaces need, pauses session, routes to /research | Research is a different agent/session, not inline |
| Design options | Figma Make / HTML prototype / MCP canvas — always offered, explicitly skippable | Cheapest to most polished, all valid |
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

## Decisions made (2026-03-17 session)

| Decision | Detail | Reason |
|---|---|---|
| Three Amigos lenses | PM lens / Design lens / Build lens — conductor voices all three | Named perspectives create intentional tempo, not just a checklist |
| Three Amigos agenda | User flow (Mermaid UML) → edge cases → integration checklist → inherited flags → acceptance criteria | Fixed skeleton prevents scope creep; inherits from Specify/Design, doesn't re-litigate |
| Build confidence signal | High / medium / low — low blocks gate, medium advances with flagged risk, high closes gate | Makes the gate meaningful — a readiness judgment, not just a tick |
| Contract change rule | Cosmetic drift = update in place. Structural change = mini Three Amigos checkpoint | Prevents full gate re-run for minor changes while protecting against design drift |
| Later items thread | Written in Specify → HANDOFF.md, signposted at Three Amigos, surfaced at Ship | Three touchpoints so the Ship prompt is never a surprise |
| Build proposal pattern | Claude proposes next unit + states why + offers one alternative. Human decides. | Keeps human as driver, not rubber-stamper |
| Build review questions | R1: does it work, R2: does it match contract / does contract need to change, R3: does it look great | Same R1/R2/R3 pattern as Design for consistency |
| Ship opens with Later items | "Stage 1 shipped. You have N stages parked. What do we do with them?" | Connects back to thread started in Specify |
| Ship delivery type | Asked before anything else runs: deploy / merge / hand off / share+publish | Conductor doesn't assume what "shipped" means |
| Ship paths route to skills | deploy → deploy-checklist, share → stakeholder-communication / launch-planning / draft-content | Conductor routes, skills do the work |
| Merge/deploy boundary | Conductor produces handoff packet, Claude Code executes | Conductor is a PM OS, not a deployment tool |
| technical-handoff | Inline for now, future skill | Not complex enough to warrant a skill file yet |
| Ship memory step | HANDOFF.md update + CLAUDE.md state write are named steps in Ship, not background housekeeping | Makes state persistence visible to the human |
| After Ship | Conductor offers: continue (Specify with Stage 2 pre-loaded) / pause / done. Human confirms. | Conductor never closes session unilaterally |

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

## Phase drill log

### Scope Zero ✅
- Three question sequence (job → signal → outcome) + open prompt
- Research fork lives at Q2: Option A = /research separate session, Option B = proceed as prototype [UNVALIDATED]
- OST skills called conditionally: jtbd-analysis, ost-exploration, ost-evidence, pm-thinking-partner
- Enforcement: one soft check if Scope Zero skipped, respects autonomy but flags it

### Specify ✅
- Three question sequence (user → scope → done) + open prompt
- Scope gate: Claude estimates size, proposes now/next/later staging, human approves the cut
- Vertical slice rule: no stage separates frontend from backend — each slice has a frontend face + backend body + testable surface (click-dummy minimum)
- Complex builds route to compound-engineering:workflows:plan before Design
- Backlog: Stage 1 scope → CLAUDE.md, full now/next/later → HANDOFF.md, backlog file only if Later > 3 items
- Later items written to HANDOFF.md here — first of three touchpoints
- Enforcement: conductor holds at scope gate, proposes the cut, will not advance until a stage is approved

### Design ✅
- Loop: make → review → refine → approve
- Art direction runs before first iteration if visual identity undefined
- Tool selection: A) Interface generator prompt (Figma Make recommended, also Lovable/Bolt/Claude); B) HTML prototype; C) MCP canvas
- figma-make-prompt-generator skill to be generalized later — prompt should work across all AI interface generators
- Three review questions: R1 Coverage, R2 Hard blockers only (soft concerns → Three Amigos agenda), R3 User clarity
- R2 boundary rule: flag only hard blockers, defer everything else to Three Amigos
- Three Amigos agenda built during Design — R2 soft concerns auto-populate it
- Enforcement: known hard blocker = loop runs again, not a Three Amigos question

### Three Amigos ✅
- Three named lenses: PM lens / Design lens / Build lens — conductor voices all three in sequence
- Agenda: user flow (Mermaid UML) → edge cases (table) → integration checklist → inherited feasibility flags → acceptance criteria
- Claude scopes agenda: inherit from Specify/Design, don't re-litigate
- Build confidence signal: high / medium / low — gates advancement
- Contract = one paragraph summary + resolved agenda checklist, written to CLAUDE.md conductor block
- Later items signposted: "Stages 2–N are parked. They will be offered again at Ship." — second of three touchpoints
- Contract change rule: cosmetic = update in place, structural = mini Three Amigos checkpoint
- Enforcement: conductor holds until confidence is medium or high; one soft challenge if skipped

### Build ✅
- Loop: plan → build → review → approve
- Unit of work = one feature within a stage
- Claude proposes next unit + states why + offers one alternative. Human decides.
- Three review questions: R1 does it work, R2 does it match contract / does contract need to change, R3 does it look great
- Contract change rule same as Three Amigos: cosmetic = in place, structural = mini checkpoint
- Exit: both Claude and human call Stage 1 complete when acceptance criteria met
- Later items do NOT surface during Build — Build is Stage 1 only

### Ship ✅
- Opens with Later items prompt: "Stage 1 shipped. You have N stages parked. What do we do with them?" — third of three touchpoints
- Delivery type question before anything else: deploy to production / merge to main / hand off to developer / share or publish
- Each path routes to existing skills where possible
- Merge/deploy paths produce a handoff packet for Claude Code — conductor does not execute
- Named steps before session close: path-specific actions → HANDOFF.md update → CLAUDE.md state write → continue/pause/done
- After Ship: conductor offers continue (Specify with Stage 2 pre-loaded) / pause / done. Human confirms.

---

## Skill resolution map

Mapped against `commands/conductor.md` — 2026-03-17.

| Skill | Status | Where |
|---|---|---|
| `jtbd-analysis` | Triggered | Scope Zero — fuzzy job |
| `ost-exploration` | Triggered | Scope Zero — no signal |
| `ost-evidence` | Triggered | Scope Zero — signal exists |
| `pm-thinking-partner` | Triggered | Scope Zero — strategic framing |
| `art-direction` | Triggered | Design — visual identity undefined |
| `figma-make-prompt-generator` | Triggered | Design — Path A |
| `stakeholder-communication` | Triggered | Ship — Path D |
| `launch-planning` | Triggered | Ship — Path D |
| `engineering:deploy-checklist` | Triggered | Ship — Path A |
| `draft-content` | Triggered (marketing plugin) | Ship — Path D |
| `compound-engineering:workflows:plan` | Triggered | Specify — complex builds |
| `prd-writing` | Standalone only — decision pending | Was in V1 Specify — replaced by conductor questions |
| `concept-brief` | Standalone only — decision pending | Was in V1 Specify — replaced by CONCEPT.md |
| `metrics-definition` | Standalone only — decision pending | Was in V1 Specify |
| `user-story-creation` | Standalone only — decision pending | Possible fit in Three Amigos |
| `project-handoff` | Standalone only — decision pending | Replaced by three-file pattern |
| `ui-ux-pro-max` | Standalone only — decision pending | Was in V1 Design |
| `workflow-documentation` | Standalone only — decision pending | Possible Ship Path C |
| `brainstorming-ideation` | Standalone only | No conductor fit identified |
| `feature-prioritisation` | Standalone only | No conductor fit identified |
| `competitor-analysis` | Standalone only | No conductor fit identified |
| `ai-decision-framework` | Standalone only | No conductor fit identified |
| `ai-feature-scoping` | Standalone only | No conductor fit identified |
| `ai-market-research` | Standalone only | No conductor fit identified |
| `build-workflow` | Superseded | Replaced by conductor |
| `user-research-synthesis` | Standalone only | No conductor fit identified |

**Pending decisions (next session):**
- `prd-writing` / `concept-brief` / `metrics-definition` — trigger anywhere in V2 or standalone-only?
- `user-story-creation` — trigger in Three Amigos UML step, or too much overlap?
- `ui-ux-pro-max` — trigger in Design, or retired from conductor?
- `project-handoff` — fully replaced by three-file pattern, or still useful standalone?

---

## Where we stopped

All six phases drilled. `commands/conductor.md` written. Skill resolution map complete — 4 decisions pending.

## How to resume

Start a new Claude Code session from `~/Documents/Conductor V2/`.
Say: "Resume Conductor V2 design session. Read HANDOFF.md and CONCEPT.md."
Next: resolve the 4 pending skill decisions (see Skill resolution map above).

After skill decisions: update `CLAUDE.md` V2 trigger phrases and routing logic, then V1 landing page decision.

---

## Open questions

- `/research` from V1 confirmed as separate session/agent — survives as-is, referenced from Scope Zero fork
- V1 landing page: update in place or wait until V2 conductor is built?
- CTA decision still pending from V1: Tally waitlist / GitHub / email?
- technical-handoff: future skill, not blocking V2
- figma-make-prompt-generator: generalize for all AI interface generators (future)
