# Agentic Coding Workflow Skills

Reusable workflow skills for coding agents that operate from repo-owned docs, Linear state, approved test designs, verification commands, and GitHub shipping flows.

The current skill format is compatible with Codex `SKILL.md` folders.

These skills are generic across target projects, but intentionally Linear-driven. They assume the target project keeps product and execution truth in repository Markdown files, while Linear records operational state.

## Skills

| Skill | Use when |
| --- | --- |
| `agent-next-action` | Choosing the next safe action from repo docs and Linear state. |
| `agent-prepare-work` | Shaping work and approving the test contract before implementation. |
| `agent-implement-work` | Implementing, verifying, and updating handoff context from an approved brief. |
| `agent-ship-work` | Preparing local changes for commit, push, repository publishing, or pull request. |

## Workflow Contracts

- Approval means an explicit user message in the current Codex thread.
- Linear is the source of issue and workflow state.
- Repo docs are the source of product, technical, and execution truth.
- GitHub Issues or other trackers are out of scope unless the user explicitly changes the workflow.

## Active Work Discovery

When the active project, milestone, or issue is not named directly, use the first matching signal:

1. User prompt issue, project, or milestone.
2. Current working directory context.
3. Repo docs under `docs/build/`.
4. Linear active project or issue state.
5. One concise user question when more than one target remains plausible.

## Minimal Target Repo Setup

For a small target repo, start with:

```text
AGENTS.md
docs/build/linear-driven-agent-workflow.md
docs/build/<milestone-slug>/slice-spec.md
```

Use `docs/build/<milestone-slug>/agent-operating-contract.md` instead of `slice-spec.md` when the milestone is mostly execution or harness work.

Add an issue brief only when tracked work starts:

```text
docs/build/<milestone-slug>/issues/<LINEAR-ID>.md
```

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
docs/build/<milestone-slug>/issues/<LINEAR-ID>.md
templates/build/issue-implementation-brief.md
templates/build/test-design.md
templates/build/decision-log.md
templates/build/agent-operating-contract.md
templates/build/slice-spec.md
templates/build/milestone-closeout.md
```

Projects can rename or omit files, but the skills should infer conservatively and ask one concise question when discovery becomes ambiguous.

## Install

Copy the skill folders into your Codex skills directory:

```bash
cp -R skills/* ~/.codex/skills/
```

Restart Codex or start a new session if the skills do not appear immediately.

## Example Prompts

```text
Use agent-next-action for this repo.
Use agent-prepare-work for ABC-123.
Use agent-implement-work for ABC-123.
Use agent-ship-work for the current issue.
```

## Public Safety

Before publishing, scan for local paths and organization-specific terms:

```bash
rg -n "<absolute-home-path>|<linear-url>|<your-workspace>|<your-project>|<your-issue-prefix>"
```

The skills should stay generic. Put project-specific behavior in the target repo docs, not in this reusable skill repo.
