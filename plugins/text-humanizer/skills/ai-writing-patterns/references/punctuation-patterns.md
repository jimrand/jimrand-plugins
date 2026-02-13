# Punctuation & Formatting Pattern Guide

## Em Dash Overuse

AI text uses em dashes (—) at rates far above typical human writing. The em dash becomes a universal connector where a human writer would choose context-appropriate punctuation.

### Detection

Count em dashes across the full text. Guidelines:

- **0-1 per 500 words**: Normal human range. No action needed.
- **2-3 per 500 words**: Borderline. Check whether each em dash is the best punctuation choice.
- **4+ per 500 words**: Strong AI signal. Most need replacing.

### Why AI Overuses Em Dashes

The em dash is grammatically flexible — it can replace commas, colons, parentheses, semicolons, and periods. Because it's valid in so many contexts, AI defaults to it rather than choosing the more precise punctuation for each situation. The result is text where every aside, every elaboration, and every mid-sentence pivot uses the same mark.

### Replacement Decision Framework

Ask: what is the grammatical relationship between the text before and after the em dash?

**If it's a non-restrictive aside (extra info that could be removed):**
- Use commas or parentheses
- AI: "The team — which had been working remotely — delivered on time."
- Fix: "The team, which had been working remotely, delivered on time."

**If it's introducing a list or explanation:**
- Use a colon
- AI: "We need three things — time, budget, and people."
- Fix: "We need three things: time, budget, and people."

**If it's a dramatic pause or shift in thought:**
- This is the one case where an em dash is often the right choice. Keep it if the interruption is genuinely abrupt or emphatic.
- "She opened the envelope — and found nothing inside."
- This is appropriate. The em dash conveys surprise.

**If it's connecting two independent clauses:**
- Use a period or semicolon
- AI: "The project missed its deadline — the team regrouped and tried again."
- Fix: "The project missed its deadline. The team regrouped and tried again."

**If it's a simple attribution or clarification:**
- Use a comma or restructure
- AI: "The CEO — Jane Park — announced the change."
- Fix: "The CEO, Jane Park, announced the change."

### A Note on En Dashes vs. Em Dashes

En dashes (–) are for ranges (2020–2024, pages 5–10) and compound adjectives (New York–based). Em dashes (—) are for interruptions, asides, and emphasis. AI sometimes uses em dashes where en dashes belong, particularly in date ranges.

## Bold Overuse

### Detection

Look for bold formatting that serves no editorial purpose:

- **Every list item has a bold header** — especially when the header restates the content
- **Key terms bolded inline** — "We use **agile methodology** to deliver **high-quality** results for **enterprise clients**"
- **Emphasis bolding** — bolding adjectives or phrases for emphasis where italics or no formatting would be more appropriate

### Replacement Guidance

- In flowing prose: remove most bold. Use italics sparingly if emphasis is truly needed.
- In lists: bold headers are acceptable when they serve as scannable labels (not when they repeat what follows).
- In technical docs: bold for UI elements, commands, and truly critical warnings. Not for every term.

**Redundant inline headers** — a specific bold pattern where the header and the content say the same thing:

- AI: "**Performance:** Performance improved by 20% over the previous quarter."
- Fix: "Performance improved by 20% over the previous quarter." (cut the header)
- Or: "**Performance:** Up 20% over Q3." (make the content add something new)

## Title Case vs. Sentence Case

### Detection

AI defaults to capitalizing every significant word in headings:

- "The Future Of Sustainable Energy Solutions" (title case)
- vs. "The future of sustainable energy solutions" (sentence case)

Title case is not wrong — it's a style choice. But AI applies it uniformly, even in casual blog posts, internal docs, and README files where sentence case is more common.

### When to Flag

- **Flag if**: The content is informal, web-based, or internal, and every heading uses title case
- **Don't flag if**: The content follows a specific style guide that requires title case (AP, Chicago in some contexts)
- **Don't flag if**: Only one or two headings use title case (might be intentional)

## Uniformly Formatted Lists

### Detection

AI creates lists where every item has identical structure:

- Same length (within a few words)
- Same grammatical opening (all start with a verb, or all start with a noun)
- Same punctuation (all end with periods, or none do)
- Same bold/formatting treatment

Human lists are messier. Some items are long, some are fragments. One might have a sub-point. Punctuation is inconsistent.

### Replacement Guidance

Don't intentionally make lists worse. But when rewriting, let items find their natural length rather than forcing uniformity. If one point needs two sentences, give it two sentences. If another is three words, let it be three words.
