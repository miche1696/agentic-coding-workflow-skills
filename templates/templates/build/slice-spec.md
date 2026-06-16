# <Milestone Name> Slice Spec

Status: draft
Tracker project: <project URL or name>
Tracker milestone: <milestone URL or name>
Product spec: `<product spec path>`
Owner: <owner>
Last updated: YYYY-MM-DD

## 1. Slice Verdict

This milestone proves:

- <demonstrable user outcome>

This milestone intentionally does not prove:

- <explicit non-goal>

## 2. User Outcome

Describe the operator-visible outcome in plain language.

## 3. Acceptance Demo

```bash
<command>
<command>
```

Expected visible result:

- <result>

Expected artifacts:

- <files, database rows, records, traces, or other artifacts>

## 4. In Scope

- <scope item>

## 5. Out Of Scope

- <deferred item>

## 6. Product Interpretation

| Spec area | Slice interpretation |
| --- | --- |
| `<section ref>` | <what this slice implements now> |

## 7. Decisions Required Before Coding

| Question | Why it matters | Owner | Status |
| --- | --- | --- | --- |
| <question> | <impact> | <owner> | open/resolved |

## 8. Decisions Already Locked

| Decision | Source | Applies to |
| --- | --- | --- |
| <decision> | `decision-log.md#DEC-001` | <issue IDs or areas> |

## 9. Data Contracts

| Record/object/file | Purpose | Required fields or behavior |
| --- | --- | --- |
| <name> | <purpose> | <fields/behavior> |

## 10. CLI Or API Contract

| Command/API | Status | Safe for agent to run? | Purpose |
| --- | --- | --- | --- |
| `<command>` | planned/stubbed/implemented | yes/no | <purpose> |

## 11. Trace Contract

| Flow | Required trace fields | Inspection command |
| --- | --- | --- |
| <flow> | <fields> | `<command>` |

## 12. Test And Eval Plan

Status: draft / pending human review / approved

### Approved Milestone Tests

| Test | Level | What it proves | Fixture/golden output | Trace assertion | Command/status |
| --- | --- | --- | --- | --- | --- |
| <test> | unit/integration/CLI/eval | <proof> | <path or none> | <trace check or none> | `<command>` planned/stubbed/implemented |

### Rejected Or Deferred Tests

| Test idea | Decision | Reason |
| --- | --- | --- |
| <test idea> | rejected/deferred | <why> |

## 13. Issue Plan

| Issue | Purpose | Depends on | Repo brief |
| --- | --- | --- | --- |
| <ISSUE-ID> | <purpose> | none | `docs/build/<milestone-slug>/issues/<ISSUE-ID>.md` |

## 14. Risks And Blocking Gaps

| Risk/gap | Impact | Resolution path |
| --- | --- | --- |
| <risk> | <impact> | <decision/test/doc/code path> |

## 15. Definition Of Done

- [ ] All required issues are complete.
- [ ] Human-reviewed milestone test design is approved.
- [ ] Approved tests were coded before production implementation, or exceptions are recorded.
- [ ] The acceptance demo works from a clean local state.
- [ ] Required traces are emitted and inspectable.
- [ ] The agent operating contract reflects implemented commands.
- [ ] Product decisions are recorded in `decision-log.md`.
