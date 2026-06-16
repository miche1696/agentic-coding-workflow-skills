---
name: agent-prepare-work
description: "Use when preparing tracked coding work before implementation: shaping the issue brief, resolving decisions, designing tests, recording approvals, and moving work to Ready."
---

# Agent Prepare Work

Prepare tracked coding work until it is ready for implementation. Do not write production code.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. `docs/build/linear-driven-agent-workflow.md`
4. Active milestone, slice, epic, or project spec
5. Active decision log
6. Active agent or harness operating contract
7. Existing issue/work brief under `docs/build/.../issues/`
8. `templates/build/issue-implementation-brief.md`
9. `templates/build/test-design.md`

Then read the Linear issue.

## Prepare The Brief

- Create or update the repo-owned work brief.
- Keep product truth in repo docs, not tracker text.
- Include outcome, scope, out-of-scope, decisions, open questions, CLI/API surface, data shape, trace plan, fixtures, tests, verification commands, acceptance criteria, and handoff requirements.
- Include a concrete Technical Implementation Plan covering modules/files, data/migration work, command/API changes, test/trace implementation, sequence, and non-goals.

## Resolve Decisions

Stop and ask concise questions when:

- a product decision is missing,
- a foundational technical choice is missing,
- the brief and milestone spec disagree,
- implementation would materially narrow or change scope,
- a default must be chosen and repo docs do not define it,
- real credentials or external access are required.

After the user answers, record accepted product-impacting or foundational decisions in the decision log when the repo has one.

## Design Tests

Before implementation, propose the smallest useful test contract:

- unit tests,
- integration or CLI tests,
- fixtures,
- golden outputs when useful,
- trace assertions,
- verification commands,
- rejected or deferred tests with reasons.

Ask for approval. Approval means an explicit user message in the current Codex thread. Do not implement tests until approved.

After approval, record approved, rejected, and deferred tests in the brief. The work can move to `Ready` only when the brief has no blockers and the approved test contract is recorded.

## Tracker Sync

When the workflow calls for Linear updates:

- missing brief or shaping in progress: `Shaping`,
- unresolved decisions: `Needs Decision`,
- awaiting test approval: `Test Design`,
- approved brief and tests: `Ready`.

Do not use another tracker unless the user explicitly changes the workflow.
