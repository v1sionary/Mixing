# Technical Proposal / Design Document / RFC

**Document job:** Prove that a design is worth doing, feasible, and controllable — so reviewers can approve, reject, or request changes before code is written.

**When to use:** New feature design, architecture change, system refactoring, technology selection decision, cross-team initiative requiring consensus.

## Sections

| # | Section | Core content | Required |
|---|---------|-------------|----------|
| 1 | Metadata | Title, author, reviewers, status (Draft / In Review / Approved / Superseded), version, date | Yes |
| 2 | Summary / TL;DR | One paragraph: what, why, how, expected benefit. Enough for a reader to decide whether to read further | Yes |
| 3 | Background and motivation | Business context, pain points, supporting data, why now, stakeholders | Yes |
| 4 | Goals and non-goals | Measurable targets (QPS, availability, latency, etc.) + explicit declaration of what is out of scope | Yes |
| 5 | User-facing explanation | Use cases, user stories, guide-level explanation, UX scenarios | Recommended |
| 6 | Detailed design | Architecture diagram, core flows, sequence diagrams, data model (ER / DDL / indexes), API design (params / idempotency / rate limiting), state machine | Yes |
| 7 | Alternatives considered | Candidate approaches with pros/cons matrix, selection rationale, prior art from the industry | Yes |
| 8 | Cross-cutting concerns | Security, privacy, performance (capacity estimation / load test), cost, observability (monitoring / alerting), compatibility, multi-region | Yes |
| 9 | Implementation plan | Milestones, task breakdown, dependencies, rollout strategy, rollback plan, go-live checklist | Yes |
| 10 | Test strategy | Unit tests, integration tests, load tests, chaos engineering, reconciliation (for financial systems) | Recommended |
| 11 | Risks and mitigation | Known risks, impact assessment, mitigation plan, owners | Yes |
| 12 | Open questions | Items for discussion, known unknowns, pre-review vs implementation-phase questions | Recommended |
| 13 | Teaching and adoption | Documentation update plan, team training, migration guide, naming conventions | Optional |

## Writing principles

1. **BLUF (Bottom Line Up Front).** The summary must let a reader decide whether to deep-read without scrolling past the fold.
2. **Problem before solution.** Define constraints and success criteria before describing the design.
3. **Explicit comparison.** Never present only the chosen approach — explain why alternatives were rejected.
4. **Layered audience.** Executive summary for managers; detailed design for engineers.
5. **Decision tool, not post-hoc documentation.** A design doc is a means to reach consensus before coding, not a record written afterwards.
6. **Trim to fit.** Small tasks do not need every section filled. Remove sections that add no reader value.
7. **Lifecycle status.** Mark the document's stage: Draft → In Review → Approved → Superseded.
8. **Write alone, review together.** One person writes the draft; the team reviews.

## Adaptation notes

- For a lightweight RFC (< 1 page scope), keep only: Summary, Motivation, Proposed approach, Alternatives, Open questions.
- For a pure architecture decision record (ADR), keep: Context, Decision, Consequences, Status.
- Merge "Goals / Non-goals" into "Background" when the document is short enough that splitting them creates orphan sections.
- Add a "Prior art" section when the design draws on patterns from other systems or open-source projects.
