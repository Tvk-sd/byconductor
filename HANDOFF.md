# Conductor V2 — Handoff

Last updated: 2026-03-17
Status: Drilling phases — Scope Zero ✅ Specify ✅ Design ✅ Three Amigos next

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
- Enforcement: conductor holds at scope gate, proposes the cut, will not advance until a stage is approved

### Design ✅
- Loop: make → review → refine → approve
- Art direction runs before first iteration if visual identity undefined
- Tool selection: A) Interface generator prompt (Figma Make recommended, also Lovable/Bolt/Claude) — best speed/quality ratio, fine-tune directly, push to GitHub; B) HTML prototype — runs locally in browser/Cursor, use for quick validation or backend-heavy work; C) MCP canvas — real-time canvas editing, requires canvas open before starting
- figma-make-prompt-generator skill to be generalized later — prompt should work across all AI interface generators
- Three review questions: R1 Coverage, R2 Hard blockers only (feasibility debates deferred to Three Amigos), R3 User clarity
- R2 boundary rule: "flag only hard blockers, defer everything else to Three Amigos" — conductor enforces this explicitly
- Three Amigos agenda built during Design — R2 soft concerns go on it automatically
- Enforcement: known hard blocker = loop runs again, not a Three Amigos question

### Three Amigos ⬅ next

## Where we stopped

Design drilled and locked. Session ended here due to context length.

## How to resume

Start a new Claude Code session from `~/Documents/Conductor V2/`.
Say: "Resume Conductor V2 design session. Read HANDOFF.md and CONCEPT.md."
Next phase to drill: Three Amigos gate.

After Three Amigos: Build loop, Ship gate.
Then: write conductor SKILL.md, review individual skill files, resolve embedded vs triggered vs referenced.

---

## Open questions

- `/research` from V1 confirmed as separate session/agent — survives as-is, referenced from Scope Zero fork
- Design confirmed as always-offered, explicitly skippable — three options: Figma Make / HTML / MCP canvas
- V1 landing page: update in place or wait until V2 conductor is built?
- CTA decision still pending from V1: Tally waitlist / GitHub / email?
