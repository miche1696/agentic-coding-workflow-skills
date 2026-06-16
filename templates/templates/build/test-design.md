# <Target Name> Test Design

Status: draft / pending human review / approved
Target type: milestone / issue
Tracker target: <tracker milestone or issue URL>
Source doc: `<slice spec or issue brief path>`
Owner: <owner>
Last updated: YYYY-MM-DD

Use this template only when the test-design conversation is large enough to deserve its own artifact. For small issues, record the same content directly in the issue brief.

## 1. Test Design Goal

- <goal>

## 2. Sources Read

- `<product spec path>`
- `<active slice spec>`
- `<issue brief, if applicable>`
- `<decision log>`
- `<agent operating contract>`
- <tracker target>

## 3. Proposed Tests

| Test | Level | Why it matters | Fixture/golden output | Trace assertion | Recommendation |
| --- | --- | --- | --- | --- | --- |
| <test> | unit/integration/CLI/eval | <reason> | <path or none> | <trace assertion or none> | keep/reject/defer |

## 4. Human Review Notes

| Decision type | Test or theme | Note |
| --- | --- | --- |
| Accepted | <test or theme> | <note> |
| Rejected | <test or theme> | <why> |
| Changed | <test or theme> | <how> |

## 5. Approved Tests To Code Before Production Implementation

| Test | Level | Expected failure before implementation | Acceptance mapping | Command |
| --- | --- | --- | --- | --- |
| <test> | unit/integration/CLI/eval | <why it fails before implementation, if applicable> | <criterion or behavior> | `<command>` |

## 6. Required Fixtures And Golden Outputs

| Artifact | Purpose | Created before production code? |
| --- | --- | --- |
| <path> | <purpose> | yes/no |

## 7. Required Trace Assertions

| Trace event | Required fields | Test that asserts it |
| --- | --- | --- |
| <event> | <fields> | <test> |

## 8. Rejected Or Deferred Tests

| Test idea | Decision | Reason |
| --- | --- | --- |
| <test idea> | rejected/deferred | <why> |

## 9. Open Questions

| Question | Why it matters | Blocking? |
| --- | --- | --- |
| <question> | <impact> | yes/no |

If there are no blocking questions, write:

> No blocking test-design questions remain.

## 10. Approval

This test design is approved when:

- [ ] The human operator has accepted the useful tests.
- [ ] Rejected or deferred tests are recorded with reasons.
- [ ] Tests map to acceptance criteria or milestone outcomes.
- [ ] Fixtures and golden outputs are identified or explicitly unnecessary.
- [ ] Trace assertions are identified or explicitly unnecessary.
- [ ] Commands are documented or marked as planned.
- [ ] Production implementation is still blocked until approved tests are coded.
