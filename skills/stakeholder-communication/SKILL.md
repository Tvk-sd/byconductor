---
version: 1.0.0
name: stakeholder-communication
description: BLUF-format stakeholder updates, status reports, exec comms — audience-adapted, never softens bad news. Triggers: "write a stakeholder update", "draft a status update", "exec communication", "write an update for leadership", "communicate this to the team", "board update", "status email", "cross-functional update", "how do I tell stakeholders about this".
---

**Before starting:** present a brief work plan — what you will do and in what order — plus any clarifying questions, and wait for confirmation before proceeding.

This skill produces crisp, audience-adapted communications that lead with the most important thing and don't bury bad news.

---

## Config

!`cat ${CLAUDE_SKILL_DIR}/config.json 2>/dev/null || echo "NOT_CONFIGURED"`

If the output above is `NOT_CONFIGURED`, ask the user:

1. **Regular audiences** — who do you typically communicate with? List each group with 1–2 words on what they care about most. (e.g. "exec team: revenue + timeline", "engineering: technical risk", "board: strategic risk + burn")
2. **Default channel** — where do these updates usually go? (email / Slack / Notion / other)
3. **Tone constraints** — anything to always avoid? (e.g. "no sprint/velocity/backlog for exec audience", "always use first name not title")

Then write answers to `${CLAUDE_SKILL_DIR}/config.json`:
```json
{
  "audiences": [
    { "name": "exec", "priority": "revenue and timeline", "jargon_free": true },
    { "name": "engineering", "priority": "technical risk and scope" }
  ],
  "default_channel": "email",
  "tone_constraints": []
}
```

If configured, use these audience profiles as defaults when the user doesn't specify. Pre-fill the audience analysis section without asking. Do not ask again.

---

## Required inputs

Ask for:
- What happened (key developments, decisions, milestones)
- Current status — including problems
- Key metrics and trends
- Decisions needed from stakeholders
- Audience — if not already set in config

---

## Process

### Audience Analysis (before writing)
Reason through:
- What does this audience care most about? (Revenue? Timeline? Technical risk? Customer impact?)
- What is the ONE thing they need to take away?
- What concerns will they have that should be addressed preemptively?
- What action is needed from them, if any?

### Update structure

1. **BLUF** — Bottom Line Up Front: one sentence, most important takeaway
2. **Key metrics** — 2–3 data points maximum
3. **On track / at risk** — be specific ("2-week delay on auth integration due to API partner dependency" not "timeline risk")
4. **Decisions needed** — with clear deadlines and owners
5. **What's next** — upcoming milestones with dates

If multiple audiences are specified, create separate versions tailored to each group's priorities and vocabulary. Maintain factual consistency; adjust emphasis and framing.

---

## Constraints

- Maximum 300 words per audience version
- No burying bad news — lead with risks if they are the most important development
- No PM jargon for non-PM audiences (no "velocity", "sprint", "backlog" for execs)
- Every risk mentioned must include a mitigation plan or explicit ask for help
- Do not soften language on blockers — executives respect directness over optimism

---

## File output

After producing the final output, save it as a markdown file in the current working directory:

```
Filename: [project-slug]-STAKEHOLDER-UPDATE.md
```

If no project slug is evident from context, ask the user for one before saving. Confirm the save with: `Saved: [filename]`

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
