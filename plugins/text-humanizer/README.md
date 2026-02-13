# Text Humanizer

Detect AI-written content and rewrite it to sound naturally human — while preserving the original tone, meaning, and factual content.

## What It Does

This plugin adds two capabilities:

**`/humanize`** — Analyzes text for AI writing patterns, then rewrites it with annotated explanations of every change. Offers two output modes: inline (full walkthrough) or diff (compact changes-only view). Outputs a clean rewritten version ready to use.

**`/ai-detect`** — Scans text for AI writing patterns and reports findings without making any changes. Useful when you want to assess content before deciding how to edit it yourself.

Both commands work with any type of writing: emails, blog posts, reports, memos, social media posts, product descriptions, technical documentation, academic papers, and more.

## Components

| Type | Name | Purpose |
|------|------|---------|
| Command | `/humanize` | Full analysis + annotated rewrite (inline or diff mode) |
| Command | `/ai-detect` | Detection-only scan, no rewriting |
| Skill | ai-writing-patterns | Core knowledge base: AI tells, humanization techniques, tone preservation |

## Usage

### Humanize text

Type `/humanize` and then paste your text, or provide a file path:

```
/humanize path/to/document.md
```

You'll be asked to choose an output format:
- **Inline mode** — Full annotated walkthrough (best for learning what to fix)
- **Diff mode** — Compact changes-only view (best for long documents)

Then you'll get:
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
1. An AI confidence score with genre identification
2. Each detected pattern with the flagged passage quoted and signal strength noted
3. A summary of which patterns are most prominent

## How It Works

The plugin identifies AI writing through seven categories of signals:

- **Structural** — formulaic paragraphs, symmetrical lists, predictable document arcs
- **Lexical** — overused AI-favorite words, hedge stacking, filler affirmations, copula avoidance, nominalization overuse
- **Rhetorical** — compulsive balance, empty summarization, emotional flattening, significance inflation
- **Sentence-level** — uniform sentence lengths, passive voice overuse, noun phrase pileups, participial phrase overuse
- **Style & formatting** — em dash overuse, boldface overuse, redundant inline headers, title case, emoji
- **Content inflation** — significance inflation, vague attributions, adversity-to-triumph arcs, promotional vocabulary
- **Communication artifacts** — chatbot closers, metacommentary, disclaimer language

Rewrites preserve the original tone by profiling formality, energy, warmth, authority, and humor before making any changes. Detection is weighted by genre — technical documents, marketing copy, academic papers, and casual writing each have different primary tells.

## Research Basis

The detection patterns in this plugin are informed by peer-reviewed research on LLM writing characteristics, including studies on lexical overrepresentation in biomedical literature (Kobak et al., 2025), grammatical style variation between human and AI text (Reinhart et al., 2025), the causes of vocabulary overuse in large language models (Juzek & Ward, 2025), and large-scale analysis of ChatGPT conversation patterns (Merrill et al., 2025). See `skills/ai-writing-patterns/references/research-sources.md` for full citations.

## No Setup Required

This plugin has no external dependencies, API keys, or service integrations. It works entirely through Claude's language capabilities guided by the bundled knowledge base.

## Changelog

### v1.1.0

**Detection expanded from 4 to 7 categories.** Added style & formatting tells (em dash overuse, boldface overuse, redundant inline headers, title case, emoji, uniform lists), content inflation tells (significance inflation, vague attributions, adversity-to-triumph arcs, promotional vocabulary clusters), and communication artifacts (chatbot closers, metacommentary, disclaimer language, knowledge framing). Existing categories gained new patterns: copula avoidance, nominalization overuse, participial phrase overuse, and the "not just X, but Y" construction.

**3 new humanization techniques (11 total).** Added Restore the Copula (#9), Inject Genuine Voice (#10), and Fix the Formatting (#11).

**Signal strength guide.** Each AI tell is now classified as high, medium, or low signal to calibrate confidence and avoid false positives.

**Genre-aware detection.** Detection is now weighted by content type (business, creative, technical, marketing, academic) so the most relevant tells are prioritized.

**Output format choice.** `/humanize` now offers inline mode (full annotated walkthrough) or diff mode (compact changes-only view).

**Research citations.** All quantified claims are now attributed to peer-reviewed sources. New `references/research-sources.md` file provides the full citation list.

**New reference files.** Added `references/punctuation-patterns.md` (em dash, bold, and formatting fix guide) and `references/research-sources.md`.

**Expanded word list.** ~13 new high-signal words added. New sections for copula avoidance patterns, participial phrase alternatives, and communication artifacts.

**4 new before/after examples (9 total).** Added technical README, social media post, academic abstract, and neighborhood description examples.

### v1.0.0

Initial release. 4 detection categories (structural, lexical, rhetorical, sentence-level), 8 humanization techniques, 5 before/after examples, tone preservation framework, `/humanize` and `/ai-detect` commands.
