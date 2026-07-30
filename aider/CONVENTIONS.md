# CONVENTIONS.md

## Git Commits

Use Conventional Commits: `<type>: <short description>`

Types: feat, fix, docs, chore, refactor, test, ci, build, perf

- Lowercase type, imperative mood, no trailing period, ~72 char subject
- No commit body unless explicitly asked

## Code Quality

- Follow existing project patterns before introducing new ones
- Use TypeScript strict mode when available
- Prefer `const` over `let`; never `var`
- Handle all errors with try/catch; never swallow silently
- Prefer early returns to reduce nesting

## Performance

- Minimize re-renders, bundle size, and API round-trips
- Avoid N+1 queries; use pagination and indexed lookups
- No heavy deps without clear need; prefer simple fast paths
- Prefer lazy loading and code splitting for non-critical paths

## Security

- Never commit secrets (.env, API keys, tokens, credentials)
- Use environment variables for all secrets
- Parameterized queries only — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions
