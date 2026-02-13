# Research Sources

The detection patterns in this skill are informed by the following peer-reviewed studies and published analyses. Specific quantified claims in SKILL.md are attributed to their source.

## Academic Papers

**Juzek, T.S. & Ward, Z.B. (2025).** "Why Does ChatGPT 'Delve' So Much? Exploring the Sources of Lexical Overrepresentation in Large Language Models." Findings of the Association for Computational Linguistics: ACL 2025. arXiv:2412.11385.
- Identified 21 words with abnormal frequency spikes in AI-generated text
- Found that RLHF (Reinforcement Learning from Human Feedback) is the primary cause of lexical overrepresentation
- Documented temporal shift: word preferences change across model versions

**Kobak, D., González-Márquez, R., Horváth, E., & Lause, J. (2025).** "Delving into AI-assisted writing in biomedical publications through excess vocabulary." Science Advances, 11(27). doi:10.1126/sciadv.adt3813.
- Analyzed 15.1 million PubMed abstracts (2010-2024)
- Found 454 excess vocabulary words in 2024; 66% were verbs, 14% adjectives — nearly all style words, not content nouns
- Top overrepresented words by ratio: "delves" (28x), "underscores" (13.8x), "showcasing" (10.7x)
- Estimated at least 13.5% of 2024 biomedical abstracts show markers of LLM processing

**Reinhart, A., Markey, B., Laudenbach, M., Pantusesu, K., Yurko, R., Weinberg, G., & Brown, D.W. (2025).** "Do LLMs write like humans? Variation in grammatical and rhetorical styles." Proceedings of the National Academy of Sciences, 122(8). doi:10.1073/pnas.2422455122.
- Found LLMs use nominalizations at 1.5-2x the human rate
- Documented 10%+ decrease in "is" and "are" usage in post-2023 academic writing
- Specific words used at extreme rates: "camaraderie" and "tapestry" at ~150x, "palpable" and "intricate" significantly elevated

**Geng, M. & Trotta, R. (2025).** "Human-LLM Coevolution: Evidence from Academic Writing." Findings of the Association for Computational Linguistics: ACL 2025. arXiv:2505.07784.
- Documented measurable shifts in academic writing style since widespread LLM adoption

**Dugan, L., Hwang, A., Thilk, F., et al. (2024).** "RAID: A Shared Benchmark for Robust Evaluation of Machine-Generated Text Detectors." Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics. arXiv:2405.07940.
- Established benchmarks for evaluating AI text detection accuracy

## Published Analyses

**Merrill, J.B., Chen, S.Y., & Kumer, E. (2025).** "What are the clues that ChatGPT wrote something? We analyzed its style." The Washington Post, November 13.
- Analyzed 37,929 ChatGPT conversations (328,744 messages, May 2024-July 2025)
- Found specific emoji used 10-11x more than humans; 70% of messages contained emoji by mid-2025
- Documented "not just X, but Y" construction in 6% of conversations
- Tracked temporal shifts in vocabulary preferences

**Belcher, W.L. (2025).** "10 Ways AI is Ruining Your Students' Writing." Chronicle of Higher Education, September 16.
- Identified "Polonius problem" (AI states the obvious) and "Windbag problem" (grammatically correct but substantively empty text)
- Noted that AI repetition penalties fragment writing coherence rather than improving it

**Rudnicka, K. (2025).** "Each AI chatbot has its own, distinctive writing style — just as humans do." Scientific American, July 9.
- Documented that different AI models produce distinct stylistic fingerprints (idiolects)

## How These Inform the Skill

- **Lexical tells** (Section 2): Word lists derived from Kobak et al. and Reinhart et al. findings on overrepresented vocabulary
- **Copula avoidance** (Section 2): Directly informed by Reinhart et al. finding on decreased "is"/"are" usage
- **Nominalization overuse** (Section 2): Based on Reinhart et al. 1.5-2x rate finding
- **"Not just X, but Y"** (Section 3): Based on Merrill et al. 6% conversation frequency finding
- **Emoji patterns** (Section 5): Based on Merrill et al. 10-11x overuse and 70% message inclusion findings
- **Temporal drift warning** (introduction): Based on Juzek & Ward finding that RLHF causes vocabulary preferences to shift across model versions
