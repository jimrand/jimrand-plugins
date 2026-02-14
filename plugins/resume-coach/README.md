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

## Changelog

### v1.1.0

**Document type/style recognition.** New `/resume-coach:identify` skill detects document type, structural format, and regional conventions from 50+ signals. Supports 17 resume types: standard US, federal, academic, tech, legal, medical, consulting, IB/PE, executive, education, nonprofit, military transition, skilled trades, creative, Europass, UK CV, and German CV. User confirmation required before analysis proceeds.

**All skills now type-aware.** Review, rewrite, and ATS skills call identify as Step 0. Structure evaluation uses type-specific required/optional sections. AI detection calibration adjusts sensitivity per type (e.g., formal federal language is expected, not flagged). ATS check routes to the correct evaluation system — commercial ATS, USAJOBS HR scoring, committee review, or notes non-applicability.

**Expanded AI detection.** Detection expanded from 4 to 7 categories: added style & formatting tells (em dash overuse, bold overuse, uniformly formatted bullets), content inflation tells (significance inflation, vague attributions), and communication artifacts (chatbot closers, metacommentary, disclaimer language). Signal strength guide classifies each tell as high, medium, or low signal.

**New humanization patterns.** Added copula avoidance patterns (restoring "is"/"has"/"are" where AI avoids them), participial phrase alternatives, and em dash decision framework for punctuation fixes.

**17 type-specific reference files.** One file per document type with required sections, length rules, content rules, AI detection calibration, evaluation system details, career level mapping, and common mistakes.

**Federal resume support.** USAJOBS-specific analysis path: KSA extraction from vacancy announcements, coverage mapping, specialized experience checks, and scoring estimate on the 70-100 point scale.

**Research citations.** New `research-sources.md` with peer-reviewed sources backing detection patterns (Kobak et al., Reinhart et al., Juzek & Ward, Merrill et al.).

### v1.0.0

Initial release. 4 AI detection categories (structural, lexical, rhetorical, sentence-level), career level calibration (entry through executive), ATS optimization, `/review`, `/rewrite`, and `/ats` skills.
