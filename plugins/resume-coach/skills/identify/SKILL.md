---
name: identify
description: >
  This skill should be used when the user asks to "what type of resume is this",
  "identify my resume format", "is this a federal resume", "what kind of CV is this",
  or when the user provides a resume and the type is unclear. Also called automatically
  by the review and rewrite skills as their first step. Works for all resume and CV
  types: standard US, federal, academic, legal, medical, consulting, tech, executive,
  military transition, education, nonprofit, trades, creative, investment banking,
  and EU/Europass formats.
version: 1.1.0
---

# Resume/CV Type & Style Identification

Detect the document type, structural format, and regional conventions of a resume or CV. Confirms with the user before any analysis proceeds.

## Input Handling

If the user provides a file path or uploads a file, read it. If they paste text, use it directly. If neither, ask them to provide the resume.

## Process

### Step 1: Signal Scan

Read `${CLAUDE_PLUGIN_ROOT}/skills/identify/references/document-types.md` for the full detection signal table.

Scan the document for type-identifying signals. Look for:

- **Structural markers** — Required sections, section ordering, length
- **Content markers** — Specific data fields (GS grade, bar admissions, USMLE scores, etc.)
- **Formatting markers** — Template patterns (Europass), photo inclusion, date formats
- **Language markers** — KSA mirroring, legal citation style, clinical terminology
- **Link markers** — GitHub profile, portfolio URL, USAJOBS reference numbers

Collect all detected signals and map them to document types. Most resumes will produce 2-3 signals pointing to a single type.

### Step 2: Format & Region Detection

In addition to document type, identify:

**Structural format:**
- Reverse-chronological (most common)
- Functional / skills-based
- Combination / hybrid

**Regional conventions:**
- US (no photo, 1-2 pages, "resume" for private sector)
- UK (personal statement, 2 pages, A4, "CV" for everything)
- EU/Europass (standardized template, CEFR language ratings)
- German (photo required, date of birth, formal credentials)
- Other EU (note specific conventions observed)

### Step 3: Present Detection & Confirm

Present the detection to the user clearly:

"Based on the structure and content, this appears to be a **[type]** in **[format]** format, following **[regional]** conventions."

Then add a brief note explaining why — cite 2-3 specific signals observed.

Ask: **"Is this correct, or is this a different type of resume/CV?"**

### Step 4: Handle Disagreement (Two-Step Picker)

If the user says no or indicates a different type:

**First, ask the broad category:**

"Which category best describes this document?"

- **Private sector** — Standard corporate/business resume
- **Government** — Federal, state, or municipal government application
- **Academic** — University faculty, research, or teaching position
- **Professional services** — Legal, medical, consulting, or finance
- **Technical** — Software engineering, IT, or technical role
- **Military** — Active duty, veteran, or military-to-civilian transition
- **Other specialized** — Education (K-12), nonprofit, skilled trades, creative/design

**Then, based on the category, show specific types:**

*Private sector:*
- Standard US resume (1-2 pages, reverse-chronological, ATS-optimized)
- Executive resume (C-suite/board level, branding statement, 2-3 pages)
- Creative/infographic resume (visual design, for creative industries only)

*Government:*
- Federal resume / USAJOBS (3-5 pages, KSAs, supervisor details, GS series)
- State/municipal government resume (varies by state, often federal-adjacent)

*Academic:*
- Research-focused CV (publications-first, for research universities)
- Teaching-focused CV (teaching-first, for community colleges and teaching institutions)
- Postdoc/fellowship CV (grants and research potential emphasized)

*Professional services:*
- Legal resume (bar admissions, clerkships, one page)
- Medical CV / ERAS application (USMLE, clinical rotations, hobbies expected)
- Consulting resume (MBB format, education first, one page, competency-mapped)
- Investment banking / PE resume (deal experience, one page)

*Technical:*
- Software engineering resume (GitHub, projects section, tech stack)
- IT / systems administration resume (certifications-heavy, infrastructure focus)

*Military:*
- Military-to-civilian transition resume (MOS translation, transferable skills)
- Active duty / military internal resume (rank, MOS, evaluations)

*Other specialized:*
- Education / K-12 resume (licensure, endorsements, professional development)
- Nonprofit / NGO resume (mission alignment, fundraising metrics)
- Skilled trades resume (certifications, apprenticeships, safety record)

*Regional / international:*
- Europass CV (EU standardized format)
- UK CV (personal statement, 2 pages)
- German CV (Lebenslauf — photo, DOB, formal credentials)

### Step 5: Output Type Context

Once confirmed, state the type context that will be used by subsequent skills:

"**Document type:** [type]
**Structural format:** [chronological / functional / hybrid]
**Regional conventions:** [US / UK / EU / etc.]
**Career level:** [entry / mid / senior / executive] (if determinable)
**ATS applicability:** [standard ATS / USAJOBS scoring / not applicable / limited]"

Read the type-specific reference file for any additional context:
`${CLAUDE_PLUGIN_ROOT}/skills/identify/references/types/[type-slug].md`

Then state: "I'll use these as the lens for all analysis. Ready to proceed with [review / rewrite / ats / whatever the user requested]."

## When Called by Other Skills

When the review, rewrite, or ATS skill calls identify as its first step:

1. Run Steps 1-3 (scan, detect, present)
2. Wait for user confirmation
3. On confirmation, pass the type context to the calling skill and continue
4. On disagreement, run Step 4 (two-step picker), then continue

Do NOT skip the confirmation step even when auto-called. The user must always see what type was detected and have the chance to correct it.

## Rules

- Always present your detection with specific evidence — never state a type without citing signals
- If signals are ambiguous (pointing to multiple types), present the top 2 candidates and ask the user to choose
- If no strong signals are detected, default to "Standard US private-sector resume" but still confirm
- Never proceed to analysis without user confirmation of the document type
- The type context persists for the entire conversation — if the user runs review and then rewrite, the type only needs to be confirmed once
