---
name: linear-next-action
description: Use when the user asks for the next Linear workflow action, asks what to do next, or wants to continue a Linear-driven repo-owned execution workflow without starting implementation.
---

# Linear Next Action

Choose exactly one safe next action from Linear state and repo build docs.

## Read First

Read these when present:

1. `AGENTS.md`
2. `docs/build/next-action-protocol.md`
3. `docs/build/agentic-execution-guide.md`
4. `docs/build/linear-driven-agent-workflow.md`
5. Active milestone docs under `docs/build/<milestone-slug>/`

Then inspect Linear project, milestone, and issue state.

## Rules

- Do not write code.
- Do not modify files unless the user explicitly asks to proceed.
- Prefer the first unblocked active issue in the active milestone.
- Treat Linear as execution state only; repo Markdown is the implementation source of truth.
- If Linear is unavailable, use repo docs and say Linear could not be checked.
- If the project or active milestone cannot be identified, ask one concise question.

## Decision Order

Use the first matching action:

1. Missing active milestone folder: recommend preparing it.
2. Missing or blocked slice spec: recommend preparing or resolving it.
3. Missing decision log or agent operating contract: recommend creating it.
4. First unblocked issue has no brief: recommend preparing the issue brief.
5. Issue brief has blocking questions: ask those questions.
6. Issue is in `Test Design` or lacks approved tests: recommend designing issue tests.
7. Issue is `Ready`: recommend implementing it.
8. Issue is `In Progress`: recommend continuing implementation.
9. Issue is `Verify`: recommend verifying it.
10. All issues are done: recommend milestone closeout.

## Output Format

```md
Recommended next action:
<one sentence>

Why:
<short explanation from Linear and repo state>

Suggested prompt:
```text
<prompt>
```

Needs user decision:
<yes/no>

Blocking questions:
- <only if needed>
```
