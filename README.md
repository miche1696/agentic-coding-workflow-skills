# Agentic Coding Workflow Skills

Reusable workflow skills and starter-kit templates for coding agents that operate from repo-owned docs, Linear state, approved test designs, verification commands, and GitHub shipping flows.

The current skill format is compatible with Codex `SKILL.md` folders.

This repo is meant to be complete on its own:

- `skills/` contains the reusable agent skills.
- `templates/` contains the target-project docs those skills expect.
- `examples/` contains a filled docs-only target repo example.
- `AGENTS.md` tells Codex how to install the skills and copy the templates into another repo.
- `QUICKSTART.md` explains the manual setup flow.

## Skills

| Skill | Use when |
| --- | --- |
| `agent-next-action` | Choosing the next safe action from repo docs and Linear state. |
| `agent-prepare-work` | Shaping work and approving the test contract before implementation. |
| `agent-implement-work` | Implementing, verifying, and updating handoff context from an approved brief. |
| `agent-ship-work` | Preparing local changes for commit, push, repository publishing, or pull request. |

## Starter Kit Contents

```text
skills/
  agent-next-action/
  agent-prepare-work/
  agent-implement-work/
  agent-ship-work/

templates/
  AGENTS.md
  docs/
    build/
      agentic-execution-guide.md
      linear-driven-agent-workflow.md
      next-action-protocol.md
      milestone/
        slice-spec.md
        decision-log.md
        agent-operating-contract.md
        issues/
          ISSUE-ID.md
    dev/
      codex-harness.md
  templates/
    build/
      issue-implementation-brief.md
      test-design.md
      decision-log.md
      agent-operating-contract.md
      slice-spec.md
      milestone-closeout.md

examples/
  minimal-target-repo/

AGENTS.md
```

The nested `templates/templates/build/` path is intentional. The outer `templates/` folder is the copyable target-repo skeleton. After copying it into a project, the target project receives its own `templates/build/` folder.

## Target Repo Setup

Clone this repo, then point Codex at it and provide the target repo path:

```text
Use this workflow kit with /path/to/target-repo.
Install the skills and copy the templates using milestone slug milestone-1-first-useful-slice.
```

Codex should follow `AGENTS.md` in this repo. It will:

- copy `AGENTS.md`, `docs/`, and `templates/build/` into the target repo,
- rename `docs/build/milestone/` when a milestone slug is provided,
- install the Codex skills when asked,
- ask before overwriting existing target files.

If you only want to install the skills:

```bash
cp -R skills/* ~/.codex/skills/
```

Manual copy works without Codex:

```bash
cp templates/AGENTS.md /path/to/target-repo/AGENTS.md
cp -R templates/docs /path/to/target-repo/
cp -R templates/templates /path/to/target-repo/
```

Then rename:

```text
docs/build/milestone/
```

to the active milestone slug, for example:

```text
docs/build/milestone-1-first-useful-slice/
```

## Expected Target Project Docs

After setup, the target repo should contain:

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

Projects can rename or omit files, but the skills should infer conservatively and ask one concise question when discovery becomes ambiguous.

## Workflow Contracts

- Approval means an explicit user message in the current Codex thread.
- Linear is the default source of issue and workflow state.
- Repo docs are the source of product, technical, and execution truth.
- GitHub Issues or another tracker can be used only when the user explicitly changes the workflow or the target repo docs define the mapping.

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
rg -n "<absolute-home-path>|<tracker-url>|<your-workspace>|<your-project>|<your-issue-prefix>"
```

The skills should stay generic. Put project-specific behavior in the target repo docs, not in this reusable skill repo.
