# Technology Research / Spike Report

**Document job:** Evaluate alternatives, validate unknowns, and recommend a path forward — so the team can make an informed technology decision within a time box.

**When to use:** New technology evaluation, framework selection, feasibility study, performance benchmarking, exploratory investigation with competing options.

**When not to use:** The answer takes less than ten minutes to determine, or the team already has mature experience in the domain.

## Sections

| # | Section | Core content | Required |
|---|---------|-------------|----------|
| 1 | One-line conclusion | TL;DR — recommended approach and core rationale (conclusion first) | Yes |
| 2 | Research background | Business objective, boundary constraints, why this research is needed | Yes |
| 3 | Research questions | Explicit list of questions this research answers | Yes |
| 4 | Time box | Time invested, methods used (prototype / reading / experiment / interview) | Recommended |
| 5 | Candidate enumeration | Comprehensive list of alternatives; do not silently omit popular options | Yes |
| 6 | Comparative analysis | Evaluate by business-weighted dimensions: architecture, community health (stars / update frequency / issues / docs), production adoption, feature coverage, performance (bundle size / first paint / domain metrics), compatibility, maintenance cost, business invasiveness | Yes |
| 7 | Validation data | Benchmark results, prototype output, demo recordings, self-test results | Recommended |
| 8 | Risks and limitations | Defects, hidden costs, compatibility issues per candidate. Lead with downsides; deprioritize drawbacks irrelevant to current needs | Yes |
| 9 | Recommendation | Explicit pick + rationale. Must not only list pros/cons without deciding | Yes |
| 10 | Next steps | Follow-up stories / epics, dependencies, resource requirements | Recommended |
| 11 | References | Official docs, papers, community discussions, related repositories | Yes |

## Writing principles

1. **Question-driven.** Every section should answer a predefined question. Maintain traceability: question ↔ method ↔ conclusion.
2. **Conclusion first.** The research must have a recommended path. Listing trade-offs without deciding is not a complete deliverable.
3. **Requirement alignment.** Avoid mismatch between the technical direction and the actual business need.
4. **Weighted comparison.** Adjust evaluation dimension weights based on current requirements rather than discussing all pros/cons generically.
5. **Self-tested data.** Verify key performance claims yourself and present the data. Do not rely solely on vendor benchmarks.
6. **Strict time box.** A spike has a clear deadline and produces a decision-oriented result, not an open-ended study.
7. **Honest limitations.** State experiment limitations and confounding factors.
8. **Early feedback.** Seek input at ~10% progress to avoid direction drift (10-50-99 feedback method).

## Adaptation notes

- For a quick framework comparison (2–3 candidates, clear criteria), keep only: Conclusion, Background, Candidates, Comparison, Recommendation, References.
- For a feasibility spike with a single candidate, replace "Comparative analysis" with "Evaluation against requirements" and drop "Candidate enumeration."
- When benchmarks are the core deliverable, expand "Validation data" into multiple subsections (methodology, environment, raw data, analysis) and keep other sections brief.
