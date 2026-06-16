# Demo Slice Spec

Status: approved
Tracker project: Example Project
Tracker milestone: Demo Slice
Product spec: `docs/product/demo-product.md`
Owner: Example Owner
Last updated: 2026-06-16

## 1. Slice Verdict

This milestone proves:

- A user can run one CLI command and receive a deterministic greeting.

This milestone intentionally does not prove:

- Packaging, distribution, localization, or persistent settings.

## 2. User Outcome

The operator can run:

```bash
python -m demo_cli greet --name Ada
```

and see:

```text
Hello, Ada.
```

## 3. Acceptance Demo

```bash
python -m pytest
python -m demo_cli greet --name Ada
```

Expected visible result:

- Tests pass.
- The CLI prints `Hello, Ada.`

Expected artifacts:

- CLI module.
- Unit test for greeting formatting.

## 4. In Scope

- A `greet` command.
- Required `--name` argument.
- Deterministic output.

## 5. Out Of Scope

- Config files.
- Multiple languages.
- Shell completion.
- Packaging.

## 6. Product Interpretation

| Spec area | Slice interpretation |
| --- | --- |
| CLI greeting | Implement the smallest deterministic greeting command. |

## 7. Decisions Required Before Coding

> No blocking product decisions remain for this slice.

## 8. Decisions Already Locked

| Decision | Source | Applies to |
| --- | --- | --- |
| Use exact output `Hello, <name>.` | `decision-log.md#DEC-001` | DEMO-1 |

## 9. CLI Contract

| Command/API | Status | Safe for agent to run? | Purpose |
| --- | --- | --- | --- |
| `python -m demo_cli greet --name Ada` | planned | yes | Print a greeting. |
| `python -m pytest` | planned | yes | Run tests. |

## 10. Trace Contract

No trace contract is required for this tiny example.

## 11. Test And Eval Plan

Status: approved

### Approved Milestone Tests

| Test | Level | What it proves | Fixture/golden output | Trace assertion | Command/status |
| --- | --- | --- | --- | --- | --- |
| Greeting command prints exact text | CLI | User-visible behavior works | none | none | `python -m demo_cli greet --name Ada` planned |
| Greeting formatter handles a normal name | unit | Core formatting is deterministic | none | none | `python -m pytest` planned |

### Rejected Or Deferred Tests

| Test idea | Decision | Reason |
| --- | --- | --- |
| Packaging install test | deferred | Packaging is out of scope for this milestone. |

## 12. Issue Plan

| Issue | Purpose | Depends on | Repo brief |
| --- | --- | --- | --- |
| DEMO-1 | Add the greeting command. | none | `docs/build/demo-slice/issues/DEMO-1.md` |

## 13. Definition Of Done

- [ ] `DEMO-1` is complete.
- [ ] Approved tests are coded before production implementation.
- [ ] Acceptance demo passes.
- [ ] Docs match implementation.
