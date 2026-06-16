# Agentic Execution Guide

This guide explains how to move from product intent to implementation while using repo-owned docs, an issue tracker, and a coding agent.

## Core Rule

Product truth lives in repo Markdown.

The issue tracker records execution state.

The agent implements from repo-owned briefs, approved test designs, fixtures, traces, and verification commands.

## Working Model

Use three planning layers:

| Layer | Location | Purpose |
| --- | --- | --- |
| Product spec | `docs/product/` or equivalent | Full product target. |
| Slice spec | `docs/build/<milestone-slug>/slice-spec.md` | Current milestone interpretation and boundary. |
| Issue brief | `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md` | Concrete implementation contract for one tracked issue. |
| Test design | Slice spec, issue brief, or `docs/build/<milestone-slug>/test-design.md` | Human-approved tests that drive implementation. |

Tracker issues should link to these docs. They should not duplicate them.

## Recommended Structure

```text
docs/build/
  agentic-execution-guide.md
  linear-driven-agent-workflow.md
  next-action-protocol.md
  <milestone-slug>/
    slice-spec.md
    test-design.md
    decision-log.md
    agent-operating-contract.md
    issues/
      <ISSUE-ID>.md

docs/dev/
  codex-harness.md

templates/build/
  slice-spec.md
  test-design.md
  issue-implementation-brief.md
  decision-log.md
  agent-operating-contract.md
  milestone-closeout.md
```

## Build Loop

1. Select one active milestone.
2. Draft or update the milestone slice spec.
3. Record product-impacting decisions in the decision log.
4. Define runnable commands in the agent operating contract.
5. Pick the next unblocked issue.
6. Draft the issue implementation brief.
7. Ask blocking product or foundational technical questions.
8. Design tests with the human operator.
9. Record approved, rejected, and deferred tests.
10. Implement tests, fixtures, golden outputs, and trace assertions first.
11. Implement the smallest production behavior that satisfies the brief.
12. Run documented verification commands.
13. Inspect traces before changing code after trace-related failures.
14. Update docs and tracker state.
15. Close the issue only when behavior, tests, traces, docs, and tracker state are current.

## Human Gates

The human operator owns:

- product interpretation,
- scope cuts,
- defaults not defined by existing docs,
- test approval,
- acceptance judgment.

The agent owns:

- drafting briefs,
- surfacing decisions,
- proposing tests,
- writing tests and fixtures,
- implementation,
- verification,
- trace-driven debugging,
- handoff doc updates.

## Test-First Rule

Every implementation issue needs an approved test design before production code starts.

When implementation starts, create or update approved tests, fixtures, golden outputs, and trace assertions before production implementation. If a test cannot be coded first, record why in the issue brief before continuing.

## Trace-Driven Debugging

Every issue should make failures inspectable.

Define:

- trace events to emit,
- required trace fields,
- commands to inspect traces,
- tests or eval assertions proving traces exist.

When tests or evals fail, inspect traces before changing code.
