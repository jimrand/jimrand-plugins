# Resume AI Patterns

Detecting AI-generated writing in resumes, organized by four categories of tells.

## Structural Tells

### Formulaic Paragraph Structure
AI summaries follow a predictable pattern: [Bold claim] then [Supporting detail], repeated identically. Human summaries vary their approach — leading with a number, a story, or a short declarative statement.

**Signal**: Every sentence in a section follows the same arc (noun phrase opener, comma, elaboration).

### Symmetrical Groupings
AI loves groups of three with parallel structure. When every list has exactly three items with identical grammatical form, the rhythm becomes mechanical.

**Signal**: Repeating groups of three with identical structure throughout the resume.

### Uniform Bullet Length
Human bullets naturally vary — some are one line, some are three. AI produces bullets that are all approximately the same length.

**Signal**: All bullets in a section are within 20% of the same word count.

### Predictable Section Balance
AI gives each role roughly the same emphasis regardless of relevance. A human weights recent and relevant roles heavily and condenses older ones.

**Signal**: A 15-year-old role has the same number of bullets as the current role.

## Lexical Tells

### AI-Favorite Power Verbs
These verbs appear far more often in AI-generated resumes:

- **Spearheaded** — AI's default for "led"
- **Championed** — AI's default for advocacy
- **Orchestrated** — AI's default for coordination
- **Pioneered** — AI's default for anything new
- **Revolutionized** — hyperbolic in almost any corporate context

One of these is fine. Three or more signals generation.

### Resume Cliche Phrases
These appear overwhelmingly in AI-generated resumes:

- "Proven track record of delivering..."
- "Results-oriented professional..."
- "Passionate about [domain]..."
- "Self-motivated team player..."
- "Dynamic and detail-oriented..."
- "Leveraged best practices to..."
- "In a fast-paced environment..."
- "Exceeded expectations consistently..."
- "Trusted advisor to senior leadership..."

Three or more of these in the same resume is a strong AI signal.

### Modifier Stacking
AI stacks adjectives and adverbs where one would do:

- "Highly innovative and cutting-edge"
- "Truly exceptional and outstanding"
- "Comprehensive and thorough"
- "Significant and substantial"
- "Rigorous and meticulous"

**Fix**: Keep the strongest modifier, cut the rest.

### Buzzword Density
AI packs multiple buzzwords into single phrases:

- "Strategic implementations of generative AI solutions"
- "Data-driven optimization through cross-functional synergies"
- "Innovative approaches to digital transformation initiatives"

**Signal**: Three or more buzzwords within a single noun phrase.

### AI Connector Words
Resume-specific AI connectors that signal generation when they appear repeatedly:

- "Enabling..." (trailing clause)
- "Resulting in..."
- "Driving [vague noun]..."
- "Delivering [vague noun]..."
- "Through strategic [noun]..."
- "By leveraging [noun]..."

## Rhetorical Tells

### Unearned Authority
AI makes bold claims without evidence:

- "Proven expertise in..." — prove it with a number
- "Demonstrated ability to..." — demonstrate it with an example
- "Deep understanding of..." — show the understanding through work
- "Exceptional ability to..." — let results be exceptional

**Fix**: Cut the claiming phrase, lead with evidence.

### Vague Authority Endings
AI bullets start strong (specific work) and end weak (vague impact):

- "...directly influencing C-suite strategic decisions"
- "...driving organizational excellence"
- "...aligning teams with business objectives"
- "...delivering measurable business impact"
- "...establishing a foundation for future growth"

**Fix**: Name the specific decision, outcome, or metric. If you can't, cut the ending.

### Empty Summarization
AI adds summary sentences that restate what was already said:

- "This resulted in significant improvements across the organization."
- "These efforts collectively contributed to the team's success."

**Fix**: Cut the summary sentence. The bullets already made the point.

### Emotional Flattening
AI-generated resumes have no personality. Every sentence sits at the same mild, impressive temperature. There's no hint of what the person cares about or what distinguishes their voice.

**Signal**: The resume could describe anyone in the field with similar tenure.

## Sentence-Level Tells

### Uniform Sentence Length
Human writing has rhythm — long followed by short, fragments, punchy closers. AI produces sentences all roughly the same length.

**Signal**: All sentences in a section are 20-30 words with no variation.

### Passive Voice Overuse
Some passive voice is normal in resumes, but AI overuses it:

- "A new system was designed and implemented" vs. "Built a new system"
- "Key improvements were identified" vs. "Identified three areas for improvement"

**Signal**: More than 30% of bullets use passive construction.

### Noun Phrase Pileups
AI chains multiple words before the main noun:

- "Advanced predictive analytics capabilities"
- "Comprehensive enterprise-wide digital transformation initiatives"
- "Executive-level strategic recommendation framework"

**Signal**: Four or more words stacked before a noun.

## Calibration Notes

### What NOT to Flag
Some patterns are standard resume conventions, not AI tells:
- Fragment-style openers ("Led a team of...") — normal resume style
- Action verb starts on every bullet — expected
- Quantified results — humans do this too
- Industry jargon — appropriate in context

### Career Level Considerations
- **Entry-level**: AI tells are common because candidates have less substance. Flag but be generous.
- **Mid-level**: Most common level for AI generation. Apply full scrutiny.
- **Senior/Executive**: Some formality that looks AI-generated is appropriate. "Established a governance framework" is fine for a VP. Focus on substance over style at this level.

## Style & Formatting Tells

### Em Dash Overuse
AI uses em dashes (—) where commas, colons, periods, or parentheses would be more natural. In resumes, this most commonly appears in summary paragraphs and cover letters.

**Signal**: More than 1 em dash per 200 words in resume text.

**Fix**: Replace each em dash with the punctuation that fits the grammatical relationship:
- Non-restrictive aside → commas or parentheses
- Introducing a list or explanation → colon
- Connecting independent clauses → period or semicolon
- Dramatic pause (rare in resumes) → keep the em dash

See punctuation-patterns.md for the full decision framework.

### Bold Overuse
AI bolds key terms, list headers, and emphasis phrases excessively. In resumes, this often appears as every skill or achievement term bolded inline.

**Signal**: More than 3 bolded terms per section in flowing text (skills lists with bold headers are acceptable).

### Uniformly Formatted Bullets
AI creates bullets where every item has identical length, structure, and opening pattern. Human resume bullets naturally vary — some are one line, some are two, some start with different verb types.

**Signal**: All bullets in a role within 20% of the same word count AND identical grammatical opening.

## Content Inflation Tells

### Significance Inflation
AI elevates routine work with language reserved for major achievements. A process improvement becomes "a transformative initiative." A tool migration becomes "a pivotal shift in organizational capability."

**Signal**: Language scale dramatically exceeds the actual scope of the work described.

**Fix**: Match language to actual scope. Let metrics prove significance rather than adjectives.

### Vague Attributions
"Industry best practices," "proven methodologies," "widely recognized frameworks" — authoritative framing that names nothing specific.

**Signal**: Authority claims without specific named sources, tools, or frameworks.

**Fix**: Name the specific practice, methodology, or framework. Or cut the attribution.

## Communication Artifacts

These should NEVER appear in a resume. Flag with high confidence.

- "I hope this helps!"
- "Feel free to reach out"
- "Let me break this down"
- "Here's what you need to know"
- "As of my last update"
- "Based on available information"

These most commonly leak into cover letters and LinkedIn summaries when AI-generated text is pasted without cleanup.

## Signal Strength Guide

Not all tells carry equal weight. Use this to calibrate confidence:

**High signal — one occurrence is meaningful:**
- Communication artifacts (chatbot closers, disclaimer language) in resume or cover letter
- "In today's fast-paced [industry] landscape" or equivalent clichéd openers
- Significance inflation on clearly entry/mid-level work
- Filler affirmations ("Great question!" in a cover letter)
- "Proven track record of..." (the most common AI resume cliché)

**Medium signal — look for 2+ occurrences or clustering:**
- Em dash overuse (check frequency across full document)
- Copula avoidance patterns
- Modifier stacking
- Participial phrase openings on bullets
- "Not just X, but Y" constructions
- Vague authority endings

**Low signal — only meaningful as part of a broader pattern:**
- Individual uses of "ensure," "key," "strategic," "comprehensive"
- Single passive voice construction
- One smooth transition phrase
- One use of "spearheaded" (it's a tell in clusters, fine alone)
