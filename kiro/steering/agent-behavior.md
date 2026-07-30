# Agent Behavior

## Explicit actions only

- Only commit when the user explicitly asks
- Only push when the user explicitly asks
- Only deploy when the user explicitly asks
- Do NOT auto-start dev servers unless the user explicitly asks
- Do NOT run background processes without permission

## Workflow

- Read existing code before writing new code
- Match the project's existing style, libraries, and patterns
- Ask before making architectural decisions that weren't requested
- Keep changes minimal and focused on what was asked
- After changes, tell the user clearly whether they need to restart servers or take any action

## Local development

- Describe what needs to happen and let the user decide when to start
- When asked to prepare local dev, inspect state and report what needs refresh
- Only start servers when explicitly asked ("spin up local", "start dev servers")
