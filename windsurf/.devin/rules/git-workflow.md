---
trigger: always_on
description: "Conventional commit format, git safety, and workflow constraints"
---

# Git Workflow

## When to commit

Only commit when the user explicitly asks. If unclear, ask first.

## Message format

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>: <short description>
```

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`, `build`, `perf`

Rules:
- Lowercase type, colon, space, then description
- Imperative mood: "add feature" not "added feature"
- No trailing period, keep under ~72 characters
- No commit body unless explicitly asked
- No AI co-author trailers; author commits as the user only

## Git safety

- Never update git config
- Never run destructive commands (force push, hard reset) unless explicitly asked
- Never skip hooks (`--no-verify`) unless explicitly asked
- Never force push to `main`/`master` — warn if asked
- Avoid `git commit --amend` unless the commit is unpushed and was created in the current session
- Do not push unless the user explicitly asks
- No interactive git (`git add -i`, `git rebase -i`)
