---
name: test-case-quality
description: Test case quality gates, priority levels, suite organisation, and traceability matrix
---

# Test Case Quality Gates & Organisation

## Priority Levels

| Priority | Definition | Examples |
|---|---|---|
| **P0 Critical** | App crashes, data loss, security breach, core flow broken | Login broken, payment fails |
| **P1 High** | Major feature doesn't work; workaround is difficult | Cart can't be updated |
| **P2 Medium** | Feature works but degrades experience | Wrong error message |
| **P3 Low** | Minor cosmetic issue | Typo, incorrect tooltip |

## Quality Gates

ALL of the following must pass before a test case set is marked implementation-ready:

- [ ] Every PRD acceptance criterion has at least one test case
- [ ] Happy path covered for all user stories
- [ ] At least 2 negative/error path cases per major feature
- [ ] Edge cases documented for all input fields
- [ ] P0 test cases identified for smoke test suite
- [ ] All test cases have specific, binary expected results (no "works correctly")
- [ ] Preconditions are unambiguous for all test cases
- [ ] Test data requirements documented
- [ ] Platform coverage specified for all test cases

## Evaluation Output

- `✅ READY — Test case suite meets all quality gates.`
- `❌ GAPS FOUND: [numbered list of specific missing scenarios or vague criteria]`

## Test Suite Structure

```
Test Suite: [Feature Name]
├── Smoke Tests (P0 only — run on every deploy, < 5 min)
├── Regression Tests (P0 + P1 — run before release)
├── Full Test Suite (all priorities — run nightly)
└── Exploratory Testing Notes (manual, unscripted sessions)
```

## Traceability Matrix

| Test Case | User Story | Acceptance Criterion |
|---|---|---|
| TC-001 | US-01 | AC-01.1 |
| TC-002 | US-01 | AC-01.2 (error state) |
| TC-003 | US-02 | AC-02.1 |

## Automation Candidates

Flag test cases that should be automated (P0 and P1 that run frequently):

| TC ID | Framework |
|---|---|
| TC-001 | Playwright / XCUITest / Espresso |
| TC-002 | Playwright |
