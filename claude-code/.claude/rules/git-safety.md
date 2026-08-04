# Git Safety

- Never update git config
- Never run destructive commands (force push, hard reset) unless the user explicitly requests them
- Never skip hooks (`--no-verify`) unless the user explicitly asks
- Never force push to `main`/`master` — warn if asked
- Avoid `git commit --amend` unless the commit is unpushed and was created in the current session
- If a pre-commit hook fails, fix and make a new commit (don't amend)
- Do not push unless the user explicitly asks
- No interactive git (`git add -i`, `git rebase -i`)
- No empty commits
