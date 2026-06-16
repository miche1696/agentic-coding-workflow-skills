---
name: github-ship-work
description: Use when the user wants to prepare completed local work for GitHub by reviewing changes, committing intentionally, pushing a branch, or opening a pull request.
---

# GitHub Ship Work

Prepare local work for GitHub without mixing unrelated changes.

## Read First

Read these when present:

1. `AGENTS.md`
2. Active issue brief under `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md`
3. Active milestone `agent-operating-contract.md`
4. Verification notes from the current work

Then inspect git state.

## Rules

- Never revert user changes unless explicitly requested.
- Separate unrelated dirty work from the current issue.
- Confirm what belongs in the commit before staging when scope is ambiguous.
- Do not push or open a pull request unless the user asks for that action.
- Prefer a branch name that includes the issue ID when available.
- Include verification results in the pull request body.

## Commit Preparation

Before committing:

- review `git status`,
- review relevant diffs,
- run or confirm documented verification,
- stage only files that belong to the current work,
- write a concise commit message tied to the issue.

## Pull Request Shape

Use this structure when opening a PR:

```md
## Summary

- <change>

## Verification

- `<command>`: <result>

## Notes

- <known limits or deferred work>
```

Keep the PR body factual. Link the Linear issue when available.
