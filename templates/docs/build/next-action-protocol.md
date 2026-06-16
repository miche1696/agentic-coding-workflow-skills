# Next Action Protocol

Use this protocol when the user asks:

```text
Plan next action.
What should I do next?
Continue the workflow.
```

The goal is to choose one safe next action, not to start coding automatically.

## Required Inputs

Read:

1. `AGENTS.md`
2. `docs/build/agentic-execution-guide.md`
3. `docs/build/linear-driven-agent-workflow.md`
4. Active tracker project, milestone, and issues when tools are available
5. Existing `docs/build/<milestone-slug>/` files

If the tracker is unavailable, inspect repo docs and state that tracker state could not be used.

## Decision Table

Use the first matching rule.

| State | Next action |
| --- | --- |
| Active project cannot be identified | Ask which project to use. |
| Active milestone cannot be identified | Ask which milestone is active. |
| Active milestone folder does not exist | Recommend creating it from templates. |
| Active milestone `slice-spec.md` does not exist | Prepare the slice spec. |
| Slice spec has blocking questions | Ask those questions. |
| Milestone lacks approved test/eval design | Design milestone tests. |
| `decision-log.md` does not exist | Create it from template. |
| `agent-operating-contract.md` does not exist | Create it from template. |
| First unblocked issue has no repo brief | Prepare that issue brief. |
| Issue brief has blocking questions | Ask those questions. |
| Issue brief lacks a concrete Technical Implementation Plan | Update the issue brief. |
| Issue is in `Test Design` | Run the test-design conversation. |
| Issue brief lacks approved test design | Run the test-design conversation. |
| Issue is `Ready` | Recommend implementation. |
| Issue is `In Progress` | Continue implementation from the brief. |
| Issue is `Verify` | Verify the issue. |
| All active milestone issues are `Done` and no closeout exists | Prepare milestone closeout. |
| Closeout exists and is approved | Recommend selecting the next milestone. |

If tracker states differ, use equivalent labels or the `Current phase` text in the issue brief.

## Output Format

Respond with:

````md
Recommended next action:
<one sentence>

Why:
<short explanation based on tracker and repo state>

Suggested prompt:
```text
<prompt the user can approve or run>
```

Needs user decision:
<yes/no>

Blocking questions:
- <only if needed>
````

## Guardrails

- Do not recommend implementation before a repo issue brief exists.
- Do not recommend implementation before blocking questions are resolved.
- Do not recommend implementation before the Technical Implementation Plan is concrete.
- Do not recommend implementation before human-reviewed test design is approved and recorded.
- Do not create future milestone issue briefs unless that milestone is active.
- Do not treat tracker text as product truth.
- Do not make product-impacting assumptions silently.
