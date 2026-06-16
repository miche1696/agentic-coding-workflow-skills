# DEMO-1 - Add Greeting Command

Status: Ready
Tracker issue: Example Tracker DEMO-1
Milestone: Demo Slice
Slice spec: `docs/build/demo-slice/slice-spec.md`
Owner: Example Owner
Last updated: 2026-06-16

## 1. Outcome

This issue is complete when:

- `python -m demo_cli greet --name Ada` prints `Hello, Ada.`
- tests prove the formatter and CLI output.

## 2. Tracker Context

| Field | Value |
| --- | --- |
| Issue | `DEMO-1` |
| Current phase | Ready |
| Priority | Medium |
| Blocked by | none |
| Blocks | none |

## 3. Product Rules

| Spec ref | Rule | Issue interpretation |
| --- | --- | --- |
| `docs/build/demo-slice/slice-spec.md` | Greeting output must be deterministic. | Print exact output with a trailing period. |

## 4. Decisions Locked

| Decision | Source |
| --- | --- |
| Use exact output `Hello, <name>.` | `../decision-log.md#DEC-001` |

## 5. Open Questions

> No blocking questions remain.

## 6. Functional Behavior

### Inputs

- `--name <value>`

### Outputs

- `Hello, <value>.`

### State Changes

- None.

### Error Behavior

- Missing `--name` returns normal CLI argument validation.

## 7. Technical Shape

### Files Or Modules

| Path/module | Expected change |
| --- | --- |
| `demo_cli/__main__.py` | Parse `greet --name`. |
| `demo_cli/greeting.py` | Format greeting text. |
| `tests/test_greeting.py` | Unit test formatter. |
| `tests/test_cli.py` | CLI smoke test. |

### Data Model

No data model changes.

### APIs Or Capabilities

| Capability/command/API | Behavior |
| --- | --- |
| `python -m demo_cli greet --name Ada` | Print `Hello, Ada.` |

## 8. Technical Implementation Plan

### Package / Module Layout

- `demo_cli/greeting.py` holds pure formatting.
- `demo_cli/__main__.py` holds minimal argument parsing.

### Files To Create Or Change

| Path/module | Create/change | Purpose |
| --- | --- | --- |
| `demo_cli/greeting.py` | create | Format greeting text. |
| `demo_cli/__main__.py` | create | CLI entrypoint. |
| `tests/test_greeting.py` | create | Unit coverage. |
| `tests/test_cli.py` | create | CLI smoke coverage. |

### Data And Migration Plan

- Not applicable.

### CLI / API Implementation Plan

- Use standard library `argparse`.
- Add one subcommand: `greet`.
- Require `--name`.

### Test And Trace Implementation Plan

- Add tests before production code.
- Trace assertions are not required for this tiny CLI.

### Implementation Sequence

1. Add formatter and CLI tests.
2. Confirm tests fail because modules do not exist.
3. Add formatter.
4. Add CLI entrypoint.
5. Run verification commands.

### Technical Non-Goals

- No packaging.
- No config system.
- No persistent state.

## 9. External Capability Reuse Check

> Not applicable; this issue does not touch external connectors, auth, MCP/tool surfaces, agent runtime/orchestration, or third-party APIs.

## 10. Human-Reviewed Test Design

Status: approved

### Proposed Tests

| Test | Level | Why it matters | Fixture/golden output | Trace assertion | Keep? |
| --- | --- | --- | --- | --- | --- |
| Formatter returns exact greeting | unit | Proves core behavior | none | none | yes |
| CLI prints exact greeting | CLI | Proves user-visible behavior | none | none | yes |
| Missing name error snapshot | CLI | Argparse already covers this | none | none | no |

### Approved Tests To Code Before Production Implementation

| Test | Level | Expected failure before implementation | Acceptance mapping |
| --- | --- | --- | --- |
| `format_greeting("Ada") == "Hello, Ada."` | unit | module does not exist | deterministic formatter |
| CLI stdout equals `Hello, Ada.` | CLI | module does not exist | acceptance demo |

### Rejected Or Deferred Tests

| Test idea | Decision | Reason |
| --- | --- | --- |
| Missing name error snapshot | rejected | Standard argparse behavior is enough for this slice. |

## 11. CLI Surface

| Command | Status | Expected result |
| --- | --- | --- |
| `python -m demo_cli greet --name Ada` | planned | prints `Hello, Ada.` |

## 12. Test Plan

### Unit Tests

- `format_greeting("Ada") == "Hello, Ada."`

### CLI / Smoke Tests

- `python -m demo_cli greet --name Ada`

## 13. Trace Plan

Trace assertions are not required for this tiny CLI.

## 14. Fixtures

No fixtures required.

## 15. Acceptance Criteria

- [ ] Formatter test passes.
- [ ] CLI smoke test passes.
- [ ] Acceptance demo prints exact text.

## 16. Verification Commands

```bash
python -m pytest
python -m demo_cli greet --name Ada
```

## 17. Verification Notes

Not run. This example is docs-only.

## 18. Done Checklist

- [ ] Approved tests were coded before production implementation.
- [ ] Verification commands passed.
- [ ] Docs that changed behavior are updated.
- [ ] Tracker issue is current.
