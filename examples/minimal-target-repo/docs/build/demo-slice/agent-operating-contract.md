# Agent Operating Contract

Milestone: Demo Slice
Slice spec: `docs/build/demo-slice/slice-spec.md`
Owner: Example Owner
Last updated: 2026-06-16

This file tells the agent how to launch, test, and inspect the active milestone.

## 1. Command Status

| Command | Status | Safe for agent to run? | Requires approval? | Purpose |
| --- | --- | --- | --- | --- |
| `python -m pytest` | planned | yes | no | Run tests. |
| `python -m demo_cli greet --name Ada` | planned | yes | no | Run the acceptance demo. |

## 2. Environment Requirements

| Requirement | Needed for | Notes |
| --- | --- | --- |
| Python 3.11+ | tests and CLI | Example assumption only. |

## 3. Safe Automation Rules

The agent may run automatically:

- `python -m pytest`
- `python -m demo_cli greet --name Ada`

The agent must ask before running:

- commands that install packages,
- commands that write outside the repo.

## 4. Expected Output Shapes

### `python -m demo_cli greet --name Ada`

```text
Hello, Ada.
```

## 5. Trace Inspection

No trace command exists for this example.

## 6. Known Gaps

| Gap | Impact | Owner |
| --- | --- | --- |
| Commands are planned, not implemented | This example is docs-only | Example Owner |
