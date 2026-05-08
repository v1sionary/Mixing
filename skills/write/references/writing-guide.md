# Writing guide

Use this reference for engineering documents that need accuracy, structure, and direct prose.

## Core goal

Write documents that help engineers understand the problem space, make decisions, and move work forward.

Keep prose direct, structured, and low-fluff. Favor stable boundaries, concrete judgment criteria, and executable framing over polished but empty exposition.

## Boundary and abstraction level

State what the document solves and what it does not solve.

- Define the object under discussion before describing details.
- Keep each section at one abstraction level.
- Do not mix requirements analysis with implementation detail unless the document explicitly covers both.
- Do not mix standards with vague strategy language.
- Do not explain a subsystem before defining its role and boundary.
- Mark incomplete facts with `TBD`, `not covered here`, `out of scope`, `pending confirmation`, or `not applicable`.

## Structured reasoning

Write to help the reader judge, not just receive information.

- Define the object first.
- Decompose by stable dimensions.
- Put the conclusion before the explanation.
- Follow abstract statements with a concrete handle: example, counterexample, table, checklist, rule, risk, next step, code, or pseudo-code.
- Prefer lists when multiple conditions or decisions exist and each item is independently meaningful. Use numbered lists only for real order: priority, sequence, procedure, ranking, or dependency. Use bullets for parallel items that readers need to scan. When items form one continuous argument or are tightly coupled, use prose instead of a list.
- When a section has 4+ single-sentence bullets that relate tightly, consider merging them into a single paragraph. Use commas by default; use semicolons only when items contain internal commas. Over-bulleted sections read like slides, not prose.
- Use tables when comparing categories, options, roles, states, or constraints.
- Use short code or pseudo-code only when it clarifies a mechanism.
- When introducing a specific case or example, state what it represents — which design choice, tradeoff, or category — before diving into details.
- When listing multiple terms, state why they matter to the reader. A bare term list reads like a roll call, not an argument.

### Summaries

Summaries serve one of two jobs: preview or recap. Pick one per summary.

- Preview: tell the reader what the document will cover without revealing every conclusion.
- Recap: state what was covered and what was concluded.
- Do not mix preview framing with conclusive claims in the same paragraph.
- Default to 2–3 sentences. Cover enough to orient the reader without restating the body.

## Engineering prose

Use plain engineering language.

- Prefer direct statements over soft framing.
- Prefer plain engineering verbs over marketing verbs.
- Prefer explicit tradeoffs over fake balance.
- Prefer naming the real problem over hiding it behind process language.
- Prefer repeatable structure over clever prose.
- Prefer honest incompleteness over fabricated completeness.

Useful sentence patterns:

- `Use X to achieve Y.`
- `X matters because Y.`
- `This section covers X and excludes Y.`
- `The risk is X; the control is Y.`
- `Do X here; defer Y to the next stage.`
- `If information is missing, record it explicitly and move on.`

Avoid sentence patterns:

- `In order to better...`
- `From an overall perspective...`
- `Empower...`
- `Comprehensively enhance...`
- `Provide strong support for...`
- `Further deepen...`

## Critical review overlay

Use this overlay where the document needs judgment: tradeoffs, risks, design criticism, standards, anti-patterns, and review notes.

- Reject abstractions that do not explain behavior or decision criteria.
- Name bad ideas plainly when the evidence supports that judgment.
- Keep interfaces, responsibilities, and boundaries clear.
- Cut paragraphs that sound impressive but carry no operational meaning.
- Replace diplomatic vagueness with precise disagreement when tradeoffs are real.
- Stay factual; do not role-play hostility or add performative aggression.

Do not force this overlay into basic explanatory sections.

## Sentence rules

- Write one core judgment per sentence.
- Prefer short sentences, parallel clauses, and lists over long chains.
- Put the decision before the rationale.
- Allow deliberate keyword repetition when it keeps the center of gravity stable.
- Use English technical terms when they are the natural term of record.
- Avoid vague attribution. Name the source, report, team, doc, benchmark, or observed evidence when making factual claims.
- Direct means not burying the point in process language or diplomatic framing. Definitive means claiming certainty. A sentence can be direct without being definitive. For causal claims based on observational evidence, stay direct but use inductive language: write `results suggest X typically leads to Y` rather than `X leads to Y`.
- Do not chain semicolons to compress parallel definitions into one sentence. Write separate sentences or restructure.

## Paragraph rules

- Keep one point per paragraph.
- Start each subsection with the scope, conclusion, or question it answers.
- Keep transitions minimal.
- Turn dense explanation into bullets when it improves judgment speed.
- Split paragraphs that contain unrelated topics, multiple abstraction levels, or more than one decision.
- Review paragraphs that exceed roughly 200 words (or ~400 Chinese characters) or contain 3+ independent concepts. If they cover multiple ideas, split at the concept boundary. If the paragraph is one coherent argument that reads smoothly, it can stay long.
- Do not open a document with a context-setting background paragraph. Place background at the point where it supports a specific claim.

## Heading design

Write headings that carry a judgment or conclusion, not just a topic label.

- Prefer a claim over a noun phrase: `Multi-agent coordination amplifies hallucinations` over `Multi-agent coordination`.
- Use colon format (`Topic: qualifier`) when introducing a term or attaching a principle: `Sandbox: boundaries matter more than features`.
- Use a single sentence when the subtitle is weak, redundant with the main title, or breaks reading flow.
- Drop filler words: `How to evaluate agents` over `How should we think about evaluating agents`.
- Do not string three nouns together with commas as a heading. If the heading cannot stand as a meaningful sentence, rewrite it.
- Keep commas in headings only for sequenced actions (`Fix eval first, then fix the agent`) or parallel pairs (`Sync decisions, async I/O`). Use a colon instead when the structure is `topic, explanation`.

## Content rules

- Separate facts, interpretations, constraints, and decisions.
- Surface unresolved items explicitly.
- Add examples and anti-examples when defining a rule.
- Prefer mechanisms and criteria over slogans.
- Treat references as support, not as substitute content.
- Keep versions, platforms, dependencies, environment details, sources, and risk boundaries when they affect correctness. Fill in missing context when the conclusion depends on it.
- Do not generalize a local test, personal experience, or single incident into a universal rule.
- When showing commands, configs, or code, explain the key parameters and the reasoning behind the choice — not just the final result.
- State the observation scope for performance, security, or stability claims: data source, test environment, sample size, or time window.
- When proposing a solution, add an applicability boundary: when it works and when it does not.
- Add time markers (`as of 2026-04`, `at the time of writing`) to facts that expire: prices, version numbers, product names, feature availability.
- Verify proper nouns — brand names, font names, product names — before changing them. Factual edits carry higher risk than style edits.
- When comparing multiple approaches within the same observation, merge them into one paragraph with one sentence per approach. Separate paragraphs per approach reads like a list, not analysis.
- Weave named sources into the sentence naturally. Do not parenthesize attributions or isolate them into standalone citation sentences.

### Images

- Place figures before the detail they summarize, not after. A figure works best as a visual TL;DR followed by a list or table with the specifics.
- Keep figure alt text aligned with the prose. If the prose lists 5 items but the alt text lists 6, update one or the other.
- Do not add a figure just to break up text density. If no diagram naturally fits, let the text be dense.

### References

- Use a flat list by default. Do not force categorization by type (papers / blogs / repos) unless the reader needs it.
- Order by relevance to the argument, not by publication date.
- Prefer primary sources (papers, official reports) over secondary ones (blog posts, repos). Keep only high-load-bearing secondary items.
- Keep the list scannable — typically 10–14 items.

## Terminology and bilingual text

- Keep terminology consistent across the document.
- Explain a term the first time it matters; do not repeat the same explanation later.
- When multiple terms first appear in the same passage, spread the annotations across surrounding sentences instead of clustering parentheticals. If context already makes the meaning clear, omit the annotation entirely.
- In Chinese documents, keep natural technical terms where they are already standard.
- In mixed Chinese/English text, add spaces between Chinese and English terms when readability improves.
- Do not mix punctuation styles casually. Use the punctuation style of the dominant language.
- If English and Chinese versions appear as pairs, check that they carry the same meaning rather than the same word order.

## Final style check

Before delivery, check:

- Match the user's language for the deliverable.
- The document states what problem it solves.
- Each major section answers a concrete question.
- The abstraction level is stable within each section.
- Reviewers have enough criteria to agree, disagree, or ask focused follow-ups.
- The prose avoids inflated language and generic assistant phrasing.
- Unknowns are marked instead of hidden.
- The document reads like an engineer making reality legible, not like a model trying to sound complete.
