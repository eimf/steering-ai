# CLAUDE.md

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

## Git Commits

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>: <short description>
```

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`, `build`, `perf`

- Lowercase type, imperative mood, no trailing period, ~72 char subject
- No commit body unless I explicitly ask
- No AI co-author trailers; author commits as me only
- After committing, run `git log -1 --format=full` to verify

## Git Safety

- Never update git config
- Never force push, hard reset, or skip hooks unless I explicitly ask
- Never force push to `main`/`master` — warn if I ask
- Avoid `git commit --amend` unless the commit is unpushed and was created in this session
- If a pre-commit hook fails, fix and make a new commit
- No interactive git (`git add -i`, `git rebase -i`)

## Performance

- Minimize re-renders, bundle size, and API round-trips
- Avoid N+1 queries; use pagination and indexed lookups
- No heavy deps without clear need; prefer simple fast paths
- Don't fetch data the UI doesn't need; cache/dedupe where possible

## Code Quality

- Use TypeScript strict mode when available
- Prefer `const` over `let`; never `var`
- Handle all errors with try/catch; never swallow silently
- Prefer early returns to reduce nesting
- Follow existing patterns before introducing new ones

## Security

- Never commit secrets: `.env`, `.env.local`, API keys, tokens, credentials
- Use environment variables for all secrets
- Parameterized queries only — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions

## Local Development

- Do NOT auto-start dev servers; describe what's needed and let me decide
- After changes, tell me whether I need to restart anything
