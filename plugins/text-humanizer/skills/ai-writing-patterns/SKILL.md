---
name: ai-writing-patterns
description: >
  This skill should be used when the user asks to "humanize text",
  "make this sound more human", "detect AI writing", "fix AI-sounding content",
  "copy edit for naturalness", "rewrite to sound less robotic", "check if this
  sounds AI-generated", or needs guidance on making written content feel
  authentically human while preserving its original tone.
version: 1.1.0
---

# AI Writing Pattern Detection & Humanization

Core knowledge for identifying AI-generated text patterns and rewriting content to sound naturally human.

Research basis: The detection patterns in this skill are informed by peer-reviewed studies on LLM writing characteristics. See `references/research-sources.md` for the full citation list.

## Important: AI Tells Are a Moving Target

Specific word preferences shift across model versions. For example, certain vocabulary that was heavily overused by early ChatGPT versions became less frequent in later releases as models were retrained (Juzek & Ward, 2025). This means:

- **Structural and rhetorical patterns are more stable** than individual word tells — weight them more heavily in your analysis.
- **The word list is a snapshot**, not a permanent inventory. When scanning, treat word frequency as supporting evidence rather than primary proof.
- **New patterns emerge** as models evolve. Emoji overuse and certain rhetorical constructions have increased even as some vocabulary tells have decreased.

## Tone Preservation — The Cardinal Rule

Before making any changes, identify the original tone along these dimensions:

- **Formality**: casual ↔ formal
- **Energy**: subdued ↔ enthusiastic
- **Warmth**: detached ↔ personal
- **Authority**: tentative ↔ authoritative
- **Humor**: serious ↔ playful

Lock in these dimensions before rewriting. Every edit must stay within the same tonal range. If the original is a dry, formal memo, the rewrite must remain a dry, formal memo — just one that sounds like a specific human wrote it, not a language model.

## AI Writing Tells — What to Look For

### 1. Structural Tells

**Formulaic paragraph structure.** AI text tends to follow a predictable rhythm: topic sentence → elaboration → example → transition. Human writing is messier — sometimes the point arrives late, sometimes a paragraph is just one punchy sentence.

**Symmetrical lists and groupings.** AI loves groups of three, five bullet points with similar lengths, and balanced parallel constructions. Humans are less tidy. A list might have two items, or seven, with varying depth.

**Overly smooth transitions.** Phrases like "Moreover," "Furthermore," "It's worth noting that," "Additionally," and "In conclusion" used as paragraph openers signal AI. Humans use these sparingly, or skip transitions entirely, letting the reader make the connection.

**Predictable document arc.** Introduction → body → balanced conclusion with a call to action or forward-looking statement. Real writing often ends abruptly, trails off, circles back, or closes with a question.

### 2. Lexical Tells

**Register-inappropriate vocabulary.** AI tends to reach for slightly elevated words where simpler ones would be natural: "utilize" instead of "use," "facilitate" instead of "help," "leverage" instead of "take advantage of," "commence" instead of "start."

**Hedge stacking.** Phrases like "It's important to note that," "It should be mentioned that," "One might argue that" pile up in AI writing as a way to sound balanced. A human either commits to a claim or doesn't — they don't stack three qualifiers in one sentence.

**Filler affirmations.** "Great question!" "Absolutely!" "That's a really interesting point." These are conversation-padding phrases that AI inserts to seem engaged. Real writers skip them or use them only when genuinely struck by something.

**Overuse of high-signal vocabulary.** Words like "delve," "tapestry," "landscape," "nuanced," "multifaceted," "holistic," "robust," "streamline," and "foster" appear at far higher rates in AI text than in human writing. Research on 15.1 million biomedical abstracts found that "delves" appeared at 28x its expected frequency in 2024, and "underscores" at 13.8x (Kobak et al., 2025). These are not banned words — they become tells through frequency and clustering.

**Excessive adverb/adjective stacking.** "Incredibly powerful and remarkably efficient" — AI loves doubling up modifiers. Humans usually pick one.

**Copula avoidance.** AI systematically avoids simple "is," "has," and "are" constructions, replacing them with more elaborate phrasing. Research has documented a 10%+ decrease in copula usage in post-2023 academic writing (Reinhart et al., 2025). Watch for:
- "X is a leader in..." → AI writes "X serves as a leader in..." or "X stands as a leader in..."
- "The company has..." → AI writes "The company boasts..." or "The company features..."
- "This is important" → AI writes "This holds significance" or "This represents a cornerstone"

**Nominalization overuse.** Turning verbs and adjectives into abstract nouns: "we decided" becomes "our decision-making process," "they improved" becomes "the improvement initiative." LLMs use nominalizations at 1.5-2x the human rate (Reinhart et al., 2025).

### 3. Rhetorical Tells

**Compulsive balance.** AI text hedges everything: "While X has benefits, it also has drawbacks." "On one hand... on the other hand." Human writing can be opinionated, one-sided, or deliberately provocative.

**Empty summarization.** Endings that restate the introduction almost verbatim: "In summary, X is a powerful tool that can help you achieve Y." Humans usually end with something new — an implication, a warning, a question, an anecdote.

**Unearned authority.** Declarative statements that sound confident but say little: "Effective communication is the cornerstone of any successful organization." This is AI filling space. A human making this claim would anchor it to something specific.

**Emotional flattening.** AI smooths over frustration, excitement, confusion, and surprise. Everything comes out at the same mild, professional temperature. Real writing has spikes — a short angry sentence, an aside in parentheses, a sudden shift in register.

**The "not just X, but Y" construction.** AI frequently uses this rhetorical structure to add emphasis: "not just a tool, but a transformation," "not just efficient, but revolutionary." Analysis of hundreds of thousands of AI-generated messages found this pattern in approximately 6% of conversations by mid-2025 (Merrill et al., 2025). Occasional use is fine — repeated use in a single piece is a signal.

### 4. Sentence-Level Tells

**Uniform sentence length.** AI tends to write sentences of roughly similar length (15-25 words). Human writing naturally varies: a 40-word sentence followed by a 4-word one. Red flag: more than 3 consecutive sentences within ±5 words of each other.

**Passive voice overuse.** "It was determined that the project should be restructured" instead of "We decided to restructure the project." AI defaults to passive constructions, especially in business writing.

**Noun phrase pileup.** "The comprehensive implementation strategy development process" — AI chains nouns together where humans would break them apart or rephrase.

**Present participial phrase overuse.** AI heavily favors "-ing" constructions at the start of sentences or as connective tissue: "Offering a range of solutions, the firm..." "Building on years of experience, the team..." "Combining tradition with innovation, the product..." When these appear more than once or twice in a short piece, they create a recognizable AI cadence. Human writers vary their openings: subject-first, prepositional phrases, occasional fragments.

### 5. Style & Formatting Tells

**Em dash overuse.** AI uses em dashes at significantly higher rates than human writers, substituting them where a comma, colon, period, semicolon, or parenthetical would be more natural. More than 1-2 em dashes per 500 words is a signal. Most AI em dashes should be replaced with the punctuation mark that fits the grammatical relationship: commas for light pauses, colons for introductions, parentheses for asides, periods for full stops. See `references/punctuation-patterns.md` for detailed guidance.

**Boldface overuse.** AI bolds key terms, list headers, and emphasis phrases far more than a human editor would. The result is a "highlight everything" effect where nothing actually stands out. In flowing prose, bold should be rare. In lists, not every item needs a bold header.

**Redundant inline headers.** AI creates list items formatted as `**Label:** Explanation of the label` where the bold header just restates or summarizes what follows. Human writers either use a header OR explain — not both redundantly.

**Title case in headings.** AI defaults to capitalizing every significant word in headings ("The Future Of Sustainable Energy Solutions"). Most modern style guides and publications use sentence case ("The future of sustainable energy solutions"). Title case in informal or web content is a formatting tell.

**Emoji in professional content.** Analysis of over 300,000 AI-generated messages found that by mid-2025, 70% contained at least one emoji, with certain emojis (green check marks, brain symbols) appearing 10-11x more frequently than in human text (Merrill et al., 2025). Emoji in casual social media is normal; emoji in business emails, reports, or professional articles is a tell.

**Uniformly formatted lists.** AI creates lists where every item has the same length, structure, and punctuation. Human-created lists are messier — items vary in length, some have sub-points, some are sentence fragments while others are full sentences.

### 6. Content Inflation Tells

**Significance inflation.** AI routinely elevates routine subjects with language reserved for momentous occasions. A minor product update becomes "a pivotal shift in how organizations approach..." A company founding story becomes "a transformative journey that would reshape the industry." The fix: match the language to the actual scale of the thing being described.

**Vague attributions.** "Experts agree," "Research indicates," "Industry leaders recognize," "Studies have shown" — authoritative framing that names no one specific. A human writer either cites a specific source or drops the attribution and states the claim directly.

**The adversity-to-triumph arc.** "Despite significant challenges, [subject] has continued to demonstrate remarkable resilience and emerge stronger than ever." AI applies this narrative formula to everything from company histories to product descriptions to city profiles. Real writing acknowledges that sometimes the challenges won, or the outcome is mixed, or the story is still unresolved.

**Promotional vocabulary clusters.** Words like "breathtaking," "nestled," "vibrant," "bustling," "rich tapestry," and "hidden gem" cluster heavily in AI-generated geographic, cultural, and travel descriptions. Each word individually is fine; the cluster pattern is the tell.

### 7. Communication Artifacts

These are traces of conversational AI interaction that leak into content when someone pastes AI-generated text without cleaning it:

**Chatbot closers.** "I hope this helps!" "Let me know if you have any questions!" "Feel free to reach out if you need anything else!" These are conversational sign-offs that don't belong in standalone content.

**Metacommentary.** "That's a great question!" "This is an important topic to explore." "You raise an excellent point." These phrases comment on the question rather than answering it — a hallmark of conversational AI padding.

**Disclaimer language.** "As of my last update..." "Based on available information..." "While I don't have access to the most recent data..." These reveal the text was generated in a conversation rather than written as standalone content.

**Knowledge framing.** "There are several key factors to consider:" "Let me break this down:" "Here's what you need to know:" — instructional framing that makes sense in a conversation but reads oddly in a blog post, email, or report.

## Signal Strength Guide

Not all tells carry equal weight. Use this to calibrate your confidence:

**High signal — one occurrence is meaningful:**
- Chatbot closers or disclaimer language in standalone content
- "In today's fast-paced digital landscape" or equivalent clichéd openers
- Significance inflation on clearly mundane topics
- Filler affirmations ("Great question!")

**Medium signal — look for 2+ occurrences or clustering:**
- Em dash overuse (check frequency across the full text)
- Hedge stacking
- Modifier doubling
- Participial phrase openings
- "Not just X, but Y" constructions
- Copula avoidance patterns

**Low signal — only meaningful as part of a broader pattern:**
- Individual uses of "ensure," "key," "crucial," "comprehensive"
- Single passive voice construction
- One smooth transition phrase
- Title case in a heading (could be house style)

## Humanization Techniques

### Technique 1: Break the Pattern

Vary paragraph lengths dramatically. Follow a 4-sentence paragraph with a 1-sentence paragraph. Start a paragraph with "But" or "And." End one mid-thought and pick it up later.

### Technique 2: Choose Specific over Generic

Replace abstract language with concrete details. "Effective tools" → name the tool. "Various stakeholders" → name them or describe them. "Significant improvements" → cite a number or describe what changed.

### Technique 3: Cut the Scaffolding

Remove transitional phrases that exist only to connect paragraphs. If the connection between two paragraphs isn't obvious without a transition, the paragraphs might need reordering — not glue.

Remove topic sentences that merely announce what the paragraph will discuss. Jump straight into the substance.

### Technique 4: Let Personality Leak Through

Add an aside, a parenthetical, a dash-interrupted thought. Use a contraction. Reference something specific to the author's context. Insert a short, opinionated sentence. Let a sentence start with "Look," or "Here's the thing" if the tone permits it.

### Technique 5: Embrace Asymmetry

If a list has five items, consider whether three of them are really the same point. Cut to three. Or expand one item that deserves more space and leave the others short. Not everything needs equal airtime.

### Technique 6: Vary the Rhythm

Alternate between long, compound sentences and short declarative ones. Use fragments intentionally. Start a sentence with a conjunction. Let the cadence be unpredictable.

Target: avoid more than 3 consecutive sentences within ±5 words of each other. After a long compound sentence, a 3-5 word sentence or fragment is one of the strongest humanizing moves.

### Technique 7: Replace AI-Favorite Words

Consult `references/word-replacements.md` for a detailed substitution guide. The goal is not to ban words but to break the pattern of overuse.

### Technique 8: Fix the Ending

Cut any ending that merely restates the introduction. Replace it with one of: a specific next step, a question for the reader, a brief anecdote, a surprising implication, or nothing — just stop when the content is done.

### Technique 9: Restore the Copula

Where AI has replaced simple "is," "has," or "are" with elaborate alternatives, put the simple word back. "Serves as a hub for" → "is a hub for." "Boasts an impressive array of" → "has." "Stands as a testament to" → "shows" or just "is proof of." Simple verbs are not weak — they are clear.

### Technique 10: Inject Genuine Voice

Pattern removal alone produces clean but still generic text. The second step is actively adding human characteristics:
- State a genuine opinion or take a mild side, rather than hedging everything to perfect neutrality
- Reference a specific experience, constraint, or context the reader would recognize
- Acknowledge mixed feelings or unresolved tension — AI resolves everything neatly; humans don't always
- Leave one thread deliberately unresolved or raise a question at the end instead of wrapping up with a bow

### Technique 11: Fix the Formatting

Strip unnecessary bold from flowing prose. Convert redundant inline headers to plain sentences. Replace title case headings with sentence case. Remove emoji from professional content. Let list items vary in length and structure.

Replace em dashes with context-appropriate punctuation — see `references/punctuation-patterns.md` for the decision framework.

## Output Format Options

When using `/humanize`, offer the user a choice of output format before beginning the rewrite:

### Option A: Inline Mode (default)

The current format — full annotated walkthrough followed by clean text:

**Analysis Summary**
State how many AI tells were found and the overall confidence level (low / moderate / high). Note which categories are most prominent.

**Annotated Changes**
For each change, show:

**[AI Tell category: specific pattern]** ⚑ signal strength
> Original text passage

→ Rewritten passage

*Why*: Brief explanation of what made the original sound AI-generated and how the rewrite addresses it.

**Rewritten Full Text**
Present the complete rewritten text as a clean block, with no annotations, ready to copy and use.

### Option B: Diff Mode

A compact format for users who want to see only what changed, with reasons alongside. Better for long documents.

**Analysis Summary**
Same as inline mode — tell count, confidence, prominent categories.

**Changes**

```
① [Lexical: copula avoidance] ⚑ medium
- The platform serves as a central hub for team collaboration.
+ The platform is a central hub for team collaboration.
  ↳ Restored simple "is" — AI replaced the copula with "serves as"

② [Style: em dash overuse] ⚑ medium
- The results — which exceeded all expectations — were announced Tuesday.
+ The results, which exceeded all expectations, were announced Tuesday.
  ↳ Replaced em dashes with commas; this is a non-restrictive clause, not an interruption

③ [Rhetorical: significance inflation] ⚑ high
- This represents a pivotal transformation in how organizations approach data.
+ This changes how the team handles data reporting.
  ↳ Matched language to actual scope — a reporting tool update, not a paradigm shift

④ [Communication artifact: chatbot closer] ⚑ high
- I hope this helps! Let me know if you have any questions.
+ [removed]
  ↳ Conversational sign-off doesn't belong in a standalone document
```

**Rewritten Full Text**
Same as inline mode — clean block, no annotations.

## Genre-Aware Detection

Different content types have different primary tells. When analyzing text, first identify the genre and weight your scan accordingly:

- **Business/professional** — Prioritize: transition scaffolding, modifier stacking, empty summarization, chatbot closers, em dash overuse
- **Creative/personal** — Prioritize: emotional flattening, personality absence, formulaic structure, the adversity arc, uniform rhythm
- **Technical** — Prioritize: passive voice, noun phrase pileup, copula avoidance, nominalization, participial phrases
- **Marketing/promotional** — Prioritize: empty superlatives, significance inflation, promotional vocabulary clusters, vague attributions
- **Academic** — Prioritize: nominalization overuse, copula avoidance, high-signal vocabulary, vague citations, participial phrases

## Additional Resources

- **`references/word-replacements.md`** — Detailed word and phrase substitution guide
- **`references/before-after-examples.md`** — Real examples of AI text humanized across different content types and tones
- **`references/punctuation-patterns.md`** — Em dash, bold, and formatting pattern detection and fix guide
- **`references/research-sources.md`** — Academic citations backing the detection patterns
