# Style Guide

## Code Style

- Follow existing project patterns and conventions before introducing new ones
- Use TypeScript strict mode when available
- Prefer explicit types on exported functions
- Use `const` over `let`; never use `var`
- Use template literals instead of string concatenation
- Prefer early returns to reduce nesting
- Handle all errors with try/catch; never swallow silently

## Performance

- Minimize re-renders, bundle size, and API round-trips
- Avoid N+1 queries; use pagination and indexed lookups
- No heavy dependencies without clear need; prefer simple fast paths
- Don't fetch data the UI doesn't need; cache/dedupe where possible
- Prefer lazy loading and code splitting for non-critical paths

## Security

- Never include secrets, API keys, tokens, or credentials in code
- Use environment variables for all secrets
- Use parameterized queries — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions over open ranges

## Git Commits

Use Conventional Commits format: `<type>: <short description>`

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`, `build`, `perf`

- Lowercase type, imperative mood, no trailing period
- Keep subject under ~72 characters

## Testing

- Write tests for new features when a test framework exists
- Test behavior, not implementation details
- Follow Arrange-Act-Assert pattern
