# Mixing

Mixing 是一个面向程序员研发流程的 skill 框架，名字来自「混音」：把人的判断、工程习惯、项目上下文和 agent 的执行能力混合成可复用的工作流。

Mixing turns engineering habits into installable, composable skills for software development. The goal is to keep useful structure around the work without trapping the agent inside project-private assumptions.

## Why

好的程序员不只是写代码。他们会澄清需求、做设计取舍、审查自己的改动、系统性调试、阅读一手资料、写清楚文档，也会在发布前确认风险。

AI 的输出能力很强，但没有结构时容易变得泛化、漂移、过度自信。Mixing 把这些研发习惯拆成清晰的 skills：每个 skill 有明确目标、触发条件和边界，然后让 agent 在边界内发挥。

## Principles

- Adaptive workflows belong in skills: use them when the task needs judgment, context, follow-up questions, or tradeoff decisions.
- Deterministic checks belong in scripts when they become necessary: use them for validation, packaging, lookup, status checks, and repeatable invariants.
- Formal skills require an explicit task and a clear contract before `skills/<name>/SKILL.md` is created.
- Project-specific behavior should be discovered from public repository context and user-provided constraints, not hardcoded from private local state.
- Keep framework mechanisms generic. Do not import project-specific skill names, aliases, release rituals, or platform packaging choices from another repository.

## Skill Model

Each programmer habit can become an installed skill when it is specific enough to route and useful enough to repeat.

A Mixing skill should define:

- When to use it.
- What it does.
- What it is not for.
- What inputs and project context it may read.
- What artifact it returns or changes.
- Which checks belong outside the skill because they are deterministic.

Supporting material should live near the skill when it exists: references loaded only when needed, specialist prompts, and helper scripts for deterministic work.

## Project Context

Generic programmer behavior belongs inside Mixing. Project-specific behavior should be extracted at runtime from the target repository and the user task.

Useful context sources include:

- README files, manifests, Makefiles, CI workflows, and scripts.
- Existing project rules and agent instructions.
- Diffs, generated artifacts, protected files, release assets, and version constraints.
- Explicit user instructions.

Public docs and examples must not include credentials, certificate paths, private key filenames, tokens, or personal machine details.

## Chaining Skills

Skills are designed to be composed, but transitions should stay manual. Each skill should finish its task and wait for the user to choose the next step.

Common workflow shapes:

- Plan a feature -> implement -> review -> merge.
- Debug a regression -> fix -> verify -> release.
- Read sources -> synthesize -> write -> polish.
- Inspect an environment -> identify gaps -> apply chosen fixes.

Each arrow represents a user decision, not an automatic skill trigger.

## Rules

Shared behavior rules live in `rules/`. They are public project behavior, not private memory.

- `rules/anti-patterns.md` keeps cross-skill behavior disciplined.
- `rules/chinese.md` keeps Chinese output natural and avoids common AI prose patterns.
- `rules/english.md` keeps optional English writing feedback focused and quiet.
