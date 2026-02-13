---
name: ai-writing-patterns
description: >
  This skill should be used when the user asks to "humanize text",
  "make this sound more human", "detect AI writing", "fix AI-sounding content",
  "copy edit for naturalness", "rewrite to sound less robotic", "check if this
  sounds AI-generated", or needs guidance on making written content feel
  authentically human while preserving its original tone.
version: 1.0.0
---

# AI Writing Pattern Detection & Humanization

Core knowledge for identifying AI-generated text patterns and rewriting content to sound naturally human.

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

**Overuse of "delve," "tapestry," "landscape," "nuanced," "multifaceted," "holistic," "robust," "streamline," "foster."** These words appear at far higher rates in AI text than in human writing. They are not banned words — they are signal words. One "nuanced" is fine. Three in two paragraphs is a tell.

**Excessive adverb/adjective stacking.** "Incredibly powerful and remarkably efficient" — AI loves doubling up modifiers. Humans usually pick one.

### 3. Rhetorical Tells

**Compulsive balance.** AI text hedges everything: "While X has benefits, it also has drawbacks." "On one hand... on the other hand." Human writing can be opinionated, one-sided, or deliberately provocative.

**Empty summarization.** Endings that restate the introduction almost verbatim: "In summary, X is a powerful tool that can help you achieve Y." Humans usually end with something new — an implication, a warning, a question, an anecdote.

**Unearned authority.** Declarative statements that sound confident but say little: "Effective communication is the cornerstone of any successful organization." This is AI filling space. A human making this claim would anchor it to something specific.

**Emotional flattening.** AI smooths over frustration, excitement, confusion, and surprise. Everything comes out at the same mild, professional temperature. Real writing has spikes — a short angry sentence, an aside in parentheses, a sudden shift in register.

### 4. Sentence-Level Tells

**Uniform sentence length.** AI tends to write sentences of roughly similar length (15-25 words). Human writing naturally varies: a 40-word sentence followed by a 4-word one.

**Passive voice overuse.** "It was determined that the project should be restructured" instead of "We decided to restructure the project." AI defaults to passive constructions, especially in business writing.

**Noun phrase pileup.** "The comprehensive implementation strategy development process" — AI chains nouns together where humans would break them apart or rephrase.

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

### Technique 7: Replace AI-Favorite Words

Consult `references/word-replacements.md` for a detailed substitution guide. The goal is not to ban words but to break the pattern of overuse.

### Technique 8: Fix the Ending

Cut any ending that merely restates the introduction. Replace it with one of: a specific next step, a question for the reader, a brief anecdote, a surprising implication, or nothing — just stop when the content is done.

## Output Format for Annotated Reviews

When showing changes with explanations, use this format:

### Analysis Summary
State how many AI tells were found and the overall confidence level (low / moderate / high) that the text is AI-generated. Note which categories of tells are most prominent.

### Annotated Changes
For each change, show:

**[AI Tell category: specific pattern]**
> Original text passage

→ Rewritten passage

*Why*: Brief explanation of what made the original sound AI-generated and how the rewrite addresses it.

### Rewritten Full Text
Present the complete rewritten text as a clean block, with no annotations, ready to copy and use.

## Additional Resources

- **`references/word-replacements.md`** — Detailed word and phrase substitution guide
- **`references/before-after-examples.md`** — Real examples of AI text humanized across different content types and tones
