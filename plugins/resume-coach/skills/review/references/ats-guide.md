# ATS Optimization Guide

How applicant tracking systems work and how to optimize resumes for them.

## How ATS Systems Work

Modern ATS platforms (Workday Recruiting, Greenhouse, Lever, iCIMS, Taleo, SmartRecruiters) process resumes in three stages.

### 1. Parsing
The system extracts structured data: contact info, work history, education, skills.

**What breaks parsing:**
- Multi-column layouts (parser reads left-to-right, creates garbled text)
- Tables used for layout (some parsers skip table content)
- Headers and footers (often ignored)
- Text in images, graphics, or text boxes
- Non-standard section headers
- Unusual characters that render differently across systems
- PDF files with non-selectable text (image-based PDFs)

### 2. Keyword Matching

**Boolean matching (older systems):**
- Exact keyword match against required skills
- AND/OR logic: "Python AND SQL AND AWS"
- Case-insensitive but exact-string in many systems

**NLP-based matching (modern systems):**
- Semantic similarity ("ML" matches "machine learning")
- Contextual relevance
- Synonym expansion ("managed" matches "led" matches "supervised")
- Skills taxonomies (recognizes related skill clusters)

**Implications:**
- Use BOTH spelled-out terms and acronyms: "Natural Language Processing (NLP)"
- Include exact keywords from the job description, not just synonyms
- Place keywords in the Skills section AND in context within bullets

### 3. Scoring & Ranking
Systems assign relevance scores based on:

- Keyword match rate against required/preferred qualifications
- Keyword placement weight (Skills > titles > bullets > summary)
- Recency (keywords in recent roles weighted higher)
- Title alignment with the open position
- Experience duration with each skill
- Education match (degree level and field)

## Keyword Strategy

### Required vs. Preferred
- **Required/Must-have**: Likely filter criteria. Missing them may disqualify.
- **Preferred/Nice-to-have**: Boost the score but probably not filters.
- **Listed in both JD and qualifications**: Highest priority keywords.

### Keyword Placement Hierarchy

| Location | ATS Weight | Strategy |
|---|---|---|
| Skills section | Highest | Include all matching technical skills |
| Job titles | Very high | Ensure titles are searchable |
| Bullet points | High | Use keywords in natural context |
| Summary | Medium (varies) | Include 3-5 top keywords |
| Core Competencies | Medium-High | Leadership and soft skill keywords |
| Education | Low-Medium | Relevant certifications and coursework |

### Keyword Density
- Each keyword: 1-3 appearances across the resume
- Once in Skills + once in a bullet is ideal
- More than 3 of the same keyword looks like stuffing
- ATS does not reward repetition beyond a threshold

### Synonym Coverage
Cover multiple forms of the same skill:

- "Machine Learning" AND "ML"
- "Natural Language Processing" AND "NLP"
- "Amazon Web Services" AND "AWS"
- "Generative AI" AND "GenAI"
- "Large Language Model" AND "LLM"
- "Continuous Integration/Continuous Deployment" AND "CI/CD"

## Format Recommendations

### File Format
- **.docx**: Most reliably parsed across all ATS
- **.pdf**: Works in most modern systems; some older ones struggle
- Avoid: .pages, .odt, .rtf (inconsistent support)

### Section Headers — Standard vs. Risky

| Recognized | Risky |
|---|---|
| Professional Experience | Where I've Made Impact |
| Work Experience | Career Journey |
| Education | Academic Background |
| Technical Skills / Skills | Toolbox |
| Summary / Executive Summary | About Me |
| Certifications | Learning & Growth |

### Date Formats
- **Best**: "May 2018 – Feb 2024" or "05/2018 – 02/2024"
- **Acceptable**: "2018 – 2024"
- **Avoid**: "May '18 – Feb '24" (apostrophe can break parsers)

### Characters to Watch
- Em dash (—): Replace with regular dash (-) for safety
- Smart quotes: Replace with straight quotes
- Special bullets (■, ▪): Standard bullet (•) is usually fine
- Arrow characters (→, ←): Replace with "to" or standard punctuation
- Pipe (|): Generally safe for contact info separators

### Contact Information
- Place at the very top
- Include: name, phone, email, city/state, LinkedIn URL
- Avoid: physical address, photo

## Common Mistakes

### Over-Optimization
- Keyword stuffing (same term 10+ times)
- White-text hidden keywords (detectable, grounds for rejection)
- Listing every JD keyword regardless of actual experience
- Skills section with 50+ items

### Under-Optimization
- Only internal/company-specific terminology
- No Skills section at all
- Creative section headers parsers won't recognize
- Abbreviations without spelling out
- Missing exact JD phrasing

### The ATS-Human Balance
- ATS reads the Skills section and keyword placement
- Humans read the bullets and summary
- Skills section = keyword bank for ATS
- Bullets = evidence for humans
- Core Competencies = leadership signal for humans
- Some overlap between sections is fine and expected
