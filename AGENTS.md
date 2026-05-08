# AGENTS.md

## Project

Mixing is a skill collection for engineering workflows. The repository contains eight skills: `write`, `debug`, `study`, and `read`.

## Repository Map

- `skills/` - installed Mixing skills. Keep `skills/.gitkeep` while no formal skill exists.
- `skills/*/SKILL.md` - individual skill entrypoints when formal skills are added.
- `skills/*/agents/` - optional specialist prompts loaded by a skill.
- `skills/*/references/` - optional support references loaded only when needed.
- `skills/*/scripts/` - optional deterministic helper scripts for a skill.
- `rules/` - shared writing and behavior rules.
- `.codex-plugin/plugin.json` - Codex plugin metadata.
- `.cursor/rules/` - Cursor project rules.

## Adding Or Changing A Skill

Use this path for any new skill or meaningful behavior change:

1. Create or update `skills/<name>/SKILL.md`; keep the description concrete, triggerable, and include a `Not for ...` exclusion.
2. Put deterministic enforcement in `scripts/` or `rules/`; keep only adaptive judgment in the skill body.

## Skill Vs Script

Before adding a capability, choose the layer deliberately:

| Question | Yes | No |
|---|---|---|
| Does the user need judgment, adaptation, or follow-up questions? | Skill | Script or rule |
| Does the same input always produce the same output? | Script or rule | Skill |
| Is it a lookup, list, status check, packaging check, or invariant check? | Script or rule | Skill |
| Does behavior shift with project context or conversation context? | Skill | Script or rule |

## Skill Design Rules

- Keep each skill concrete enough for routing.
- Avoid broad skills that mix unrelated workflows.
- Keep generic programmer capabilities in Mixing.
- Extract project-specific constraints from README files, manifests, CI, Makefiles, diffs, public docs, and user-provided context.
- Do not depend on credentials, private paths, personal machine state, or unpublished local files.
- Keep support files self-contained and resolve them relative to the installed Mixing directory.

## Tips
- Keep formal skills English-first so they remain portable, routable, distributable, and executable across agent/plugin environments.
- The interaction process uses the user's language.