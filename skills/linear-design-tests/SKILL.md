---
name: linear-design-tests
description: Use when a Linear issue or milestone is in Test Design and the user wants useful tests proposed, refined, approved, or recorded before implementation.
---

# Linear Design Tests

Design the smallest useful test contract before implementation.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. `docs/build/linear-driven-agent-workflow.md`
4. Active milestone `slice-spec.md`
5. Active milestone `decision-log.md`
6. Active milestone `agent-operating-contract.md`
7. Issue brief under `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md`
8. `templates/build/test-design.md`

Then inspect the Linear issue state.

## Propose

For the active issue, propose:

- unit tests,
- integration or CLI tests,
- fixtures,
- golden outputs when useful,
- trace assertions,
- verification commands,
- tests to reject or defer with reasons.

Keep the set small enough to drive implementation without broadening scope.

## Rules

- Do not write production code.
- Do not implement tests until the user approves the contract.
- Record approved, rejected, and deferred tests in the issue brief after approval.
- Move or recommend moving the issue to `Ready` only after the approved test contract is recorded.

## Approval Prompt

End with a clear approval question:

```text
Do you approve this test contract as written, or should any tests be added, removed, or deferred?
```
