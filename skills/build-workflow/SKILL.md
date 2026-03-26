---
name: build-workflow
description: Human-in-the-loop build workflow for PMs using Claude Code. Maps every phase (Discover → Specify → Design → Build → Review → Ship) to the right skills, MCPs, and agent patterns. Includes parallel agent setup for building multiple features simultaneously. Trigger phrases: "how do I build this", "start a build", "what skill should I use", "parallel build", "run agents in parallel".
---

# Human-in-the-Loop Build Workflow

A complete map of skills, MCPs, and agent patterns for building products with Claude Code — with you as the decision-maker at every handoff.

---

## The Build Loop

```mermaid
flowchart TD
    START([New idea or problem]) --> D

    subgraph D [1. DISCOVER]
        D1["&quot;think through this with me&quot;\npm-thinking-partner"]
        D2["&quot;what job are we hired for&quot;\njtbd-analysis"]
        D3["&quot;explore the opportunity space&quot;\nost-exploration"]
        D4["&quot;brainstorm ideas for&quot;\nbrainstorming-ideation"]
        D1 --- D2 --- D3 --- D4
    end

    D --> CP1{{"YOUR CHECKPOINT\nAgree on the problem"}}
    CP1 -->|approved| S

    subgraph S [2. SPECIFY]
        S1["&quot;write a PRD for&quot;\nprd-writing"]
        S2["&quot;write user stories for&quot;\nuser-story-creation"]
        S3["&quot;define success metrics for&quot;\nmetrics-definition"]
        S4["&quot;prioritise these features&quot;\nfeature-prioritisation"]
        S1 --- S2 --- S3 --- S4
    end

    S --> CP2{{"YOUR CHECKPOINT\nApprove PRD + metrics"}}
    CP2 -->|approved| DE

    subgraph DE [3. DESIGN]
        DE1["&quot;art direct this&quot;\nart-direction"]
        DE2["&quot;design a dashboard / landing page&quot;\nui-ux-pro-max"]
        DE3["Paper MCP — Claude reads & writes canvas"]
        DE4["Figma MCP — Claude reads Figma designs"]
        DE1 --- DE2 --- DE3 --- DE4
    end

    DE --> CP3{{"YOUR CHECKPOINT\nApprove design in Paper"}}
    CP3 -->|approved| B

    subgraph B [4. BUILD]
        B1["&quot;plan this feature&quot;\ncompound-engineering:workflows:plan"]
        B2["&quot;execute this plan&quot;\ncompound-engineering:workflows:work"]
        B3["21st.dev Magic MCP — polished components"]
        B4["Context7 MCP — live library docs"]
        B1 --> CP4{{"Approve build plan"}}
        CP4 -->|approved| B2
        B2 --- B3 --- B4
    end

    B --> CP5{{"YOUR CHECKPOINT\nReview each feature"}}
    CP5 -->|approved| R
    CP5 -->|changes needed| B

    subgraph R [5. REVIEW]
        R1["&quot;review this code&quot;\nengineering:review"]
        R2["&quot;critique this design&quot;\ndesign:critique"]
        R3["&quot;accessibility audit&quot;\ndesign:accessibility"]
        R1 --- R2 --- R3
    end

    R --> CP6{{"YOUR CHECKPOINT\nSign off on quality"}}
    CP6 -->|approved| SH
    CP6 -->|issues found| B

    subgraph SH [6. SHIP]
        SH1["&quot;plan this launch&quot;\nlaunch-planning"]
        SH2["&quot;deploy checklist&quot;\nengineering:deploy-checklist"]
        SH3["&quot;stakeholder update&quot;\nstakeholder-communication"]
        SH1 --- SH2 --- SH3
    end

    SH --> CP7{{"Final go/no-go"}}
    CP7 -->|ship it| END([Shipped])
    CP7 -->|not yet| R

    subgraph PARALLEL [PARALLEL BUILDS]
        P1["&quot;create a worktree for feature X&quot;\ncompound-engineering:git-worktree"]
        P2["Open separate Claude terminal per feature"]
        P3["Each agent works on its own branch"]
        P4["Merge only approved branches"]
        P1 --> P2 --> P3 --> P4
    end

    style CP1 fill:#f5a623,color:#000
    style CP2 fill:#f5a623,color:#000
    style CP3 fill:#f5a623,color:#000
    style CP4 fill:#f5a623,color:#000
    style CP5 fill:#f5a623,color:#000
    style CP6 fill:#f5a623,color:#000
    style CP7 fill:#f5a623,color:#000
    style PARALLEL fill:#e8f4fd,stroke:#2196F3
```

Each phase ends with a human checkpoint (🟠). Claude presents output. You approve before the next phase begins.

---

## Phase Map

### 1. Discover
**Goal:** Agree on the problem before anything is written.

| Tool | Trigger |
|---|---|
| `pm-thinking-partner` | "think through this with me: [idea]" |
| `jtbd-analysis` | "what job are we hired for" |
| `ost-exploration` | "explore the opportunity space" |
| `brainstorming-ideation` | "brainstorm ideas for" |
| Granola MCP | Pull context from meeting notes automatically |
| Notion MCP | Capture output to Notion |

→ **Your checkpoint:** Agree on the problem and target outcome.

---

### 2. Specify
**Goal:** A clear PRD and success metrics before any design or code.

| Tool | Trigger |
|---|---|
| `prd-writing` | "write a PRD for" |
| `user-story-creation` | "write user stories for" |
| `feature-prioritisation` | "prioritise these features" |
| `metrics-definition` | "define success metrics for" |
| `ai-feature-scoping` | "scope this AI feature" |
| Notion MCP | Store spec in Notion |

→ **Your checkpoint:** Approve the PRD and metrics. Do not proceed to design without this.

---

### 3. Design
**Goal:** A visual design in Paper that Claude can read and convert to code.

| Tool | Trigger |
|---|---|
| `art-direction` | "art direct this" / "visual identity for" |
| `ui-ux-pro-max` | "build a landing page" / "design a dashboard" |
| `figma-make-prompt-generator` | "generate a Figma Make prompt" |
| Paper MCP | Claude reads/writes your Paper canvas directly |
| Figma MCP | Claude reads Figma designs |

→ **Your checkpoint:** Approve the design in Paper before Claude writes code.

---

### 4. Build
**Goal:** Production-ready code from your approved design.

| Tool | Trigger |
|---|---|
| `compound-engineering:workflows:plan` | "plan this feature" |
| `compound-engineering:workflows:work` | "execute this plan" |
| `feature-dev:feature-dev` | "build this feature" |
| Paper MCP | Claude reads your canvas as build context |
| Context7 MCP | Live library docs — always active |
| 21st.dev Magic MCP | Fetches polished UI components on demand |

→ **Your checkpoints:** Approve the build plan first. Review after each discrete feature. Never batch.

---

### 5. Review
**Goal:** Catch quality, accessibility, and correctness issues before shipping.

| Tool | Trigger |
|---|---|
| `engineering:review` | "review this code" |
| `design:critique` | "critique this design" |
| `design:accessibility` | "accessibility audit" |
| `compound-engineering:workflows:review` | Deep multi-agent code review |

→ **Your checkpoint:** Sign off before launch prep begins.

---

### 6. Ship
**Goal:** A clean launch with stakeholders informed.

| Tool | Trigger |
|---|---|
| `launch-planning` | "plan this launch" |
| `engineering:deploy-checklist` | "deploy checklist" |
| `stakeholder-communication` | "stakeholder update" |
| Notion MCP | Publish update or launch doc |

→ **Your checkpoint:** Final go/no-go.

---

## Parallel Builds — Running Multiple Features at Once

Use git worktrees to give each feature its own isolated copy of the repo. Claude agents run independently in each worktree so they never conflict.

### Setup (one time per project)
```bash
# Ensure your project has git
git init && git add . && git commit -m "initial"
```

### Start a parallel feature build
```bash
# Create isolated worktree for each feature
git worktree add ../project-feature-a -b feature/feature-a
git worktree add ../project-feature-b -b feature/feature-b
```

Then open Claude Code in each directory:
```bash
cd ../project-feature-a && claude   # Agent 1
cd ../project-feature-b && claude   # Agent 2
```

Each agent has its own context, its own branch, and cannot interfere with the other.

### Merge when approved
```bash
# Review each branch independently, then merge
git checkout main
git merge feature/feature-a
git merge feature/feature-b
git worktree remove ../project-feature-a
git worktree remove ../project-feature-b
```

Use the `compound-engineering:git-worktree` skill to manage this:
> "create a worktree for feature X"

---

## The Human-in-the-Loop Rule

> You are the decision-maker at every phase boundary. Claude executes — you steer.

The two highest-value checkpoints:
1. **Spec approval** — prevents building the wrong thing entirely
2. **Design approval in Paper** — prevents expensive code rework

Never let Claude move from design to build, or from plan to code, without explicit confirmation from you.

---

## Progressive Updates

Claude will confirm which phase is active at the start of each session and suggest the next appropriate skill or action. If you are mid-build, Claude will resume from the last approved checkpoint.
