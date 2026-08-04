---
inclusion: always
---

# Git Commits

## When to commit

Only commit when the user explicitly asks. If unclear, ask first.

## Commit format

Use [Conventional Commits](https://www.conventionalcommits.org/):

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
- After committing, run `git log -1 --format=full` to verify no extra trailers

## Git safety

- Never update git config
- Never run destructive commands (force push, hard reset) unless explicitly asked
- Never skip hooks (`--no-verify`) unless explicitly asked
- Never force push to `main`/`master` — warn if asked
- Avoid `git commit --amend` unless the commit is unpushed and was created in the current session
- If a pre-commit hook fails, fix and make a new commit (don't amend)
- Do not push unless the user explicitly asks
- No interactive git (`git add -i`, `git rebase -i`)

## Commit workflow

1. Run `git status` and `git diff` to understand changes
2. Draft message with accurate type focused on **why**, not just what
3. Stage relevant files (avoid `git add .` unless appropriate)
4. Commit using HEREDOC format:
   ```bash
   git commit -m "$(cat <<'EOF'
   type: description here
   EOF
   )"
   ```
5. Run `git status` to verify success
