# Agent Rules

## Core Constraints

1. Only commit when the user explicitly asks
2. Only push when the user explicitly asks
3. Only deploy when the user explicitly asks
4. Do NOT auto-start dev servers unless the user explicitly asks
5. Read existing code before writing new code
6. Match the project's existing style, libraries, and patterns
7. Keep changes minimal and focused on what was asked
8. Run tests/builds after changes to verify correctness
9. Never commit secrets (`.env`, API keys, tokens, credentials)
10. Use Conventional Commits format: `<type>: <description>`

## Coding Standards

- Use TypeScript strict mode when available
- Prefer `const` over `let`; never `var`
- Handle all errors with try/catch; never swallow silently
- Prefer early returns to reduce nesting
- Minimize re-renders, bundle size, and API round-trips
- Use parameterized queries — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions

## Git Safety

- Never update git config
- Never force push or hard reset unless explicitly asked
- Never skip hooks unless explicitly asked
- Never force push to `main`/`master`
- No interactive git operations
- No AI co-author trailers on commits
