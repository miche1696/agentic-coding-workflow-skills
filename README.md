# Codex Linear Workflow Skills

Reusable Codex skills for a Linear-driven, repo-owned delivery workflow.

These skills are intentionally generic. They assume the target project keeps its product and execution truth in repository Markdown files, while Linear tracks operational state.

## Skills

| Skill | Use when |
| --- | --- |
| `linear-next-action` | Choosing the next safe Linear workflow action. |
| `linear-prepare-issue` | Shaping a Linear issue into a repo-owned implementation brief. |
| `linear-design-tests` | Designing and recording human-approved tests before implementation. |
| `linear-implement-issue` | Implementing a Ready issue test-first from an approved brief. |
| `linear-verify-issue` | Verifying an implemented issue and updating handoff context. |
| `github-ship-work` | Preparing local changes for commit, push, and pull request. |

## Expected Project Docs

The skills work best when the target repo contains some or all of these files:

```text
AGENTS.md
docs/build/agentic-execution-guide.md
docs/build/linear-driven-agent-workflow.md
docs/build/next-action-protocol.md
docs/dev/codex-harness.md
docs/build/<milestone-slug>/slice-spec.md
docs/build/<milestone-slug>/decision-log.md
docs/build/<milestone-slug>/agent-operating-contract.md
docs/build/<milestone-slug>/issues/<ISSUE-ID>.md
templates/build/issue-implementation-brief.md
templates/build/test-design.md
templates/build/decision-log.md
templates/build/agent-operating-contract.md
templates/build/slice-spec.md
templates/build/milestone-closeout.md
```

Projects can rename or omit files, but the skills should then infer conservatively and ask concise questions rather than guessing.

## Install

Copy the skill folders into your Codex skills directory:

```bash
cp -R skills/* ~/.codex/skills/
```

Restart Codex or start a new session if the skills do not appear immediately.

## Example Prompts

```text
Use linear-next-action for this repo.
Use linear-prepare-issue for ABC-123.
Use linear-design-tests for ABC-123.
Use linear-implement-issue for ABC-123.
Use linear-verify-issue for ABC-123.
Use github-ship-work for the current issue.
```

## Public Safety

Before publishing, scan for local paths and organization-specific terms:

```bash
rg -n "<absolute-home-path>|<linear-url>|<your-workspace>|<your-project>|<your-issue-prefix>"
```

The skills should stay generic. Put project-specific behavior in the target repo docs, not in this reusable skill repo.
