# Jim Rand's Claude Plugins

A plugin marketplace for Claude Code and Cowork.

## Available Plugins

### resume-coach
AI-powered resume review and optimization. Detects AI writing patterns,
improves structure and tone for any career level, and optimizes for ATS.

**Skills included:**
- `review` — Comprehensive resume analysis with AI pattern detection
- `rewrite` — Rewrite flagged sections with annotated changes
- `ats` — ATS-specific optimization with optional job description matching

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
Upload a resume, then run:
1. `/resume-coach:review` for full analysis
2. `/resume-coach:rewrite` to fix flagged sections
3. `/resume-coach:ats` with a job description for targeted optimization

### text-humanizer
Paste text or provide a file path:
1. `/humanize` to detect AI patterns and get an annotated rewrite
2. `/ai-detect` to scan for AI patterns without rewriting

## Changelog

### text-humanizer

**v1.1.0** — Expanded detection from 4 to 7 categories (added style & formatting, content inflation, communication artifacts). Added 3 new humanization techniques (11 total). Added signal strength classification, genre-aware detection weighting, and output format choice (inline or diff mode). New reference files for research citations and punctuation patterns. Expanded word list with copula avoidance, participial phrase, and communication artifact sections. 4 new before/after examples (9 total).

**v1.0.0** — Initial release. 4 detection categories, 8 humanization techniques, 5 before/after examples, tone preservation framework, `/humanize` and `/ai-detect` commands.
