# Document Type Detection Signals

Quick-reference table for identifying resume/CV types from structural and content signals.

## Detection Signal Table

| Signal | Likely Type | Confidence |
|--------|-------------|------------|
| GS grade/series number (e.g., GS-13) | Federal resume | High |
| Supervisor name + phone for each role | Federal resume | High |
| Hours worked per week listed | Federal resume | High |
| Salary history per role | Federal resume | High |
| KSA statements or "Specialized Experience" language | Federal resume | High |
| USAJOBS vacancy announcement number | Federal resume | High |
| Security clearance details | Federal resume | Medium (also defense contractors) |
| Publications section with academic citations | Academic CV | High |
| Grants section with funding agencies | Academic CV | High |
| Teaching section with course listings | Academic CV | High |
| Conference presentations section | Academic CV | Medium |
| Research statement or teaching philosophy referenced | Academic CV | High |
| No page limit / 5+ pages with scholarly focus | Academic CV | Medium |
| Bar admissions near top of document | Legal resume | High |
| Clerkship listings | Legal resume | High |
| Legal citations in publications | Legal resume | High |
| USMLE scores and step dates | Medical CV | High |
| Clinical rotations section | Medical CV | High |
| ERAS formatting conventions | Medical CV | High |
| Hobbies/interests section (medical context) | Medical CV | Medium |
| Education section above experience (with MBA/GPA) | Consulting resume | Medium |
| GPA displayed prominently (3.5+) | Consulting resume | Medium |
| Interests paragraph (non-hobby context) | Consulting resume | Medium |
| One page with 10+ years experience | Consulting or IB/PE resume | Medium |
| Deal experience section (transactions, LBO, DCF) | IB/PE resume | High |
| Transaction type and deal size listed | IB/PE resume | High |
| GitHub profile link in header | Tech resume | High |
| Projects section with repository links | Tech resume | High |
| Technical skills section with specific stack | Tech resume | Medium |
| Portfolio URL in header | Creative/UX resume | High |
| Case study references | Creative/UX resume | Medium |
| Visual/graphic design elements | Creative resume | Medium |
| Branding statement (not summary) | Executive resume | Medium |
| Branding title different from current role | Executive resume | Medium |
| Board memberships section | Executive resume | High |
| Professional Educator License + endorsements | Education resume | High |
| Grade-level endorsements (K-6, 5-12) | Education resume | High |
| Professional development section | Education resume | Medium |
| MOS/AFSC code | Military transition | High |
| Military rank in job titles | Military transition | High |
| DD-214 reference | Military transition | High |
| CFRE or CGWS certification | Nonprofit resume | High |
| Fundraising/donor metrics | Nonprofit resume | Medium |
| Organization descriptions in brackets | Nonprofit resume | Medium |
| Journeyman/apprenticeship credentials | Skilled trades | High |
| Trade certifications (HVAC, welding, electrical) | Skilled trades | High |
| Safety record section | Skilled trades | Medium |
| Europass template structure (blue/white, single-column) | Europass CV | High |
| CEFR language ratings (A1-C2) | EU format | High |
| Photo included | European (likely German or French) | Medium |
| Date of birth included | European (likely German) | Medium |
| Nationality field | European format | Medium |
| "Personal Statement" section (4-6 sentences) | UK CV | Medium |
| A4 paper formatting cues | European format | Low |
| dd/mm/yyyy date format | European format | Low |

## Ambiguous Cases

Some signals overlap across types:

- **Security clearance** — Could be federal resume OR defense contractor private-sector resume. Look for other federal signals (GS grade, supervisor phone) to disambiguate.
- **Publications section** — Could be academic CV OR a senior industry researcher. Check for grants, teaching, and conference sections to disambiguate.
- **Education at top** — Could be consulting resume, recent graduate, OR academic CV. Check for GPA display and one-page format (consulting) vs. length and scholarly content (academic).
- **One page strict** — Could be consulting, IB/PE, legal, or early-career standard. Use content signals to narrow.
- **Certifications-heavy** — Could be education, trades, IT, or nonprofit. Check certification types to disambiguate.

When ambiguous, present the top 2 candidates to the user and ask them to choose.

## Type → Expectations Quick Reference

| Type | Expected Length | ATS System | Key Sections | AI Detection Notes |
|------|---------------|------------|--------------|-------------------|
| Standard US | 1-2 pages | Standard ATS (Taleo, Workday, etc.) | Summary, Experience, Education, Skills | Standard detection applies |
| Federal | 3-5 pages (may be 2 under Merit Hiring Plan) | USAJOBS HR scoring (70-100 point scale) | All standard + supervisor info, hours, salary, KSAs | KSA mirroring looks repetitive but is REQUIRED — do not flag. Formal government language is expected. |
| Academic CV | No limit (5-20+ pages) | Not applicable — committee review | Appointments, Publications, Grants, Teaching, Service | Formal academic language overlaps with AI tells — calibrate heavily. Nominalizations may be disciplinary convention. |
| Legal | 1 page (exceptions for public interest) | Limited — most legal hiring is direct | Bar Admissions, Education, Experience, Publications | Precise legal language is expected — do not flag formal constructions. |
| Medical CV | 3-5 pages | ERAS system | USMLE, Rotations, Research, Volunteer, Hobbies | Clinical terminology is expected. Hobbies section is standard — do not flag. |
| Consulting | 1 page strict | Standard ATS | Education (top), Experience, Interests | Education-at-top is correct for consulting. GPA display is expected. |
| IB/PE | 1 page strict | Standard ATS | Education, Experience, Deal Experience | Transaction-specific language is expected. |
| Tech | 1-2 pages | Standard ATS (with tech-specific keywords) | Summary, Experience, Projects, Skills, Education | GitHub/portfolio links expected. Projects section is standard. |
| Executive | 2-3 pages | Standard ATS or direct/recruiter | Branding Statement, Core Competencies, Experience, Board | Branding statements are not summaries — different evaluation criteria. |
| Creative/UX | 1 page (+ portfolio) | Often bypasses ATS | Summary, Experience, Skills, Portfolio link | The resume itself is secondary to the portfolio. |
| Education K-12 | 1-2 pages | Varies (many districts use ATS) | Certifications, Education, Teaching Experience, PD | Licensure section is critical and leads. |
| Nonprofit | 1-2 pages | Standard ATS | Summary, Experience (with org descriptions), Fundraising | Mission-alignment language is expected, not AI inflation. |
| Military transition | 1-2 pages | Standard ATS | Summary, Translated Experience, Skills, Education | Translation from military jargon is the primary challenge. Functional format may be appropriate. |
| Skilled trades | 1-2 pages | Limited ATS | Certifications, Experience, Skills, Safety | Certifications lead. Simple format expected. |
| Europass | 2-3 pages | Not applicable — standardized template | About Me, Experience, Education, Languages, Digital Skills | Template-mandated structure — do not flag formatting. CEFR ratings are required. |
| UK CV | 2 pages | Varies | Personal Statement, Experience, Education, Skills | Personal statement is expected. British spelling required. |
| German CV | 2-3 pages | Varies | Photo, Personal Info, Education, Experience, Skills | Photo and DOB are expected — do not flag as inappropriate. |
