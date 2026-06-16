# Quickstart

This repo is a starter kit for repo-owned, issue-tracker-driven coding-agent workflows.

It contains:

- `skills/`: reusable Codex skills.
- `templates/`: files to copy into a target project.
- `examples/`: a small filled target repo example.
- `AGENTS.md`: instructions Codex can follow when applying this kit to another repo.

## 1. Clone The Kit

```bash
git clone https://github.com/miche1696/agentic-coding-workflow-skills.git
cd agentic-coding-workflow-skills
```

## 2. Point Codex At The Kit

Open this repo in Codex or provide it as context, then ask:

```text
Use this workflow kit with /path/to/target-repo.
Install the skills and copy the templates using milestone slug milestone-1-first-useful-slice.
```

Codex should read this repo's `AGENTS.md`, install the skills, copy the templates, and ask before overwriting anything.

Skills are installed into:

```text
${CODEX_HOME:-$HOME/.codex}/skills
```

Restart Codex or start a new session if newly installed skills do not appear immediately.

## 3. Manual Copy Fallback

From this repo:

```bash
cp templates/AGENTS.md /path/to/target-repo/AGENTS.md
cp -R templates/docs /path/to/target-repo/
cp -R templates/templates /path/to/target-repo/
```

Then rename the milestone placeholder:

```text
docs/build/milestone/
```

to a real milestone slug, for example:

```text
docs/build/milestone-1-first-useful-slice/
```

## 4. Fill The Minimum Required Docs

Start with:

```text
AGENTS.md
docs/build/agentic-execution-guide.md
docs/build/linear-driven-agent-workflow.md
docs/build/next-action-protocol.md
docs/build/<milestone-slug>/slice-spec.md
docs/build/<milestone-slug>/decision-log.md
docs/build/<milestone-slug>/agent-operating-contract.md
```

Create an issue brief only when a tracked issue is ready to shape:

```text
docs/build/<milestone-slug>/issues/<ISSUE-ID>.md
```

## 5. Use Short Prompts

After the target repo has the docs, use prompts like:

```text
Use agent-next-action for this repo.
Use agent-prepare-work for ABC-123.
Use agent-implement-work for ABC-123.
Use agent-ship-work for the current issue.
```

## 6. Check The Example

See `examples/minimal-target-repo/` for a small docs-only example of a configured target project.
