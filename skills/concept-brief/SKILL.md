---
version: 1.1.0
name: concept-brief
description: Writes a voice-forward concept brief (~300 words): what it is, what it believes, who it's for. Saves as CONCEPT.md. Reads ARTDIRECTION.md if present. Use before PRD or build. Triggers: "concept brief", "write a concept brief", "vision brief", "direction brief", "write up the vision", "project brief", "what is this thing", "summarise the vision", "capture the concept".
---

**Before starting:** state your understanding of the project in one sentence and ask up to 2 clarifying questions if the input is ambiguous. Wait for confirmation before drafting.

This skill produces a single `CONCEPT.md` — a brief, opinionated document that gives any reader (human or AI collaborator) a clear sense of what the project is, what it believes, and where it's going. It is not a PRD. It is the document you read before the PRD.

---

## What this produces

A saved file: `[project-slug]-CONCEPT.md` in the current working directory.

Content: ~300 words. No tables. Short paragraphs. Strong voice. Something you could share with a designer, a developer, a stakeholder, or an AI — and all of them would immediately understand what they're working on and why.

---

## Required inputs

Ask for (if not already provided):
- Project name
- One-sentence description of what it does
- Who it's for (be specific — not "users", a real person in a real situation)
- The central problem it solves
- Any notes on positioning, voice, or brand (optional but welcomed)

Before drafting, automatically check the current working directory for a file matching `*-ARTDIRECTION.md`. If found, read it — it will inform the Visual identity section. No user action needed.

---

## Concept Brief Structure

Write the document in this order. Each section is 1–3 short paragraphs or statements. No bullet points. No filler. No jargon. Write like a founder who also writes well.

### 1. What it is
Plain English. What does this actually do? What category is it? What is it NOT?
One sharp paragraph. Max 3 sentences. State the category clearly before you complicate it.

### 2. The problem
Not bullet points. A brief narrative about the pain. What happens in the world without this?
What does the user currently have to do, and why does it fall short?
Make it vivid enough that the reader feels it.

### 3. What we believe
One clear positioning statement or belief. This is the thesis — the thing that, if true, justifies everything. It should be specific enough to be mildly controversial.
Format as a blockquote.

### 4. Who it's for
A real description of the person — not a persona card, not a demographic. What do they care about? What have they already tried? Why are they the right person to build this for?
Avoid job titles unless they carry real meaning.

### 5. What success looks like
3 concrete outcomes. Not KPIs — human outcomes. What changes for this person? What becomes possible that wasn't before?

### 6. Visual identity (conditional)

Only include this section if a `*-ARTDIRECTION.md` file exists in the current working directory.

If found: read it and write 3–5 sentences covering the dominant color register, typographic personality, imagery tone, and overall feel. Write as prose — this is a direction summary, not a design spec. End with a reference line: `Full art direction: [filename]`

If not found: omit this section entirely. No placeholder, no mention.

---

## Voice rules

- Short sentences over long ones
- Confident, not hedged — avoid "might", "could", "potentially"
- No buzzwords: no "leverage", "synergy", "holistic", "seamlessly", "transformative"
- If a sentence doesn't earn its place, cut it
- The document should feel like it was written by someone with a clear point of view, not assembled from a template
- Use present tense for what the product does; past tense is fine for the problem narrative

---

## File output

After drafting, save the concept brief as a standalone markdown file:

**Filename:** `[project-slug]-CONCEPT.md`
(e.g. `pm-os-plugin-CONCEPT.md`, `fieldwork-CONCEPT.md`)

Save it in the current working directory using the Write tool.

Confirm the save with: `Saved: [filename]`

Then display the full document inline so the user can read and react without opening the file.

---


## Gotchas

<!-- Add a line here each time this skill produces the wrong output or misses something important. Fill from real failures, not hypotheses. -->

---

## Progressive Updates

Whenever the user explicitly states not to do something (e.g. "don't ask for X", "stop doing Y", "never include Z"), automatically edit the role and behaviour description at the top of this SKILL.md to reflect that constraint permanently. This ensures the skill adapts to user preferences over time without requiring repeated instructions.
