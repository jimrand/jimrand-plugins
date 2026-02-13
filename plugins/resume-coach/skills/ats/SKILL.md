---
name: ats
description: >
  This skill should be used when the user asks to "optimize for ATS",
  "check ATS compatibility", "keyword optimize my resume",
  "will my resume pass ATS", "match my resume to a job description",
  "check keywords", "USAJOBS optimization", or wants to improve how
  their resume performs in applicant tracking systems or federal
  scoring systems. Works for all resume and CV types including federal
  (USAJOBS), academic, legal, medical, consulting, tech, executive,
  military transition, education, nonprofit, trades, creative,
  and EU/Europass formats. Optionally accepts a job description
  or vacancy announcement to match against.
version: 1.1.0
---

# ATS Optimization

Analyze a resume for applicant tracking system compatibility: keyword coverage, format parsing, and scoring potential. Optionally match against a specific job description.

## Input Handling

Read the resume from a file path, upload, or pasted text. If not provided, ask for it.

Optionally accept a job description to match against. Ask: "Do you have a specific job description you'd like me to match against, or should I analyze for general keyword coverage based on the roles your resume targets?"

## Process

### Step 0: Document Type Identification

Same as review skill. Skip if type context already exists.

**After identification, check ATS applicability:**

If the document type has "Not applicable" for ATS (academic, Europass, creative), inform the user:

"This is a [type] — it's evaluated by [evaluation method], not by ATS systems. ATS optimization isn't relevant for this document type. Would you like me to [suggest appropriate optimization for this type] instead?"

If the document type is Federal Resume, inform the user:

"Federal resumes are evaluated through USAJOBS HR scoring, not commercial ATS systems. The keyword and format rules are different. I can analyze your resume against USAJOBS-specific requirements instead. Would you like to proceed with federal-specific optimization?"

Only proceed with the standard ATS analysis for document types where ATS is applicable.

### Step 1: Format & Parsing Check

Read `${CLAUDE_PLUGIN_ROOT}/skills/review/references/ats-guide.md` for the full ATS reference.

Check for format issues that cause ATS parsing failures:

- **Special characters**: Unicode arrows, em dashes, smart quotes, non-standard bullets
- **Section headers**: Standard naming vs. creative headers parsers won't recognize
- **Date formats**: Consistency and parseability
- **Contact info**: Positioned where parsers expect it (top of document)
- **File format**: Note risks with the input format
- **Layout**: Multi-column layouts, tables used for formatting, text boxes
- **Abbreviations**: Any abbreviation not also spelled out at least once

Report each issue with severity: will break parsing / may cause issues / minor risk.

### Federal-Specific Analysis (if document type is Federal Resume)

If the user has provided a vacancy announcement or job description:

1. Extract KSAs from the vacancy announcement
2. Map each KSA to where it's addressed in the resume
3. Check for verbatim or near-verbatim language matching
4. Identify KSAs that are missing or only implied
5. Check specialized experience coverage
6. Verify all required data fields are present
7. Estimate scoring potential on the 70-100 point scale

Present as a federal scoring analysis rather than an ATS compatibility check.

### Step 2: Keyword Coverage

**If a job description was provided:**

1. Extract required and preferred keywords from the JD
2. Categorize as: technical skills, soft skills, tools/platforms, industry terms, certifications
3. Map each keyword to where it appears in the resume (or note it's missing)
4. Calculate match percentage by category
5. Flag keywords in the resume that are NOT in the JD (potential noise for this specific role)

**If no job description:**

1. Infer 2-3 likely target roles from the resume content
2. Identify standard keywords for those roles using current market expectations
3. Map coverage against those keyword sets
4. Note high-value keywords that are absent

### Step 3: Keyword Placement Analysis

ATS systems weight keywords differently by location:

1. **Skills section**: Most directly parsed; boolean keyword matching
2. **Job titles**: Heavily weighted for role matching
3. **Bullet points**: Contextual matching, NLP-based scoring
4. **Summary/Competencies**: Weighted by some systems, treated as keyword bank by others

Check whether important keywords appear in high-weight locations vs. only in free text.

### Step 4: Scoring Estimate

Based on the analysis, estimate performance:

- **Keyword match rate**: Percentage of expected keywords present
- **Keyword placement**: Are key terms in parseable locations?
- **Format risk**: Could parsing issues cause keyword loss?
- **Title alignment**: Do job titles match common search terms?

Assign overall ATS readiness: **Strong** / **Moderate** / **Needs Work**.

### Step 5: Recommendations

Provide specific, actionable recommendations:

1. **Must-add keywords**: Missing high-value terms with suggested placement
2. **Format fixes**: Specific characters or structures to change
3. **Keyword placement moves**: Terms to add to the Skills section
4. **Title considerations**: Whether titles need context for ATS matching
5. **Abbreviation expansion**: Terms that need both forms

For each recommendation, specify exactly where in the resume to make the change.

### Step 6: Tension Management

Note conflicts between ATS optimization and human readability:

- Keywords that help ATS but sound unnatural — suggest placing in Skills rather than bullets
- Format changes that improve parsing but hurt visual design
- Keyword density that helps scoring but creates a stuffed impression

Frame these as trade-offs and let the user decide.

## Rules

- Never recommend keyword stuffing. Each keyword should appear 1-3 times in natural context.
- Distinguish between must-have keywords (likely filter criteria) and nice-to-have (scoring boost).
- If the JD uses different terminology than the resume for the same concept, flag both terms.
- Consider both exact-match ATS (older systems) and NLP-based ATS (modern systems).
- Always preserve human readability. ATS optimization should be invisible to a human reader.
- The Skills section is a keyword bank for ATS. Core Competencies is a leadership signal for humans. Both can exist and serve different audiences.
