# Coding Standards

- Follow existing project patterns before introducing new ones
- Use TypeScript strict mode when available
- Prefer `const` over `let`; never `var`
- Handle all errors with try/catch; never swallow silently
- Prefer early returns to reduce nesting
- Minimize re-renders, bundle size, and API round-trips
- Use parameterized queries — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions
- Never commit secrets (`.env`, API keys, tokens, credentials)
