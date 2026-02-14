---
name: review
description: >
  This skill should be used when the user asks to "review my resume",
  "check my resume", "analyze my resume", "scan my resume for AI",
  "is my resume AI-sounding", "how does my resume look", or wants
  feedback on resume quality, structure, tone, or ATS readiness.
  Works for all resume and CV types: standard US, federal, academic,
  legal, medical, consulting, tech, executive, military transition,
  education, nonprofit, trades, creative, investment banking,
  and EU/Europass formats. Entry-level through executive.
version: 1.1.0
---

# Resume Review

Comprehensive resume analysis covering AI pattern detection, structure, tone consistency, and ATS readiness. Works for any career level from entry-level to executive.

## Input Handling

If the user provides a file path or uploads a file, read it. If they paste text, use it directly. If neither, ask them to provide the resume.

## Process

### Step 0: Document Type Identification

Before analyzing anything, identify the document type.

Read `${CLAUDE_PLUGIN_ROOT}/skills/identify/SKILL.md` and execute the identify process:

1. Scan for type signals per `${CLAUDE_PLUGIN_ROOT}/skills/identify/references/document-types.md`
2. Present detection to user and confirm
3. If confirmed, read the type-specific reference file: `${CLAUDE_PLUGIN_ROOT}/skills/identify/references/types/[type-slug].md`
4. If the user disagrees, run the two-step picker per the identify skill

The confirmed document type becomes the lens for ALL subsequent steps. If type context was already established earlier in the conversation (e.g., user already ran `/resume-coach:identify`), skip this step and use the existing context.

### Step 1: Career Level Detection

Before analyzing anything, determine the career level from the resume content.

**If document type is Federal Resume:** Map career level to GS grade per the federal-resume reference file. GS-5 to GS-7 = entry, GS-9 to GS-11 = mid, GS-12 to GS-13 = senior, GS-14 to GS-15 / SES = executive.

**If document type is Academic CV:** Map career level to academic rank: ABD/PhD candidate = entry, Postdoc/Visiting = early-mid, Assistant Professor = mid, Associate Professor = senior, Full Professor / Endowed Chair = executive.

**For all other types:** Use the existing career level framework:
- Entry-level (0-3 years)
- Mid-level (3-8 years)
- Senior (8-15 years)
- Executive (15+ years)

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/career-levels.md` for standard level expectations. Also read the career level mapping in the type-specific reference file for any adjustments.

### Step 2: Structure Assessment

Evaluate resume structure against **type-specific** and career level expectations.

Read the "Required Sections" and "Optional Sections" from the type-specific reference file. Evaluate:

- Are all required sections present and in expected order?
- Are any inappropriate sections included (e.g., skills section on a legal resume, hobbies on a private-sector resume)?
- Is section balance appropriate for this document type?
- Is length appropriate for this type and career level?
- Does the format (chronological / functional / hybrid) match type expectations?

**Type-specific structure notes:**
- Federal: Check for supervisor info, hours, salary in each experience entry
- Academic: Check publication subdivisions, citation format consistency, section order for institution type
- Tech: Check for GitHub link, projects section, skills list currency
- Legal: Check for bar admissions placement, clerkship formatting
- Consulting: Confirm one page, education at top, interests section present
- Europass: Confirm template structure, CEFR language ratings

### Step 3: AI Pattern Scan

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/resume-ai-patterns.md` for the general pattern reference.

**CRITICAL: Before scanning, read the "AI Detection Calibration" section from the type-specific reference file.** This tells you:
- Which patterns to reduce sensitivity for (legitimate conventions for this type)
- Which patterns to increase sensitivity for (especially strong tells for this type)
- False positive guidance specific to this document type

Apply the calibration adjustments during your scan. Patterns flagged as "reduce sensitivity" should only be flagged if they appear at very high frequency or in clearly inappropriate contexts.

Scan every section for AI tells across the standard four categories, plus the three additional categories from the expanded detection framework:

1. **Structural** — formulaic paragraphs, symmetrical lists, predictable patterns
2. **Lexical** — AI-favorite words, modifier stacking, buzzword density, copula avoidance, nominalization overuse
3. **Rhetorical** — unearned authority claims, empty summarization, emotional flattening, significance inflation, "not just X, but Y"
4. **Sentence-level** — uniform length, passive voice overuse, noun phrase pileups, participial phrase overuse
5. **Style & Formatting** — em dash overuse, bold overuse, uniformly formatted lists
6. **Content Inflation** — significance inflation, vague attributions, adversity-to-triumph arc
7. **Communication Artifacts** — chatbot closers, metacommentary, disclaimer language (flag these heavily — they should never appear in a resume)

### Step 4: Tone Consistency

Analyze the resume's tone profile:
- Formality (casual to formal)
- Energy (subdued to enthusiastic)
- Authority (tentative to authoritative)

Check for tone consistency across sections. Flag jarring shifts. Verify the tone matches career level expectations from the career-levels reference.

### Step 5: ATS Quick Check

**First, check ATS applicability for this document type** per the type-specific reference file:

- **Standard ATS** (most private-sector types): Run full ATS check per `${CLAUDE_PLUGIN_ROOT}/skills/review/references/ats-guide.md`
- **USAJOBS scoring** (federal): Note that commercial ATS rules don't apply. Check for USAJOBS-specific requirements: KSA coverage, specialized experience language, required data fields.
- **Not applicable** (academic, Europass, creative): Skip ATS check entirely. Note that this document type is evaluated by [committee / direct review / etc.] and ATS optimization is not relevant.
- **Limited** (legal, some education): Note that ATS may or may not apply depending on the specific employer.

For types with standard ATS, perform the basic ATS readiness check as before.

### Step 6: Report

Present findings organized as:

1. **Document Type**: [Confirmed type] — [brief note on what this means for the analysis]
2. **Career Level**: Detected level and whether the resume matches it
3. **Structure**: What works, what needs attention (evaluated against type-specific expectations)
4. **AI Confidence**: [Low / Moderate / High] with count and category breakdown (calibrated for document type)
5. **AI Tells**: Each flagged passage with quoted text, category, and signal explanation
6. **Tone**: Profile summary and any consistency issues
7. **ATS / Evaluation Check**: Type-appropriate evaluation (ATS for private sector, USAJOBS scoring for federal, "N/A" for academic, etc.)
8. **Top 3 Priority Fixes**: The three changes with the most impact for this specific document type

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
