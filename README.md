# vibe-skills

Single source of truth for **Lovable agent skills** used across all Vibe Coding projects.
These guide what the Lovable agent does *inside a project*. They are imported at the
workspace level and shared across every project in the workspace.

## Structure
```
vibe-skills/
└── skills/
    ├── author-rls-migration/SKILL.md
    ├── architecture-audit/SKILL.md
    └── pre-launch-checklist/SKILL.md
```
Each skill is a folder containing a `SKILL.md` (YAML frontmatter: `name`, `description`;
then markdown instructions), following the Agent Skills / Claude Skills convention.

## Import into Lovable
Workspace owner/admin: **Settings → Skills → Add → Import from GitHub**, and paste the
subdirectory URL for each skill (replace `HawkinsParnell`):
- `https://github.com/HawkinsParnell/vibe-skills/tree/main/skills/author-rls-migration`
- `https://github.com/HawkinsParnell/vibe-skills/tree/main/skills/architecture-audit`
- `https://github.com/HawkinsParnell/vibe-skills/tree/main/skills/pre-launch-checklist`

Re-import after edits to pick up changes. Skills are workspace-scoped; there is no
project-level skill import.

## Scope note
Only build-behavior skills belong here. Operational runbooks that a human/Claude execute
outside Lovable (provisioning Supabase, instrumenting a repo, the devcontainer, dev→main
promotion) are NOT Lovable skills — they live in Notion under Vibe Development Home.
