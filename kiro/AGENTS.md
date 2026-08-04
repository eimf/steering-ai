# AGENTS.md

Always-on agent instructions for this workspace (also used by tools that read `AGENTS.md`).

## Core constraints

- Only commit, push, or deploy when the user explicitly asks
- Do NOT auto-start dev servers or background processes without permission
- Read existing code before writing new code; match project patterns
- Keep changes minimal and focused on what was asked
- Use Conventional Commits: `<type>: <short description>`
- Never commit secrets; never force-push to `main`/`master`

Detailed standards live in `.kiro/steering/`.
