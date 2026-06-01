---
name: prd-quality-gates
description: PRD quality gate checklist, anti-patterns to avoid, and pass/fail evaluation criteria
---

# PRD Quality Gates & Anti-Patterns

## Quality Gates

ALL of the following must pass before a PRD is marked implementation-ready:

- [ ] **Problem statement** — clear, specific, one paragraph, explains user pain
- [ ] **Primary persona** — at least one user persona defined with goals and context
- [ ] **Feature scope** — both in-scope AND out-of-scope explicitly stated
- [ ] **User stories** — at least 3 stories covering core journeys
- [ ] **Acceptance criteria** — every major feature has measurable pass/fail criteria (no vague "works well")
- [ ] **Success metrics** — at least one quantitative metric defined
- [ ] **No implementation leak** — PRD does not prescribe tech stack, architecture, or database choices
- [ ] **Open questions addressed** — no blockers left unanswered before handoff

## Evaluation Output

Run all gates and output exactly one of:

- `✅ READY — PRD meets all quality gates.`
- `❌ GAPS FOUND: [numbered list of failing gates with specific questions to resolve]`

## Anti-Patterns to Avoid

| Anti-Pattern | Why It's Wrong | Fix |
|---|---|---|
| "The system should be fast" | Not measurable | "Page load under 2s on 3G" |
| "Use React for the frontend" | PRD prescribes implementation | Move to RFC |
| "TBD" on acceptance criteria | Engineers can't test against TBD | Resolve before handoff |
| Features listed without personas | No context for priority decisions | Add who benefits and why |
| 40-page PRD for an MVP | Overspecification kills agility | Cut to what's needed for v1 |
| "And" in a user story | Too many concerns in one story | Split into separate stories |
| Acceptance criteria with "should" | "Should" is not binary | Use "must" or rewrite as Given/When/Then |
