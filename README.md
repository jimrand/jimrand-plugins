# Jim's Claude Plugins

A plugin marketplace for Claude Code and Cowork.

## Available Plugins

### resume-coach
AI-powered resume review and optimization. Detects AI writing patterns,
improves structure and tone for any career level, and optimizes for ATS.

**Skills included:**
- `review` — Comprehensive resume analysis with AI pattern detection
- `rewrite` — Rewrite flagged sections with annotated changes
- `ats` — ATS-specific optimization with optional job description matching

## Installation

```bash
/plugin marketplace add jimrand/jimrand-plugins
/plugin install resume-coach@jimrand-plugins
```

## Usage

Upload a resume, then run:
1. `/resume-coach:review` for full analysis
2. `/resume-coach:rewrite` to fix flagged sections
3. `/resume-coach:ats` with a job description for targeted optimization
