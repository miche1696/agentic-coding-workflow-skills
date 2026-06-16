---
name: linear-verify-issue
description: Use when verifying an implemented Linear issue, running documented checks, inspecting traces, updating handoff docs, and preparing the issue for Done.
---

# Linear Verify Issue

Verify an implemented issue and update future-agent context.

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

Then inspect Linear issue state.

## Verify

Run the documented checks from the issue brief:

- unit tests,
- integration or CLI checks,
- eval commands,
- trace inspection commands,
- stale-context scan if the repo defines one.

Do not add new scope while verifying.

## Update Handoff Context

Update relevant docs when behavior changed:

- issue brief status, verification notes, and Done checklist,
- agent operating contract command status and output shapes,
- harness guide command usage and safe automation rules,
- slice spec command status, risks, and acceptance assumptions,
- decision log for product or foundational technical decisions,
- Linear issue body or comment,
- downstream Linear issues if assumptions changed.

## Closeout Rule

Recommend or set `Done` only when:

- tests pass,
- trace inspection is current,
- docs reflect reality,
- Linear reflects reality,
- remaining planned work is clearly recorded.
