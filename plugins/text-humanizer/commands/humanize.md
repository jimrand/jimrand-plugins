---
description: Rewrite text to sound human, with annotated changes
allowed-tools: Read, Write, Edit, Glob, Grep
argument-hint: [file-path or paste text]
---

Humanize the provided text — detect AI writing patterns and rewrite the content to sound naturally human while preserving the original tone.

Load the ai-writing-patterns skill for reference. Also read `${CLAUDE_PLUGIN_ROOT}/skills/ai-writing-patterns/references/word-replacements.md` and `${CLAUDE_PLUGIN_ROOT}/skills/ai-writing-patterns/references/before-after-examples.md` for detailed guidance.

## Input Handling

If `$ARGUMENTS` is a file path, read the file. If `$ARGUMENTS` is not provided, ask the user to paste or provide the text they want humanized. If the user has already pasted text in their message, use that directly.

## Process

### Step 1: Tone Analysis

Before touching any words, analyze the original text's tone:

- Formality (casual ↔ formal)
- Energy (subdued ↔ enthusiastic)
- Warmth (detached ↔ personal)
- Authority (tentative ↔ authoritative)
- Humor (serious ↔ playful)

State the tone profile in one sentence. This is the guardrail — all rewrites must stay within this tonal range.

### Step 2: AI Pattern Scan

Scan the text for AI tells across all four categories: structural, lexical, rhetorical, and sentence-level. Count and categorize every tell found.

Assign an overall AI confidence level:

- **Low** (0-3 tells): Mostly human-sounding. Minor tweaks at most.
- **Moderate** (4-8 tells): Noticeably AI-influenced. Targeted rewrites needed.
- **High** (9+ tells): Strongly AI-generated. Substantial rewriting needed.

### Step 3: Annotated Rewrite

For each AI tell found, show:

**[Category: specific pattern]**
> Original passage

→ Rewritten passage

*Why*: One sentence explaining what was AI-sounding and how the rewrite fixes it.

Group changes by paragraph or section so the user can follow along with the original text.

### Step 4: Clean Output

After all annotations, present the complete rewritten text as a single clean block with no annotations — ready to copy and use.

If the input was a file, offer to write the rewritten text to a new file (appending `-humanized` to the original filename).

## Rules

- Never change factual content, data, quotes, or proper nouns.
- Preserve the original text's meaning completely — no adding claims or removing information.
- Keep approximately the same length (±15%). Do not pad or dramatically shorten.
- If the original text is already natural-sounding (Low AI confidence), say so and suggest only minor tweaks rather than rewriting.
- Match the tone profile from Step 1 in every rewritten passage.
