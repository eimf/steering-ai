# CLAUDE.md

Always-on project instructions. Modular details live in `.claude/rules/`.

## Agent Behavior

- Only commit when I explicitly ask
- Only push when I explicitly ask
- Only deploy when I explicitly ask
- Do NOT auto-start dev servers unless I explicitly ask
- Do NOT run background processes without permission
- Read existing code before writing new code
- Match the project's existing style, libraries, and patterns
- Keep changes minimal and focused on what was asked
- Run tests/builds after changes to verify correctness

## Quick standards

- Conventional Commits: `<type>: <short description>`
- Never commit secrets; never force-push to `main`/`master`
- Prefer TypeScript strict mode, `const`, early returns, explicit error handling

See `.claude/rules/` for full topic files.
