---
name: write
description: "Draft, rewrite, or polish documentation with clear problem framing, stable abstraction levels, structured reasoning, and direct prose. Only activates on explicit writing or editing requests. Not for code comments, pure translation, compliance advice, or deterministic checks."
when_to_use: "写文档, 输出文档, 帮我写, 起草, 重写, 重构文档, 润色, 优化文档, 改稿, 去AI味"
metadata:
  version: "0.1.0"
---

# Write: Write clear, accurate and structured documentation.

Prefix your first line with 🎛 inline, not as its own paragraph.

This skill guides the drafting, rewriting, and polishing of technical documents, producing clear structure, precise language, and a natural professional tone free of AI patterns or formulaic phrasing.

## Pre-flight
Before writing a document, gather essential information from the user about:

1. **Source present?**
   - Draft Mode requires `Source material` (facts, notes, files, conversation context, or reference materials to draft from). The writing goal is derived from the user's instruction and `Document type`. If no source material is present, ask in one sentence.
   - Rewrite / Polish Mode requires `Source text` (the actual prose to reshape or edit). If the user gave only an instruction with no text, ask for it in one sentence. Do not proceed.
2. **Mode locked?** Before writing, classify the task into exactly one mode.
  - when the user asks for a new document and does not provide a complete source text to edit -> Draft Mode
  - when the user asks to change the document's structure, logic, outline, section order, or argument shape -> Rewrite Mode
  - when the user provides prose and asks for better wording, proofreading, natural tone, or AI-tone removal without structural change -> Polish Mode

  If the requested mode is ambiguous, infer from the strongest verb:
  - `draft`, `write`, `create`, `generate`, `起草`, `写一份`, `生成文档` -> `Draft Mode`
  - `rewrite`, `restructure`, `reorganize`, `rebuild`, `重写`, `重构`, `调整结构` -> `Rewrite Mode`
  - `polish`, `proofread`, `edit text`, `sound natural`, `remove AI tone`, `润色`, `改稿`, `去AI味` -> `Polish Mode`

  If cannot classify the mode, ask the user for the exact mode in one sentence.
3. **Document type identified?** If the intended document type is unclear and cannot be inferred from the text (`设计文档`、`bug分析报告`or`proposal`..), ask before editing.

### Inferring from Context

If you have previous conversation context, infer `Mode`, `Document type`, and the required source (`Source material` for Draft; `Source text` for Rewrite/Polish) from what was discussed. You can derive these from files, user text, docs, or explicit assumptions that emerged in the conversation.

### Gathering Additional Information

If you need clarification, use the AskQuestion tool when available:

```
Example AskQuestion usage:
- "需要撰写什么类型的文档?" with options like ["RFC", "设计文档", "bug修复报告", "技术预研", "技术分享"]
- "你是仅需要润色`IntlSDK 设计文档.md`吗" with options like ["是", "否"]
```

If the AskQuestion tool is not available, ask these questions conversationally.

---

## Hard Rules

- **Meaning first, style second.** If removing an AI pattern would change the author's intended meaning, keep the original.
- **Stop after output.** Deliver the rewritten text. Do not append a list of changes, a justification, or a closer.

## References

All paths are relative to this skill directory.

| File | Purpose |
|------|---------|
| `references/writing-guide.md` | Keep prose direct, structured, and precise with stable abstraction levels and concrete reasoning. |
| `references/anti-ai.md` | Strip AI patterns from prose and make it sound human. |
| `references/template-proposal-design-rfc.md` | Template for technical proposals, functional design, and RFCs. |
| `references/template-bugfix-postmortem.md` | Template for bug fix reports and root cause analyses. |
| `references/template-research-spike.md` | Template for technology research, framework evaluation, and spike reports. |
| `references/template-sharing.md` | Template for tech sharing and knowledge sharing articles. |

Templates are adaptive structures, not fixed forms. Start from the document's job, choose the closest pattern, then remove sections that do not help the reader.

## Workflow

Use the mode, document type, and source identified in Pre-flight to drive the steps below.

### Choosing sections

These rules apply across Draft and Rewrite modes when deciding which sections to include or omit:

- Add `Non-goals` when the document could otherwise expand without a clear limit.
- Add `Risks` when the decision affects reliability, security, data, performance, compatibility, or user workflow.
- Add `Validation` when a reviewer needs to know how correctness will be checked.
- Add `Open questions` when facts or decisions are missing.
- Add `References` when claims depend on external docs, benchmarks, specs, issues, or prior decisions.
- Remove sections that do not answer a reader question.

In Draft and Rewrite modes, verify each condition above against the document before returning it.

### Draft Mode

Create a new document from the user's goal and available facts.

#### Execution process (in sequence)

Execute in the following order, do not reverse:
1. **Confirm inputs.** Verify Pre-flight has resolved: `Mode`, `Document type`, and `Source material`. If any is missing, stop and ask.
2. **Choose template.** Pick and load the document template from "References" section based on `Document type`.
3. **Classify the document's job.** Read `Document job` from the document template. Identify what the document must accomplish for its reader.
4. **Set the boundary and abstraction level.** State what this document will solve and what it will not solve.
5. **Draft with structured reasoning.** Load and apply `references/writing-guide.md`. Based on the document template, write to help the reader judge, not just receive information.
6. **Verify template completeness.** Compare the draft against the template's section list. For each section marked Required: confirm it exists in the draft, or explicitly note why it was omitted (scope too small, no applicable content from source material). Apply "Choosing sections" rules to check whether Non-goals, Risks, Validation, Open questions, or References should be added based on the document's content.
7. **Strip AI patterns from prose.** Load and apply `references/anti-ai.md` to remove formulaic phrasing from the draft.

Return the requested document. Do not append a change summary unless the user asked for process notes.

### Rewrite Mode

Reshape an existing document's structure while preserving its facts.

#### Execution process (in sequence)

Execute in the following order, do not reverse:
1. **Confirm inputs.** Verify Pre-flight has resolved: `Source text`, `Mode`, and `Document type`. If any is missing, stop and ask.
2. **Diagnose structural problems.** Read the source text and list concrete issues: unclear section boundaries, repeated arguments, mixed concerns in single paragraphs, missing logical flow, or sections that do not serve the reader.
3. **Choose structural guide.** If `Document type` matches a template from "References" section, load it as a reorganization reference — not a mandatory form.
4. **Reshape.** Reorder sections, rewrite headings, merge duplicates, split mixed paragraphs, and adjust flow to match the diagnosis. Load and apply `references/writing-guide.md` to keep prose direct with stable abstraction levels. Preserve all source meaning, facts, constraints, and uncertainty.
5. **Fill structural gaps.** If a template was loaded in step 3, check each Required section — add missing ones when source text supports them, mark as `pending confirmation` when material is insufficient. Apply "Choosing sections" rules for conditional sections (Non-goals, Risks, Validation, Open questions, References). Only add sections the source text provides enough material to support.
6. **Strip AI patterns from prose.** Load and apply `references/anti-ai.md` to remove formulaic phrasing introduced during restructuring.

Return the full rewritten document unless the user asks for a partial rewrite.

### Polish Mode

Edit prose in place without changing structure or meaning.

#### Execution process (in sequence)

Execute in the following order, do not reverse:
1. **Confirm inputs.** Verify Pre-flight has resolved: `Source text` and `Mode`. Document type is optional — polish applies regardless of type.
2. **Lock structure.** Treat paragraph order, heading hierarchy, section boundaries, facts, terminology, and scope as immutable. Do not silently restructure, merge sections, or reorder arguments.
3. **Scan for surface problems.** Identify: inflated language, generic assistant phrasing, report tone, empty transitions, awkward rhythm, overlong sentences, punctuation drift, and terminology inconsistency.
4. **Edit sentence by sentence.** Fix each problem found in step 3. Load and apply `references/writing-guide.md` to maintain stable abstraction levels and direct expression. When meaning and style conflict, preserve meaning — keep technical precision even when a sentence sounds less smooth.
5. **Strip AI patterns from prose.** Load and apply `references/anti-ai.md` to remove formulaic phrasing while respecting the structure lock from step 2.

Return only the edited prose unless the user explicitly asks for an explanation, diff, or change list.

## Final check

Before returning the document, verify:

[] The document states the problem, purpose, or reader job it serves.
[] The output matches the selected mode: draft creates, rewrite reshapes, polish edits in place.
[] (Draft/Rewrite) Every Required section from the template is present or has an explicit omission note.
[] (Draft/Rewrite) The five "Choosing sections" conditions have been evaluated — Non-goals, Risks, Validation, Open questions, References are present when their trigger conditions are met.
[] At least half of h2/h3 headings carry a judgment, conclusion, or qualifier — not just a topic label.
