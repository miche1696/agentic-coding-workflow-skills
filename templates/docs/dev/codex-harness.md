# Codex Harness Guide

This guide tells the agent and operator how to run this project locally without relying on chat history.

For milestone-specific command truth, also read:

```text
docs/build/<milestone-slug>/agent-operating-contract.md
```

If this guide and the active milestone operating contract disagree, stop and update the docs before implementing.

## Test-First Rule

Before production implementation for any tracked issue:

- run the human-reviewed test-design step,
- record approved and rejected tests in the issue brief,
- create or update approved tests, fixtures, golden outputs, and trace assertions before production code,
- record any exception in the issue brief before continuing.

## Current Runnable Surface

Replace these placeholders with real project commands.

| Command | Purpose | Safe? | Approval required? | Status |
| --- | --- | --- | --- | --- |
| `<setup command>` | Install or prepare local dependencies. | yes/no | yes/no | planned/stubbed/implemented |
| `<test command>` | Run automated tests. | yes/no | yes/no | planned/stubbed/implemented |
| `<dev command>` | Run the local app or harness. | yes/no | yes/no | planned/stubbed/implemented |
| `<eval command>` | Run milestone evals. | yes/no | yes/no | planned/stubbed/implemented |
| `<trace command>` | Inspect latest traces. | yes/no | yes/no | planned/stubbed/implemented |

## Setup Assumptions

Document:

- required language runtime,
- package manager,
- environment variables,
- local database or file state,
- fixture locations,
- commands that require credentials,
- commands that are safe for the agent to run automatically.

## Output Shapes

For each command the agent should assert, document the expected output.

### `<command>`

```json
{
  "ok": true,
  "result": {}
}
```

## Trace Inspection

| Need | Command or location |
| --- | --- |
| Latest run | `<command>` |
| Specific run | `<command>` |
| Failed stage | `<command or log path>` |

## Verification Checklist

- [ ] Setup command is documented.
- [ ] Test command is documented.
- [ ] Eval command is documented or explicitly not available.
- [ ] Trace inspection is documented or explicitly not available.
- [ ] Commands that require credentials or external writes require approval.
