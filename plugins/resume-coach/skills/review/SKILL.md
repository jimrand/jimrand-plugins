---
name: review
description: >
  This skill should be used when the user asks to "review my resume",
  "check my resume", "analyze my resume", "scan my resume for AI",
  "is my resume AI-sounding", "how does my resume look", or wants
  feedback on resume quality, structure, tone, or ATS readiness.
  Works for entry-level through executive resumes.
version: 1.0.0
---

# Resume Review

Comprehensive resume analysis covering AI pattern detection, structure, tone consistency, and ATS readiness. Works for any career level from entry-level to executive.

## Input Handling

If the user provides a file path or uploads a file, read it. If they paste text, use it directly. If neither, ask them to provide the resume.

## Process

### Step 1: Career Level Detection

Before analyzing anything, determine the career level from the resume content:

- **Entry-level** (0-3 years): Recent graduate, internships, limited work history
- **Mid-level** (3-8 years): Individual contributor with growing scope
- **Senior** (8-15 years): Technical leadership, team leads, senior IC
- **Executive** (15+ years): Director+, VP, C-suite, organization builders

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/career-levels.md` for level-specific expectations.

State the detected level and use it as the lens for all subsequent analysis.

### Step 2: Structure Assessment

Evaluate resume structure against career level expectations:

- Section order and completeness
- Section balance (is one role overweighted while another is thin?)
- Whether the summary matches the career level
- Whether skills are positioned appropriately for the level
- Redundancy between sections (summary restating bullet points, etc.)
- Length appropriateness for the career level

### Step 3: AI Pattern Scan

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/resume-ai-patterns.md` for the full pattern reference.

Scan every section for AI tells across four categories:

1. **Structural** — formulaic paragraphs, symmetrical lists, predictable patterns
2. **Lexical** — AI-favorite words, modifier stacking, buzzword density
3. **Rhetorical** — unearned authority claims, empty summarization, emotional flattening
4. **Sentence-level** — uniform length, passive voice overuse, noun phrase pileups

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/resume-word-replacements.md` for the signal word list.

Assign AI confidence:
- **Low** (0-3 tells): Mostly human-sounding
- **Moderate** (4-8 tells): Noticeably AI-influenced
- **High** (9+ tells): Strongly AI-generated

For each tell, quote the specific passage and explain the signal in one sentence.

Do not flag patterns that only appear once unless they are particularly strong signals (e.g., "In today's fast-paced digital landscape").

### Step 4: Tone Consistency

Analyze the resume's tone profile:
- Formality (casual to formal)
- Energy (subdued to enthusiastic)
- Authority (tentative to authoritative)

Check for tone consistency across sections. Flag jarring shifts. Verify the tone matches career level expectations from the career-levels reference.

### Step 5: ATS Quick Check

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/ats-guide.md` for the full ATS reference.

Perform a basic ATS readiness check:
- Format and parsing risks (special characters, unusual structure)
- Keyword presence for likely target roles
- Section header naming (standard vs. non-standard)
- Date format consistency
- Abbreviations used without being spelled out

Note: For deep ATS analysis with job description matching, suggest `/resume-coach:ats`.

### Step 6: Report

Present findings organized as:

1. **Career Level**: Detected level and whether the resume matches it
2. **Structure**: What works, what needs attention
3. **AI Confidence**: [Low / Moderate / High] with count and category breakdown
4. **AI Tells**: Each flagged passage with quoted text, category, and signal explanation
5. **Tone**: Profile summary and any consistency issues
6. **ATS Quick Check**: Format risks and obvious keyword gaps
7. **Top 3 Priority Fixes**: The three changes with the most impact

### Step 7: Next Steps

After the report, ask:

"Would you like me to rewrite the flagged sections with annotations showing each change and why, or would you prefer to make the edits yourself based on this analysis?"

If they want a rewrite, suggest `/resume-coach:rewrite`.
If they want ATS optimization against a specific job description, suggest `/resume-coach:ats`.

## Rules

- Always quote the specific passage being flagged. Never flag in the abstract.
- Calibrate findings to career level — some formality that looks AI-generated is appropriate at executive level.
- If the resume scores Low on AI tells, say so clearly. Do not manufacture findings.
- Do not rewrite anything in this skill. Analysis only. Rewrites happen in `/resume-coach:rewrite`.
