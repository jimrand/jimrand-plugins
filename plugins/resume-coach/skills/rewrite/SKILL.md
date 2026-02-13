---
name: rewrite
description: >
  This skill should be used when the user asks to "rewrite my resume",
  "fix my resume", "humanize my resume", "make my resume sound human",
  "clean up my resume bullets", "reword my resume", or wants AI-sounding
  text in their resume rewritten with annotations explaining each change.
  Works for entry-level through executive resumes.
version: 1.0.0
---

# Resume Rewrite

Detect AI writing patterns in a resume and rewrite flagged sections with annotated changes. Preserve all facts, tone, and career level while removing AI tells.

## Input Handling

If the user provides a file path or uploads a file, read it. If they paste text, use it directly. If neither, ask them to provide the resume.

If a review has already been done in this conversation, use those findings as a starting point rather than re-scanning from scratch.

## Process

### Step 1: Tone Lock

Before changing any words, lock the target tone.

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/career-levels.md` for level-specific tone expectations.

Determine:
- Career level (entry / mid / senior / executive)
- Formality level
- Energy level
- Authority level

State the tone profile in one sentence. This is the guardrail — all rewrites must stay within this range.

### Step 2: AI Pattern Scan

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/resume-ai-patterns.md` and `${CLAUDE_PLUGIN_ROOT}/skills/review/references/resume-word-replacements.md`.

Scan every bullet and section for AI tells. Categorize each as structural, lexical, rhetorical, or sentence-level. Skip sections that already sound natural.

### Step 3: Annotated Rewrite

For each flagged passage, present:

**[Category: specific pattern]**
> Original passage (quoted)

→ Rewritten passage

*Why*: One sentence explaining what was AI-sounding and how the rewrite fixes it.

Group changes by role or section so the user can follow along with the original.

### Step 4: Clean Output

After all annotations, present the complete rewritten text as a single clean block with no annotations — ready to copy and use.

If the input was a file, offer to write the rewritten version to a new file.

## Rewrite Rules

- Never change factual content, data, names, dates, or numbers.
- Preserve the original meaning completely.
- Keep approximately the same length (±15%) per bullet.
- Match the tone profile from Step 1 in every rewrite.
- Do not introduce new AI tells in the rewrite. Check your own output.
- If a section is already natural-sounding, say so and skip it.

## Career Level Calibration

Adapt rewrite style to career level:

**Entry-level**: Action verbs, specific contributions, learning trajectory. Do not use leadership framing for intern work. "Assisted with" is honest and appropriate. Quantify even small results.

**Mid-level**: Ownership language ("built," "designed," "ran"). Show growing scope across roles. Balance technical depth with business awareness. Each role should tell a different story.

**Senior**: Leadership framing ("established the function," "grew the team"). Strategic language is appropriate but must be backed by specifics. Name stakeholders, decisions, outcomes.

**Executive**: Organization-building language. Board-level communication style — concise, outcome-focused. The summary should tell a career story, not list attributes. Some formality is appropriate; do not overcorrect to casual.

## Common Resume Rewrites

| AI Pattern | Fix Strategy |
|---|---|
| "Proven track record of..." | Cut the claim, lead with the proof |
| "Results-oriented professional" | Delete — the bullets prove it |
| "Spearheaded / Championed / Orchestrated" | Replace with "Led" or the specific action |
| "Cross-functional synergies" | Name the actual teams and what they built |
| "Passionate about X" | Show passion through specific work |
| Modifier stacking | Keep the strongest modifier, cut the rest |
| Vague authority endings | Name the specific decision or outcome |
| Noun phrase pileups | Break into plain language |
| "Responsible for managing..." | "Managed X, resulting in Y" |
| "Played a key role in..." | State what you did directly |
