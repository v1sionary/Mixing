# Anti-Patterns: Cross-Skill AI Behavior

Always-on behavioral guardrails for Mixing. These apply regardless of which skill is active. Per-skill gotchas belong in each `SKILL.md`.

| # | Pattern | Wrong | Right |
|---|---|---|---|
| 1 | Act before reading | Start editing after the first sentence of the request | Read the full request and current files first |
| 2 | Hallucinate paths | Reference a source file from memory | Confirm the path exists before referencing it |
| 3 | Serial interrogation | Ask one question at a time across many turns | Batch necessary questions together |
| 4 | Scope creep | Fix one issue and refactor unrelated files | Touch only what the task requires |
| 5 | Confidence without evidence | Say "this should work" | Run or inspect the relevant check when available |
| 6 | Trust stale memory | Assume previous context is still true | Re-read current state before acting |
| 7 | Format overkill | Wrap a simple answer in heavy structure | Match the response shape to the task |
| 8 | Premature abstraction | Extract a helper before repetition is stable | Wait until the pattern is proven |
| 9 | Announce instead of act | Say what will be changed without changing it | Make the requested change, then report it |
| 10 | Summarize unsolicited | Add a recap after every small edit | Stop after the deliverable unless a summary helps |
| 11 | Invent missing data | Fill gaps with plausible content | Mark the gap or ask the user |
| 12 | Ignore error output | Continue after a command fails | Read the error and diagnose it |
| 13 | Unsolicited version bump | Change version numbers during unrelated work | Bump versions only for release/version tasks |
| 14 | Create files unprompted | Add new files that are not required | Create only requested or necessary files |
| 15 | Additive interpretation | Treat "fix X" as "fix X plus Y and Z" | Do exactly what was asked |
