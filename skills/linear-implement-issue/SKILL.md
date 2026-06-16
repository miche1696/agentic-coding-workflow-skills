---
name: linear-implement-issue
description: Use when implementing a Ready Linear issue from an approved repo issue brief with test-first and trace-driven development.
---

# Linear Implement Issue

Implement one Ready issue from its approved repo brief.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. `docs/build/linear-driven-agent-workflow.md`
4. Active milestone `slice-spec.md`
5. Active milestone `decision-log.md`
6. Active milestone `agent-operating-contract.md`
7. `docs/dev/codex-harness.md`
8. Issue brief under `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md`

Then verify Linear issue state is `Ready` or equivalent.

## Required Gate

Before coding, confirm:

- the issue brief exists,
- no blocking decisions remain,
- the Technical Implementation Plan is concrete,
- human-approved tests are recorded,
- verification commands are documented.

If any gate fails, stop and report the missing item.

## Implementation Order

1. Create or update approved tests.
2. Create or update fixtures and golden outputs when approved.
3. Create or update trace assertions when approved.
4. Run tests and confirm expected failures.
5. Implement production code.
6. Run documented verification commands.
7. Inspect traces before changing code after trace-related failures.

## Handoff

After implementation, update the issue brief, agent operating contract, harness docs, slice spec, decision log, and Linear issue when implementation reality changes.

Do not close the issue until behavior, tests, traces, docs, and Linear are current.
