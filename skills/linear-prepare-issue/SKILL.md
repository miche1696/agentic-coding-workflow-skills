---
name: linear-prepare-issue
description: Use when shaping or preparing a Linear issue before implementation in a repo-owned workflow, including creating or updating an issue implementation brief.
---

# Linear Prepare Issue

Prepare one Linear issue for implementation. Do not implement production code.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. `docs/build/linear-driven-agent-workflow.md`
4. Active milestone `slice-spec.md`
5. Active milestone `decision-log.md`
6. Active milestone `agent-operating-contract.md`
7. Existing issue brief under `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md`
8. `templates/build/issue-implementation-brief.md`

Then read the Linear issue.

## What To Do

- Create the issue brief if it does not exist.
- Keep product truth in repo Markdown, not Linear.
- Include a concrete Technical Implementation Plan.
- Record product rules, accepted decisions, open questions, CLI surface, trace plan, fixtures, tests, verification commands, acceptance criteria, and out-of-scope items.
- Update Linear only if the user explicitly asks or the workflow requires syncing execution state.

## Stop Conditions

Stop and ask concise questions when:

- a product decision is missing,
- a foundational technical choice is missing,
- the issue brief and slice spec disagree,
- implementation would narrow or change scope materially,
- a default must be chosen and repo docs do not define it,
- real credentials or external access are required.

## Phase Outcome

- If blocking questions remain, recommend or set `Needs Decision`.
- If no blocking questions remain, recommend or set `Test Design`.
- Do not move to `Ready` until human-approved test design is recorded.
