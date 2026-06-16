# Templates

Copy these files into a target project before using the skills.

The templates are intentionally generic. Replace placeholders such as:

- `<project name>`
- `<milestone-slug>`
- `<ISSUE-ID>`
- `<owner>`
- `<command>`

Keep product and implementation truth in the target repo. Keep tracker text short and link back to the repo docs.

## Recommended Copy

```bash
cp templates/AGENTS.md /path/to/target-repo/AGENTS.md
cp -R templates/docs /path/to/target-repo/
cp -R templates/templates /path/to/target-repo/
```

Then rename:

```text
docs/build/milestone/
```

to the active milestone slug.
