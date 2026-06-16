---
name: agent-implement-work
description: Use when implementing tracked coding work from an approved brief, including test-first changes, verification, trace inspection, docs updates, and handoff to Done.
---

# Agent Implement Work

Implement one approved work item end to end: tests first, production code second, verification and handoff last.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. Tracker workflow docs
4. Active milestone, slice, epic, or project spec
5. Active decision log
6. Active agent or harness operating contract
7. `docs/dev/codex-harness.md` or equivalent command guide
8. Approved issue/work brief

Then confirm tracker state is `Ready`, `In Progress`, or equivalent.

## Required Gate

Before coding, confirm:

- the brief exists,
- no blocking decisions remain,
- the Technical Implementation Plan is concrete,
- human-approved tests are recorded,
- verification commands are documented.

If any gate fails, stop and report the missing item.

## Implementation Order

1. Create or update approved tests.
2. Create or update approved fixtures and golden outputs.
3. Create or update approved trace assertions.
4. Run tests and confirm expected failures when practical.
5. Implement production code.
6. Run the documented checks.
7. Inspect traces before changing code after trace-related failures.

Keep scope tied to the active work item. Do not add unrelated refactors.

## Verification

Run the checks named in the brief, such as:

- unit tests,
- integration or CLI checks,
- eval commands,
- trace inspection commands,
- stale-context scan if the repo defines one.

Do not add new scope during verification.

## Handoff

Update future-agent context when behavior changes:

- work brief status, verification notes, and done checklist,
- operating contract command status, output shape, safe automation, approval requirements,
- harness or command guide,
- milestone/slice spec command status, risks, and acceptance assumptions,
- decision log for approved product or foundational decisions,
- tracker issue body/comment/status,
- downstream issues if assumptions changed.

The work can move to `Done` only when behavior, tests, traces, docs, and tracker state are current.
