# Bug Fix Report

**Document job:** Record the defect, its root cause, and the fix with enough detail for someone else to reproduce, verify, and prevent recurrence.

**When to use:** A single defect was found, investigated, and fixed. Covers production bugs, regression issues, and defect investigations.

## Sections

| # | Section | Core content | Required |
|---|---------|-------------|----------|
| 1 | Title | Specific symptom, not vague ("Checkout returns 500 when discount code X is applied") | Yes |
| 2 | Problem description | When I… I expected… But…; impact scope and severity | Yes |
| 3 | Reproduction steps | Numbered, copy-pasteable steps | Yes |
| 4 | Expected vs actual | Side-by-side comparison of correct and incorrect behavior | Yes |
| 5 | Environment | Version, OS, browser, account type, region, timestamp | Yes |
| 6 | Severity | Team-defined severity level + frequency (always reproducible?) | Yes |
| 7 | Evidence | Screenshots, video, logs, network HAR, stack traces | Recommended |
| 8 | Root cause analysis | Code-level cause, fix description, impact assessment | Yes |
| 9 | Fix verification | New test cases, regression verification, side effects check, documentation update needed? | Yes |

## Writing principles

1. **One defect per report.** Each report describes exactly one bug with enough information for someone else to reproduce it.
2. **Symptom as title.** The title describes what the user sees, not the internal cause.
3. **Reproducibility first.** If the reader cannot reproduce the bug from the report alone, it is incomplete.

## Adaptation notes

- For a minor bug with an obvious one-line fix, keep only: Title, Problem description, Root cause analysis, Fix verification.
- For a bug that required extended investigation, expand "Root cause analysis" into sub-sections: hypothesis → investigation steps → evidence → confirmed cause.
- When multiple related bugs share a single root cause, write one report with multiple symptom entries rather than separate reports.
