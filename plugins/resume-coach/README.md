# Resume Coach

AI-powered resume review and optimization. Detects AI writing patterns, improves structure and tone for any career level (entry through executive), and optimizes for applicant tracking systems.

## Skills

### `/resume-coach:review`
Comprehensive resume analysis. Detects career level, scans for AI writing tells across four categories (structural, lexical, rhetorical, sentence-level), checks structure and tone consistency, and runs a basic ATS readiness check. Returns a detailed report with specific passages quoted and flagged. Offers the choice of analysis-only or full rewrite.

### `/resume-coach:rewrite`
Rewrites flagged sections with annotated changes. Each rewrite shows the original passage, the revised version, and a one-sentence explanation of what was AI-sounding and how the fix addresses it. Ends with a clean output block ready to copy. Calibrates tone and style to career level.

### `/resume-coach:ats`
ATS-specific optimization. Checks format and parsing risks, analyzes keyword coverage, and provides placement recommendations. Optionally accepts a job description for targeted keyword matching with match percentage scoring.

## Reference Files

Located in `skills/review/references/`:

- **resume-ai-patterns.md** — Four categories of AI tells specific to resumes
- **resume-word-replacements.md** — Signal words, cliche phrases, and replacement suggestions
- **ats-guide.md** — How ATS systems parse, match, and score resumes
- **career-levels.md** — Structure, tone, and emphasis expectations by career level

## Usage

Provide a resume as a file upload, file path, or pasted text. The skills will detect the career level automatically and calibrate all analysis accordingly.

Typical workflow:
1. Run `/resume-coach:review` for a full analysis
2. Run `/resume-coach:rewrite` to fix flagged sections
3. Run `/resume-coach:ats` with a specific job description for targeted optimization
