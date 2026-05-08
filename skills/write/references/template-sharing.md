# Tech Sharing / Knowledge Sharing Article

**Document job:** Teach the reader a frame for reasoning about a problem, not just deliver a conclusion.

**When to use:** Team tech sharing, technical blog post, internal knowledge article, experience write-up, technology introduction.

## Sections

| # | Section | Core content | Required |
|---|---------|-------------|----------|
| 1 | Title | 4U principle: Urgent, Unique, Ultra-specific, Useful | Yes |
| 2 | TL;DR / Summary | What the reader will learn; what problem this solves | Recommended |
| 3 | Introduction / Background | Why this article exists; why the reader should care | Yes |
| 4 | Main body | Pyramid principle + MECE decomposition; scannable section headings | Yes |
| 5 | Code examples | Runnable snippets with key comments; avoid pasting large production blocks | Recommended |
| 6 | Diagrams and visuals | Architecture diagrams, flow charts, performance comparisons (with editable source links) | Recommended |
| 7 | Summary and outlook | 3–5 key takeaways; future direction | Yes |
| 8 | References | Links to authoritative sources, related articles | Yes |

## Narrative patterns

Choose the pattern that fits the article's content type:

- **Problem-driven:** Problem → root cause analysis → solution → lessons learned.
- **Practice summary:** Background → thinking → attempts → difficulties → final approach → results.
- **New technology introduction:** What → how it works → history → what it solves → basic usage → comparison with alternatives → summary.
- **Source code walkthrough:** Background → core concepts → code reading → design philosophy → best practices.

## Writing principles

1. **One core point.** Each article centers on one main theme.
2. **Audience adaptation.** Peers: deep-dive with terminology. Cross-stack: architecture trade-offs. Product/ops: purpose and outcomes.
3. **Clarity over cleverness.** Active voice, short sentences (25–30 words), simple vocabulary. Avoid condescending language like "simply" or "easily."
4. **Reasoning chain, not note dump.** The article must have its own argument thread and problem awareness, not just collected fragments.
5. **Reading momentum.** Sentence-to-sentence connectors, paragraph hooks, forward references — keep the reader moving.
6. **Concrete examples.** Prefer code, screenshots, and specific cases over abstract description.

## Adaptation notes

- For a short internal share (< 1000 words), keep only: Introduction, Main body, Summary, References.
- For a tutorial or how-to guide, use the "New technology introduction" pattern and expand the code examples section.
- For a post-project retrospective, use the "Practice summary" pattern and add a lessons-learned section.
