# AGENTS.md

Always-on Cascade / agent instructions for this workspace.

- Only commit, push, or deploy when the user explicitly asks
- Do NOT auto-start dev servers or background processes without permission
- Read existing code before writing; match project patterns; keep diffs focused
- Use Conventional Commits: `<type>: <short description>`
- Never commit secrets; never force-push to `main`/`master`

Detailed rules live in `.devin/rules/` (preferred). Legacy fallback: `.windsurf/rules/`.
