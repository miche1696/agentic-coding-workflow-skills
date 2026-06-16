---
name: agent-next-action
description: Use when the user asks what a coding agent should do next, asks to continue a repo-owned delivery workflow, or wants one safe next action from issue tracker and repo state without implementation.
---

# Agent Next Action

Choose exactly one safe next action. Do not code or modify files unless the user explicitly asks to proceed.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/next-action-protocol.md`
3. `docs/build/agentic-execution-guide.md`
4. `docs/build/linear-driven-agent-workflow.md` or equivalent issue-tracker workflow docs
5. Active milestone, epic, or project docs under `docs/build/`
6. Active issue brief, if one exists

Then inspect the issue tracker state when tools are available. Linear is supported, but the skill should also work with GitHub Issues or another tracker when the repo docs define the mapping.

## Decision Order

Use the first matching action:

1. Active project or milestone cannot be identified: ask one concise question.
2. Milestone/project docs are missing: recommend preparing them.
3. Slice/spec docs have blocking questions: ask those questions.
4. Operating contract or harness docs are missing: recommend preparing them.
5. First unblocked issue has no repo brief: recommend preparing the work.
6. Brief has blocking product or technical questions: ask those questions.
7. Brief lacks approved test design: recommend preparing the work through test approval.
8. Issue is ready with approved tests: recommend implementation.
9. Issue is in progress: recommend continuing implementation.
10. Issue awaits verification: recommend implementation verification.
11. All active work is done: recommend closeout or shipping.

## Output

Return:

- `Recommended next action`: one sentence.
- `Why`: short explanation from repo and tracker state.
- `Suggested prompt`: a copyable prompt the user can approve or run.
- `Needs user decision`: yes or no.
- `Blocking questions`: include only when needed.
