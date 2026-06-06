---
name: init-project
description: TripleS project initialization and local install guidance for coding-agent setup
---

# Init Project

## Purpose

TripleS project initialization prepares a repository for local agent usage. It installs agent skills, knowledge references, safety hooks, and project-root guidance files without overwriting user-owned instructions.

## Project vs Global Install

| Scope | Use when | Root docs |
|---|---|---|
| Project | The repository needs local TripleS guidance and safety hooks | `CLAUDE.md` / `AGENTS.md` can be generated |
| Global | The user wants TripleS available across many projects | No project-root docs are generated |

Prefer project install for repository-specific workflows.

## Local Install Artifacts

| Platform | Local generated files |
|---|---|
| Claude Code | `.claude/skills/*.md`, `.claude/skills/<group>-<skill>/`, `.claude/settings.json`, optional `CLAUDE.md` |
| OpenAI Codex | `.codex/skills/<skill>/`, `.codex/config.toml`, optional `AGENTS.md` |
| Cursor AI | `.cursor/rules/*.mdc`, `.cursor/rules/knowledge/`, `.cursor/rules/triples-safety.mdc` |
| GitHub Copilot | `.github/instructions/*.instructions.md`, `.github/instructions/knowledge/`, `.github/instructions/triples-safety.instructions.md` |
| Windsurf | `.windsurfrules`, `.windsurf/hooks.json` |

## Root Docs

`CLAUDE.md` and `AGENTS.md` are project-root guidance files. They explain how to use the installed local skills in the current repository.

They are not the source of all agent behavior:

- Claude agent instructions live in `.claude/skills/`.
- Codex agent instructions live in `.codex/skills/`.
- Root docs provide onboarding, command hints, and project-level reminders.

## Preservation Rules

Generated root docs use managed sentinels:

```markdown
<!-- triples-agentic:start -->
... managed content ...
<!-- triples-agentic:end -->
```

Installer behavior:

- If the root doc is absent, create it.
- If the root doc contains both sentinels, update only the managed block.
- If the root doc exists without sentinels, preserve it untouched.
- If an old TripleS-generated `AGENTS.md` is detected, migrate it into the managed-block format.

## First Commands

Claude Code:

- `/chaewon-init-setup` — explain or audit local TripleS setup.
- `/seoyeon run` — start the full PRD-to-QA delivery pipeline.
- `/jiwoo-prd`, `/hyerin-design`, `/yooyeon-rfc`, `/nakyoung-tasks` — run individual planning stages.

Codex:

- `/skills` — browse installed skills.
- `$chaewon-init-setup` — explain or audit local TripleS setup.
- `$seoyeon` — orchestrate end-to-end delivery.
- `$jiwoo-prd`, `$kaede-backend`, `$shion-qa` — call specialist skills directly.

## Update Guidance

Run:

```bash
npx triples-agentic update
```

Use update when:

- installed skills are missing or stale,
- a new TripleS version adds agents or knowledge bundles,
- local safety hooks need regeneration,
- managed root docs should receive updated TripleS guidance.

## Troubleshooting

| Symptom | Check | Fix |
|---|---|---|
| Claude command missing | `.claude/skills/<agent>.md` | Run `npx triples-agentic claude` |
| Codex skill missing | `.codex/skills/<agent>/SKILL.md` | Run `npx triples-agentic codex` |
| Root doc missing | Project install vs global install | Run project install without `--global` |
| Root doc not updated | Existing file lacks sentinels | Preserve user file or add managed block manually |
| Hooks missing | `.claude/settings.json` / `.codex/config.toml` | Run installer/update again |

## Anti-Patterns

- **Root-doc-only install:** adding `CLAUDE.md` or `AGENTS.md` without installing local skills.
- **Blind overwrite:** replacing user-owned project instructions without explicit approval.
- **Global when project is needed:** using `--global` and expecting repository root docs.
- **Delivery via setup agent:** asking `chaewon-init-setup` to perform PRD, RFC, implementation, or QA work instead of routing to the specialist agents.
