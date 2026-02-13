# Jim Rand's Claude Plugins

A plugin marketplace for Claude Code and Cowork.

## Available Plugins

### resume-coach
AI-powered resume and CV review, rewriting, and optimization for all document
types: standard US, federal, academic, legal, medical, consulting, tech,
executive, military transition, education, nonprofit, trades, creative, and
EU/international formats.

**Skills included:**
- `identify` — Detect document type, structural format, and regional conventions
- `review` — Type-calibrated analysis with AI detection across seven categories
- `rewrite` — Rewrite flagged sections with type-appropriate conventions
- `ats` — Evaluation system optimization (ATS, USAJOBS scoring, or alternatives)

### text-humanizer
Detect AI-written content and rewrite it to sound naturally human while
preserving the original tone, meaning, and factual content.

**Commands included:**
- `/humanize` — Full analysis + annotated rewrite (inline or diff mode)
- `/ai-detect` — Detection-only scan, no rewriting

## Installation

```bash
/plugin marketplace add jimrand/jimrand-plugins
/plugin install resume-coach@jimrand-plugins
/plugin install text-humanizer@jimrand-plugins
```

## Usage

### resume-coach
Upload a resume or CV, then run:
1. `/resume-coach:review` — identifies type, confirms, then delivers full analysis
2. `/resume-coach:rewrite` — fixes flagged sections with type-appropriate rewrites
3. `/resume-coach:ats` — optimizes for the right evaluation system

Or run `/resume-coach:identify` standalone to check the document type first.

### text-humanizer
Paste text or provide a file path:
1. `/humanize` to detect AI patterns and get an annotated rewrite
2. `/ai-detect` to scan for AI patterns without rewriting

## Changelog

### resume-coach

**v1.1.0** — Added document type/style recognition supporting 17 resume types (federal, academic, tech, legal, medical, consulting, executive, IB/PE, education, nonprofit, military transition, skilled trades, creative, Europass, UK CV, German CV, standard US). New `/resume-coach:identify` skill for type detection with user confirmation. All existing skills (review, rewrite, ats) now type-aware with calibrated AI detection, type-specific structure evaluation, and appropriate evaluation system routing. Integrated text-humanizer v1.1.0 improvements: expanded AI detection from 4 to 7 categories, signal strength guide, copula/participial pattern detection, and research source citations. 17 type-specific reference files, each with required sections, AI detection calibration, evaluation system details, and common mistakes.

**v1.0.0** — Initial release. 4 AI detection categories, career level calibration, ATS optimization, `/review`, `/rewrite`, and `/ats` skills.

### text-humanizer

**v1.1.0** — Expanded detection from 4 to 7 categories (added style & formatting, content inflation, communication artifacts). Added 3 new humanization techniques (11 total). Added signal strength classification, genre-aware detection weighting, and output format choice (inline or diff mode). New reference files for research citations and punctuation patterns. Expanded word list with copula avoidance, participial phrase, and communication artifact sections. 4 new before/after examples (9 total).

**v1.0.0** — Initial release. 4 detection categories, 8 humanization techniques, 5 before/after examples, tone preservation framework, `/humanize` and `/ai-detect` commands.
