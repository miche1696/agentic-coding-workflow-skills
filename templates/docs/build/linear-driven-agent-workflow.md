# Issue-Tracker Driven Agent Workflow

This document defines how to use an issue tracker, repo Markdown, and a coding agent together.

The file name keeps `linear-driven-agent-workflow.md` because the skills look for it by default. Linear works well for this flow, but any tracker can be used if its states map to the phases below.

## Goal

Build one vertical slice at a time without losing control of product decisions.

Use the tracker as the execution queue. Use the repo as the source of truth. Use the agent as the implementation worker.

## System Of Record

| Content | Source of truth |
| --- | --- |
| Product target | `docs/product/` or equivalent |
| Active milestone interpretation | `docs/build/<milestone-slug>/slice-spec.md` |
| Product decisions | `docs/build/<milestone-slug>/decision-log.md` |
| Agent command contract | `docs/build/<milestone-slug>/agent-operating-contract.md` |
| Issue implementation detail | `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md` |
| Execution status | Issue tracker |
| Work ordering and blockers | Issue tracker |

## Issue States

Use these states directly, or map your tracker states to them:

| State | Meaning |
| --- | --- |
| Backlog | Issue exists, but no repo implementation brief is ready. |
| Shaping | Agent drafts or updates the issue brief. |
| Needs Decision | Product or foundational technical questions block implementation. |
| Test Design | Brief is shaped; tests are being reviewed before implementation. |
| Ready | Brief and test design are approved. |
| In Progress | Agent or human is implementing from the approved brief. |
| Verify | Implementation exists and needs final checks, traces, and doc updates. |
| Done | Behavior is implemented, verified, documented, and linked. |

## Tracker Issue Shape

Keep tracker issues concise.

Include:

- outcome,
- scope,
- out of scope,
- dependencies,
- spec references,
- acceptance criteria,
- verification method,
- trace requirement,
- link to the repo issue brief when it exists.

Example issue block:

```md
Repo brief:
docs/build/<milestone-slug>/issues/<ISSUE-ID>.md

Current phase:
Test Design

Agent instruction:
Follow docs/build/agentic-execution-guide.md.
Do not implement until the issue brief has no blocking questions and includes a Technical Implementation Plan.
Do not implement until human-reviewed tests are approved and recorded.

Next action:
Propose the smallest useful test contract, ask for approval, then record accepted and rejected tests in the repo brief.
```

## Issue Lifecycle

### Backlog

Do not implement.

Move to `Shaping` only when this issue is the next work item to prepare.

### Shaping

Draft or update:

```text
docs/build/<milestone-slug>/issues/<ISSUE-ID>.md
```

Use:

```text
templates/build/issue-implementation-brief.md
```

Do not code.

### Needs Decision

Ask specific blocking questions.

Record accepted product-impacting or foundational decisions in:

```text
docs/build/<milestone-slug>/decision-log.md
```

Then update the issue brief.

### Test Design

Propose the smallest useful tests:

- unit tests,
- integration or CLI tests,
- fixture and golden-output tests,
- trace assertions,
- affected milestone eval checks,
- rejected or deferred tests with reasons.

Do not write production code.

### Ready

Ready means:

- repo issue brief exists,
- no blocking questions remain,
- scope and out-of-scope are clear,
- Technical Implementation Plan is concrete,
- human-reviewed test design is approved,
- test and trace plans are concrete,
- fixtures are identified or explicitly unnecessary,
- verification commands are documented.

### In Progress

Implement in this order:

1. Approved tests.
2. Approved fixtures and golden outputs.
3. Approved trace assertions.
4. Production code.
5. Documented checks.

Stop if a product or foundational technical question appears.

### Verify

Run:

- issue-specific tests,
- CLI smoke commands,
- trace inspection commands,
- relevant milestone evals,
- context handoff checks.

Update docs and tracker notes with the result.

### Done

Done requires:

- implementation satisfies the issue brief,
- approved tests and traces exist,
- verification passes,
- docs match implementation,
- tracker state is current,
- downstream assumptions are updated.

## Milestone Closeout

When all active milestone issues are done, create:

```text
docs/build/<milestone-slug>/closeout.md
```

Use:

```text
templates/build/milestone-closeout.md
```

Close the milestone only when the acceptance demo works from a clean local state.
