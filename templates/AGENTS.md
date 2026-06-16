# Agent Instructions

This repo uses a repo-owned, issue-tracker-driven execution workflow.

Product truth lives in Markdown files in this repo. The issue tracker records execution state only.

## Coding Principles

- Use a hard cutover approach. Do not implement backward compatibility unless explicitly requested.
- Optimize for code that is easy to read and skim.
- Avoid cleverness.
- Prefer early returns.
- Add comments or function descriptors only when they clarify non-obvious behavior.
- Keep scope small and tied to the active issue or milestone.

## Required Process Docs

Before implementation work, read:

1. `docs/build/agentic-execution-guide.md`
2. `docs/build/linear-driven-agent-workflow.md`

When asked to plan or choose the next workflow action, also read:

3. `docs/build/next-action-protocol.md`

For runnable local commands, read:

4. `docs/dev/codex-harness.md`
5. `docs/build/<milestone-slug>/agent-operating-contract.md`

## Issue-Driven Execution

When asked to work on a tracked issue:

1. Read the active milestone slice spec.
2. Read the active milestone decision log.
3. Read the active milestone agent operating contract.
4. Read the issue implementation brief if it exists.
5. If the issue brief does not exist, create it from `templates/build/issue-implementation-brief.md`.
6. Ensure the issue brief includes a concrete Technical Implementation Plan.
7. If product or foundational technical questions remain, ask the user and stop.
8. Run a human-reviewed test-design step before implementation.
9. Record approved tests, rejected tests, fixtures, trace assertions, and verification commands in the issue brief.
10. Do not code until the issue is clearly `Ready` and the test design is approved.
11. When coding, create or update tests, fixtures, and trace assertions before production implementation.
12. Verify with documented commands.
13. Update affected docs and tracker state when implementation reality changes.

## Phase Behavior

- `Backlog`: do not implement.
- `Shaping`: draft or update the repo issue brief. Do not code.
- `Needs Decision`: ask specific blocking questions. Do not code.
- `Test Design`: propose tests and record the approved test contract. Do not write production code.
- `Ready`: implementation may start only when the issue brief and test design are approved.
- `In Progress`: implement from the approved issue brief using test-first development.
- `Verify`: run checks, inspect traces, update docs, and summarize gaps.
- `Done`: only after behavior, tests, traces, docs, and tracker state are current.

Use equivalent labels or issue fields if your tracker uses different names.

## When To Stop And Ask

Stop and ask the user when:

- a product decision is missing,
- a foundational technical choice is missing,
- implementation would meaningfully narrow or change the spec,
- a default must be chosen and the repo docs do not define it,
- real external access or credentials are required,
- the issue brief and slice spec disagree,
- proposed tests conflict with accepted product interpretation,
- trace coverage is insufficient to debug the behavior,
- dependencies or tracker state look wrong.

Do not stop for ordinary implementation details when repo patterns make the answer clear.

## Context Handoff Gate

Before closing an issue, update the context future agents will rely on:

- issue brief status, acceptance criteria, verification notes, and Done checklist,
- active milestone agent operating contract,
- `docs/dev/codex-harness.md` when command behavior changes,
- active milestone slice spec when milestone-level behavior changes,
- decision log when product or foundational technical decisions were made,
- downstream issue dependencies when assumptions change,
- stale statements such as `planned`, `not implemented`, `blocked by`, `no harness`, `TODO`, `Current phase`, or `Next action`.

Run the stale-context scan if these paths exist:

```bash
rg -n "planned|not implemented|blocked by|no harness|TODO|Current phase|Next action" docs/build docs/dev AGENTS.md
```
