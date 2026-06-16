# Agent Instructions

This repo is a reusable Codex workflow kit.

When a user points Codex at this repo and asks to use it with another project, do not implement application code in this repo. Install or copy the workflow kit into the target project.

## Repo Contents

- `skills/`: Codex skills to install into the user's Codex skills directory.
- `templates/`: copyable target-repo scaffold.
- `examples/`: reference material only. Do not copy examples into a target repo unless the user explicitly asks.

## Target Repo Setup

When the user provides a target repo path:

1. Confirm the target path exists.
2. Install the skills by copying each immediate child of `skills/` into `${CODEX_HOME:-$HOME/.codex}/skills/`.
3. Copy `templates/AGENTS.md` to `<target>/AGENTS.md`.
4. Copy `templates/docs/` to `<target>/docs/`.
5. Copy `templates/templates/` to `<target>/templates/`.
6. Rename `<target>/docs/build/milestone/` to the active milestone slug if the user provided one.
7. If no milestone slug is provided, ask for one or leave `docs/build/milestone/` and clearly tell the user to rename it.

## Safety Rules

- Do not overwrite target files unless the user explicitly asks.
- If a target file already exists, stop and ask whether to merge, skip, or overwrite.
- Keep the kit generic. Do not add project-specific names, local paths, client names, private issue prefixes, or private product terms.
- Use `examples/` only to understand the intended shape and level of detail.
- After installing new skills, tell the user to restart Codex or start a new session if the skills do not appear.

## Useful User Prompts

Users can point Codex at this repo and say:

```text
Use this workflow kit with /path/to/my-target-repo.
Install the skills and copy the templates into /path/to/my-target-repo using milestone slug milestone-1-first-useful-slice.
```
