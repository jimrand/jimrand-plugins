# Text Humanizer

Detect AI-written content and rewrite it to sound naturally human — while preserving the original tone, meaning, and factual content.

## What It Does

This plugin adds two capabilities:

**`/humanize`** — Analyzes text for AI writing patterns, then rewrites it with annotated explanations of every change. Outputs both an annotated diff and a clean rewritten version ready to use.

**`/ai-detect`** — Scans text for AI writing patterns and reports findings without making any changes. Useful when you want to assess content before deciding how to edit it yourself.

Both commands work with any type of writing: emails, blog posts, reports, memos, social media posts, product descriptions, and more.

## Components

| Type | Name | Purpose |
|------|------|---------|
| Command | `/humanize` | Full analysis + annotated rewrite |
| Command | `/ai-detect` | Detection-only scan, no rewriting |
| Skill | ai-writing-patterns | Core knowledge base: AI tells, humanization techniques, tone preservation |

## Usage

### Humanize text

Type `/humanize` and then paste your text, or provide a file path:

```
/humanize path/to/document.md
```

You'll get:
1. A tone profile of the original text
2. An AI confidence score (Low / Moderate / High)
3. Each change annotated with what was AI-sounding and why it was rewritten
4. A clean, complete rewrite ready to copy

### Detect AI patterns

Type `/ai-detect` and paste your text or provide a file path:

```
/ai-detect path/to/document.md
```

You'll get:
1. An AI confidence score
2. Each detected pattern with the flagged passage quoted
3. A summary of which patterns are most prominent

## How It Works

The plugin identifies AI writing through four categories of signals:

- **Structural** — formulaic paragraphs, symmetrical lists, predictable document arcs
- **Lexical** — overused AI-favorite words, hedge stacking, filler affirmations
- **Rhetorical** — compulsive balance, empty summarization, emotional flattening
- **Sentence-level** — uniform sentence lengths, passive voice overuse, noun phrase pileups

Rewrites preserve the original tone by profiling formality, energy, warmth, authority, and humor before making any changes.

## No Setup Required

This plugin has no external dependencies, API keys, or service integrations. It works entirely through Claude's language capabilities guided by the bundled knowledge base.
