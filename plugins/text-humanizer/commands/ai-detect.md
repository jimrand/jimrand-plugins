---
description: Scan text for AI writing patterns without rewriting
allowed-tools: Read, Glob, Grep
argument-hint: [file-path or paste text]
---

Scan the provided text for AI writing patterns and report findings. Do NOT rewrite the text — just analyze and flag what sounds AI-generated.

Load the ai-writing-patterns skill for reference. Also read `${CLAUDE_PLUGIN_ROOT}/skills/ai-writing-patterns/references/word-replacements.md` for the word/phrase signal list.

## Input Handling

If `$ARGUMENTS` is a file path, read the file. If `$ARGUMENTS` is not provided, ask the user to paste or provide the text they want scanned. If the user has already pasted text in their message, use that directly.

## Process

### Step 1: Scan All Seven Categories

Identify the genre (business, creative, technical, marketing, academic, or other) and weight your scan accordingly — see Genre-Aware Detection in the skill.

Check the text for tells in each category:

1. **Structural tells** — formulaic paragraphs, symmetrical lists, smooth transitions, predictable arc
2. **Lexical tells** — elevated vocabulary, hedge stacking, filler affirmations, AI-favorite words, modifier stacking, copula avoidance, nominalization overuse
3. **Rhetorical tells** — compulsive balance, empty summarization, unearned authority, emotional flattening, "not just X but Y," significance inflation
4. **Sentence-level tells** — uniform length, passive voice overuse, noun phrase pileup, participial phrase overuse
5. **Style & formatting tells** — em dash overuse, boldface overuse, redundant inline headers, title case, emoji, uniformly formatted lists
6. **Content inflation tells** — significance inflation, vague attributions, adversity-to-triumph arcs, promotional vocabulary clusters
7. **Communication artifacts** — chatbot closers, metacommentary, disclaimer language, knowledge framing

### Step 2: Report

Present findings in this format:

**AI Confidence: [Low / Moderate / High]** — [X] patterns detected across [Y] categories.

**Genre:** [identified genre] | **Tone Profile**: Describe the text's tone in one sentence (formality, energy, warmth, authority, humor).

Then for each tell found:

**[Category: specific pattern]** ⚑ [high/medium/low]
> Quote the specific passage (keep quotes short — just enough to identify the location)

*Signal*: One sentence explaining why this reads as AI-generated.

### Step 3: Summary

End with a brief overall assessment:

- Which category has the most tells
- The single most AI-sounding passage in the text
- Whether the text would benefit from a full humanization pass (and suggest using `/humanize` if so)

## Rules

- Do NOT rewrite any part of the text. This is analysis only.
- Be specific — always quote the passage being flagged.
- Note the signal strength of each tell (high / medium / low) using the Signal Strength Guide in the skill.
- Don't flag patterns that only appear once unless they are high-signal tells (e.g., "In today's fast-paced digital landscape," chatbot closers, significance inflation on mundane topics).
- If the text scores Low, say so clearly and don't manufacture findings.
