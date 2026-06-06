# Agentic Coding Project Guidance

<!-- triples-agentic:start -->
## TripleS Agentic

This project has local TripleS Agentic support for Codex and other coding agents.

### Installed local files

- `.codex/skills/` — Codex skill bundles for TripleS agents and knowledge references.
- `.codex/config.toml` — safety hooks that block dangerous commands before they run.
- `AGENTS.md` — this project guidance file for agentic coding tools.

### Start here in Codex

- Use `/skills` to browse installed skills.
- Use `$chaewon-init-setup` to explain or audit local TripleS setup.
- Use `$seoyeon` for the full PRD → Design → RFC → Tasks → Development → Test Cases → QA pipeline.
- Use specialist skills directly when needed:
  - `$jiwoo-prd` — Product Requirements Document
  - `$hyerin-design` — UI/UX design spec
  - `$yooyeon-rfc` — technical RFC
  - `$nakyoung-tasks` — task breakdown
  - `$yubin-frontend`, `$kaede-backend`, `$yeonji-android`, `$sohyun-ios`, `$kotone-flutter` — implementation
  - `$lynn-testcase` — test case design
  - `$shion-qa` — QA execution and go/no-go

### Working rules

- Treat artifacts in `workspace/` as the source of truth during TripleS workflows.
- Keep `.codex/skills/` as the canonical Codex instruction source; this file is supplemental guidance.
- Do not skip human approval gates for PRD, design, RFC, task breakdown, or test cases.
- Run `npx triples-agentic update` to refresh installed skills and managed guidance.

<!-- triples-agentic:end -->
