# Shared Conventions

This document defines the general-purpose conventions that all tool-specific steering files are derived from. Edit this file to change the source of truth, then regenerate or update tool-specific files.

## Git Commits

Use [Conventional Commits](https://www.conventionalcommits.org/) format:

```
<type>: <short description>
```

### Types

- `feat` — new feature
- `fix` — bug fix
- `docs` — documentation only
- `chore` — maintenance, tooling, deps (no production code change)
- `refactor` — code change that neither fixes a bug nor adds a feature
- `test` — adding or updating tests
- `ci` — CI/CD changes
- `build` — build system or external dependencies
- `perf` — performance improvement

### Rules

- Lowercase type, colon, space, then description
- Imperative mood: "add feature" not "added feature"
- No trailing period on the subject line
- Keep subject under ~72 characters; no commit body unless explicitly asked
- No AI co-author trailers; author commits as the user only
- Do NOT commit unless the user explicitly asks

## Git Safety

- Never update git config
- Never run destructive commands (force push, hard reset) unless the user explicitly requests them
- Never skip hooks (`--no-verify`) unless the user explicitly asks
- Never force push to `main`/`master` — warn if asked
- Avoid `git commit --amend` unless the commit is unpushed and was created in the current session
- If a pre-commit hook fails, fix and make a new commit (don't amend)
- Do not push unless the user explicitly asks
- No interactive git (`git add -i`, `git rebase -i`)
- No empty commits

## Performance

- Minimize re-renders, bundle size, and API round-trips
- Avoid N+1 queries; use pagination and indexed lookups
- No heavy dependencies without clear need; prefer simple fast paths over extra abstraction
- Do not fetch data the UI does not need; cache/dedupe where the codebase already does
- Prefer lazy loading and code splitting for non-critical paths

## Code Quality

- Follow existing project patterns and conventions before introducing new ones
- Use TypeScript strict mode when available
- Prefer explicit types on exported functions
- Use `const` over `let`; never use `var`
- Handle all errors with try/catch and appropriate user feedback
- Use parameterized queries — never string concatenation for SQL/queries
- Validate all external inputs (API params, user input, env vars)

## Security

- Never commit secrets: `.env`, `.env.local`, API keys, tokens, credentials
- Never log or echo sensitive values in output
- Use environment variables for all secrets
- Validate and sanitize user input
- Use HTTPS for all external requests
- Prefer pinned dependency versions over open ranges

## Local Development

- Do NOT auto-start dev servers unless the user explicitly asks
- Do NOT run background processes without permission
- Describe what needs to happen and let the user decide when to start
- After changes, tell the user clearly whether they need to restart servers

## Agent Behavior

- Only commit when the user explicitly asks
- Only push when the user explicitly asks
- Only deploy when the user explicitly asks
- Read existing code before writing new code
- Match the project's existing style, libraries, and patterns
- Ask before making architectural decisions that weren't requested
- Keep changes minimal and focused on what was asked
- Run tests/builds after changes to verify correctness
