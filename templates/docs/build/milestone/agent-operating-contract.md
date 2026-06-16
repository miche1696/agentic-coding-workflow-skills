# Agent Operating Contract

Milestone: <milestone name>
Slice spec: `docs/build/<milestone-slug>/slice-spec.md`
Owner: <owner>
Last updated: YYYY-MM-DD

This file tells the agent how to launch, use, test, and inspect the active milestone.

Commands may be `planned`, `stubbed`, or `implemented`.

## 1. Command Status

| Command | Status | Safe for agent to run? | Requires approval? | Purpose |
| --- | --- | --- | --- | --- |
| `<setup command>` | planned/stubbed/implemented | yes/no | yes/no | <purpose> |
| `<test command>` | planned/stubbed/implemented | yes/no | yes/no | <purpose> |
| `<dev command>` | planned/stubbed/implemented | yes/no | yes/no | <purpose> |
| `<trace command>` | planned/stubbed/implemented | yes/no | yes/no | <purpose> |
| `<eval command>` | planned/stubbed/implemented | yes/no | yes/no | <purpose> |

## 2. Environment Requirements

| Requirement | Needed for | Notes |
| --- | --- | --- |
| <requirement> | <command/flow> | <notes> |

## 3. Safe Automation Rules

The agent may run automatically:

- <command or command category>

The agent must ask before running:

- <command or command category>

## 4. Expected Output Shapes

### `<command>`

```json
{
  "ok": true,
  "result": {}
}
```

## 5. Trace Inspection

| Need | Command |
| --- | --- |
| Latest trace | `<command>` |
| Run trace | `<command>` |
| Failure trace | `<command>` |

## 6. Test Commands

| Command | Status | Safe for agent to run? | Purpose |
| --- | --- | --- | --- |
| `<test command>` | planned/stubbed/implemented | yes/no | <purpose> |

## 7. Eval Contract

Milestone eval command:

```bash
<command>
```

Eval must fail when:

- <condition>

## 8. Known Gaps

| Gap | Impact | Owner |
| --- | --- | --- |
| <gap> | <impact> | <owner> |
