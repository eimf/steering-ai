# Agent Behavior

- Only commit when the user explicitly asks
- Only push when the user explicitly asks
- Only deploy when the user explicitly asks
- Do NOT auto-start dev servers unless the user explicitly asks
- Read existing code before writing new code
- Match the project's existing style, libraries, and patterns
- Keep changes minimal and focused on what was asked
- Run tests/builds after changes to verify correctness

# Git Commits

Use Conventional Commits: `<type>: <short description>`

Types: feat, fix, docs, chore, refactor, test, ci, build, perf

- Lowercase type, imperative mood, no trailing period, ~72 char subject
- No commit body unless explicitly asked
- No AI co-author trailers

# Git Safety

- Never force push, hard reset, or skip hooks unless explicitly asked
- Never force push to main/master
- No interactive git operations
- No git config changes

# Performance

- Minimize re-renders, bundle size, and API round-trips
- Avoid N+1 queries; use pagination and indexed lookups
- No heavy deps without clear need
- Prefer lazy loading and code splitting

# Code Quality

- Use TypeScript strict mode when available
- Prefer const over let; never var
- Handle all errors with try/catch; never swallow silently
- Prefer early returns to reduce nesting
- Follow existing patterns before introducing new ones

# Security

- Never commit secrets (.env, API keys, tokens, credentials)
- Use environment variables for all secrets
- Parameterized queries only
- Validate and sanitize all external inputs
- Prefer pinned dependency versions
