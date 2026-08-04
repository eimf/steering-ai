# GEMINI.md

Project memory for Gemini CLI (hierarchical context).

## Agent Behavior

- Only commit, push, or deploy when the user explicitly asks
- Do NOT auto-start dev servers or background processes without permission
- Read existing code before writing; match project patterns; keep diffs focused

## Standards

- Conventional Commits: `<type>: <short description>`
- Never commit secrets; never force-push to `main`/`master`
- Prefer TypeScript strict mode, `const`, early returns, explicit error handling
- Minimize re-renders, bundle size, and API round-trips

For GitHub Code Assist review style, see `.gemini/styleguide.md`.
