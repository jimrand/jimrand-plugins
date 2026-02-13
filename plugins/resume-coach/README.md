# Resume Coach

AI-powered resume and CV review, rewriting, and optimization. Works for all document types — standard US, federal, academic, legal, medical, consulting, tech, executive, military transition, education, nonprofit, trades, creative, and EU/international formats.

## Skills

### `/resume-coach:identify`
Detect the document type, structural format, and regional conventions. Confirms with the user before analysis proceeds. Called automatically by review and rewrite, or invoke standalone.

### `/resume-coach:review`
Comprehensive resume analysis calibrated to document type. Scans for AI writing tells across seven categories, checks structure against type-specific expectations, evaluates tone for the appropriate register, and runs the correct evaluation check (ATS, USAJOBS scoring, or notes non-applicability for academic/creative types).

### `/resume-coach:rewrite`
Rewrites flagged sections with annotated changes, calibrated to document type and career level. Each rewrite shows original, revision, and explanation. Respects type-specific conventions (formal federal language, academic precision, legal conciseness, etc.).

### `/resume-coach:ats`
Evaluation system optimization. For standard ATS types: keyword coverage, format parsing, placement analysis. For federal resumes: USAJOBS-specific scoring analysis against vacancy announcements. For academic/creative types: notes that ATS is not applicable and suggests appropriate alternatives.

## Reference Files

### Shared references (`skills/review/references/`)
- **resume-ai-patterns.md** — Seven categories of AI tells, calibrated with signal strength guide
- **resume-word-replacements.md** — Signal words, copula avoidance, participial phrases, punctuation fixes
- **ats-guide.md** — Commercial ATS parsing, matching, and scoring
- **career-levels.md** — Structure, tone, and emphasis by career level
- **research-sources.md** — Academic citations backing detection patterns

### Type identification (`skills/identify/references/`)
- **document-types.md** — Detection signal table and type-to-expectations quick reference

### Type-specific rules (`skills/identify/references/types/`)
One file per document type, each containing: required sections, length rules, content rules, AI detection calibration, evaluation system details, career level mapping, and common mistakes.

## Usage

Provide a resume or CV as a file upload, file path, or pasted text. The skills will automatically detect the document type and confirm with you before proceeding.

Typical workflow:
1. Run `/resume-coach:review` — identifies type, confirms, then delivers full analysis
2. Run `/resume-coach:rewrite` — fixes flagged sections with type-appropriate rewrites
3. Run `/resume-coach:ats` — optimizes for the right evaluation system

Or run `/resume-coach:identify` standalone to check what type your document is before deciding what to do next.
