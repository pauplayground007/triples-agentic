# Claude Code Project Guidance

<!-- triples-agentic:start -->
## TripleS Agentic

This project has local TripleS Agentic support for Claude Code.

### Installed local files

- `.claude/skills/` — TripleS agent skills and knowledge bundles.
- `.claude/settings.json` — safety hooks that block dangerous commands before they run.
- `CLAUDE.md` — this project guidance file.

### Start here

- Use `/chaewon-init-setup` to explain or audit the local TripleS setup.
- Use `/seoyeon run` for the full PRD → Design → RFC → Tasks → Development → Test Cases → QA pipeline.
- Use specialist agents directly when needed:
  - `/jiwoo-prd` — Product Requirements Document
  - `/hyerin-design` — UI/UX design spec
  - `/yooyeon-rfc` — technical RFC
  - `/nakyoung-tasks` — task breakdown
  - `/yubin-frontend`, `/kaede-backend`, `/yeonji-android`, `/sohyun-ios`, `/kotone-flutter` — implementation
  - `/lynn-testcase` — test case design
  - `/shion-qa` — QA execution and go/no-go

### Working rules

- Treat artifacts in `workspace/` as the source of truth during TripleS workflows.
- Do not skip human approval gates for PRD, design, RFC, task breakdown, or test cases.
- Use `/seoyeon status` when the workflow state is unclear.
- Run `npx triples-agentic update` to refresh installed skills and managed guidance.

<!-- triples-agentic:end -->
