# <ISSUE-ID> - <Issue Title>

Status: draft
Tracker issue: <issue URL>
Milestone: <milestone name>
Slice spec: `docs/build/<milestone-slug>/slice-spec.md`
Owner: <owner>
Last updated: YYYY-MM-DD

## 1. Outcome

Describe what works when this issue is done.

This issue is complete when:

- <concrete outcome>

## 2. Tracker Context

| Field | Value |
| --- | --- |
| Issue | `<ISSUE-ID>` |
| Current phase | Backlog / Shaping / Needs Decision / Test Design / Ready / In Progress / Verify / Done |
| Priority | <priority> |
| Blocked by | <issue IDs or none> |
| Blocks | <issue IDs or none> |

## 3. Product Rules

| Spec ref | Rule | Issue interpretation |
| --- | --- | --- |
| `<spec path>` §<section> | <rule> | <what this issue does> |

## 4. Decisions Locked

| Decision | Source |
| --- | --- |
| <decision> | `../decision-log.md#DEC-001` |

If there are no locked decisions yet, write:

> No issue-specific decisions are locked yet.

## 5. Open Questions

| Question | Why it matters | Blocking? |
| --- | --- | --- |
| <question> | <impact> | yes/no |

If there are no blocking questions, write:

> No blocking questions remain.

## 6. Functional Behavior

### Inputs

- <input>

### Outputs

- <output>

### State Changes

- <state change>

### Error Behavior

- <error case and expected response>

## 7. Technical Shape

### Files Or Modules

| Path/module | Expected change |
| --- | --- |
| <path> | <change> |

### Data Model

| Record/table/object | Required fields or behavior |
| --- | --- |
| <name> | <fields/behavior> |

### APIs Or Capabilities

| Capability/command/API | Behavior |
| --- | --- |
| <name> | <behavior> |

## 8. Technical Implementation Plan

### Package / Module Layout

- <package/module layout>

### Files To Create Or Change

| Path/module | Create/change | Purpose |
| --- | --- | --- |
| <path> | create/change | <purpose> |

### Data And Migration Plan

- <tables, migrations, file formats, or persistence changes>

### CLI / API Implementation Plan

- <commands, handlers, request/response shapes>

### Test And Trace Implementation Plan

- <where approved tests will be added before production implementation>
- <trace assertions to add>

### Implementation Sequence

1. <step>
2. <step>

### Technical Non-Goals

- <technical work intentionally deferred>

## 9. External Capability Reuse Check

Required only if this issue touches external connectors, auth, credentials, MCP/tool surfaces, agent runtime/orchestration, or third-party APIs.

If not applicable, write:

> Not applicable; this issue does not touch external connectors, auth, MCP/tool surfaces, agent runtime/orchestration, or third-party APIs.

If applicable, complete:

| Check | Result |
| --- | --- |
| Existing tools/frameworks evaluated | <options considered> |
| Reuse, wrap, or build custom decision | <decision> |
| Reason | <why this choice fits the issue> |
| Harness boundary preserved | yes/no, <how> |
| Approval, trace, and validation bypass avoided | yes/no, <how> |

## 10. Human-Reviewed Test Design

Status: draft / pending human review / approved

### Proposed Tests

| Test | Level | Why it matters | Fixture/golden output | Trace assertion | Keep? |
| --- | --- | --- | --- | --- | --- |
| <test> | unit/integration/CLI/eval | <reason> | <path or none> | <trace assertion or none> | yes/no/pending |

### Approved Tests To Code Before Production Implementation

| Test | Level | Expected failure before implementation | Acceptance mapping |
| --- | --- | --- | --- |
| <test> | unit/integration/CLI/eval | <why it fails before implementation, if applicable> | <criterion or behavior> |

### Rejected Or Deferred Tests

| Test idea | Decision | Reason |
| --- | --- | --- |
| <test idea> | rejected/deferred | <why> |

### Test Design Notes

- <human feedback, tradeoffs, or constraints>

## 11. CLI Or API Surface

| Command/API | Status | Expected result |
| --- | --- | --- |
| `<command>` | planned/stubbed/implemented | <result> |

## 12. Test Plan

### Unit Tests

- <test>

### Integration Tests

- <test>

### CLI / Smoke Tests

- <test command>

### Golden Tests

- <golden output check>

## 13. Trace Plan

| Trace event | Required fields | Why it exists |
| --- | --- | --- |
| <event> | <fields> | <reason> |

Inspection command:

```bash
<trace command>
```

Trace assertions:

- <assertion>

## 14. Fixtures

| Fixture | Purpose |
| --- | --- |
| <path> | <purpose> |

## 15. Acceptance Criteria

- [ ] <criterion>
- [ ] <criterion>

## 16. Verification Commands

```bash
<command>
<command>
```

## 17. Verification Notes

Record final command results, trace refs, known gaps, and context handoff notes.

## 18. Done Checklist

- [ ] Approved tests were coded before production implementation, or exceptions are recorded.
- [ ] Verification commands passed or gaps are documented.
- [ ] Required traces are emitted and inspectable.
- [ ] Docs that changed behavior are updated.
- [ ] Tracker issue is current.
