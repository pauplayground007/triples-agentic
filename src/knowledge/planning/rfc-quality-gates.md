---
name: rfc-quality-gates
description: RFC quality gate checklist, anti-patterns, and evaluation criteria for implementation readiness
---

# RFC Quality Gates & Anti-Patterns

## Quality Gates

ALL of the following must pass before an RFC is marked implementation-ready:

- [ ] **Architecture decision** — the chosen approach is stated clearly with a rationale
- [ ] **Alternatives documented** — at least 2 alternatives considered and rejected with reasoning
- [ ] **Data model** — entities and relationships defined (even if approximate)
- [ ] **API contracts** — public interfaces defined with request/response shapes
- [ ] **Risk assessment** — at least one risk identified with a mitigation
- [ ] **Rollback plan** — how to undo this change if it goes wrong
- [ ] **No scope creep** — RFC stays within the bounds of the approved PRD
- [ ] **Open questions closed** — no unresolved technical blockers before handoff

## Evaluation Output

Run all gates and output exactly one of:

- `✅ READY — RFC meets all quality gates.`
- `❌ GAPS FOUND: [numbered list of failing gates with specific technical questions to resolve]`

## Anti-Patterns to Avoid

| Anti-Pattern | Problem | Fix |
|---|---|---|
| "We'll figure out the DB schema later" | Blocks task estimation | Design the schema now, mark as draft |
| RFC written after code is done | Not a design doc, a post-mortem | Write RFC before implementation |
| No alternatives section | Appears like the first idea was the only idea | Always document what was rejected |
| "Industry standard approach" without citation | Vague justification | Name the standard and link to it |
| Mixing security concerns into every section | Hard to review | Dedicated security section |
| Rollout plan missing | No way to safely deploy | Always include feature flag + rollback |
| Vague risk ("could be slow") | Not actionable | Quantify: "p95 > 500ms under 1000 RPS" |
