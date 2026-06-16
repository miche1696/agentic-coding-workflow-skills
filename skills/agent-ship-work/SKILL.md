---
name: agent-ship-work
description: "Use when preparing completed coding work for GitHub or another remote: reviewing changes, staging, committing, creating or connecting a repo, pushing, and opening a pull request."
---

# Agent Ship Work

Ship completed work without mixing unrelated changes.

## Read First

Read these when present:

1. `AGENTS.md`
2. Active issue/work brief
3. Active operating contract or verification notes
4. Repo contribution or release docs

Then inspect git state.

## Rules

- Never revert user changes unless explicitly requested.
- Separate unrelated dirty work from the current work.
- Confirm ambiguous staging scope before committing.
- Do not push, create a remote repo, or open a pull request unless the user asks.
- Prefer a branch name that includes the issue ID or work slug when available.
- Include verification results in commits or pull request body when relevant.

## Commit Flow

1. Review `git status`.
2. Review relevant diffs.
3. Confirm or run documented verification.
4. Stage only files that belong to the work.
5. Commit with a concise message tied to the work item.

## Remote Repo Publishing

When the user explicitly asks to publish a new repo:

- choose or confirm the public/private repo name,
- scan for local paths, sensitive values, workspace names, and private identifiers,
- create the remote only after the local repo is clean enough to publish,
- add `origin`,
- push the default branch,
- report the public URL.

## Pull Request Flow

When the user explicitly asks for a PR:

- push the branch,
- open a draft PR by default unless the user asks for ready,
- keep the PR body factual.

Use this body shape:

```md
## Summary

- <change>

## Verification

- `<command>`: <result>

## Notes

- <known limits or deferred work>
```

Link the tracker issue when available.
