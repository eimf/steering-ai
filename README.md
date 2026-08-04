# steering-ai

General-purpose AI steering/rules templates for every major AI coding assistant. Copy the folder for your tool into your project and customize.

## Supported Tools

| Tool | Location | Format |
|------|----------|--------|
| **Kiro** | `kiro/.kiro/steering/*.md` (+ skills, agents, hooks, specs, …) | Markdown + `inclusion` frontmatter |
| **Cursor** | `cursor/.cursor/rules/*.mdc` (+ skills, agents, commands, hooks) | MDC (Markdown + YAML frontmatter) |
| **Windsurf / Cascade** | `windsurf/.devin/rules/*.md` (fallback: `.windsurf/rules/`) | Markdown + YAML frontmatter |
| **Claude Code** | `claude-code/CLAUDE.md` + `.claude/rules/*.md` | Plain markdown |
| **Antigravity** | `antigravity/AGENTS.md` + `.agents/rules/*.md` | Plain markdown |
| **GitHub Copilot** | `copilot/.github/copilot-instructions.md` + `instructions/*.instructions.md` | Plain markdown + `applyTo` |
| **Cline** | `cline/.clinerules/*.md` (+ `.cline/` tree) | Plain markdown |
| **Aider** | `aider/.aider.conf.yml` + `CONVENTIONS.md` + `.aiderignore` | YAML config + markdown |
| **Amazon Q** | `amazon-q/.amazonq/rules/*.md` | Plain markdown |
| **Gemini** | `gemini/GEMINI.md` + `.gemini/styleguide.md` | Plain markdown (+ config example) |

## Quick Start

1. Pick your AI tool from the table above
2. Copy the corresponding folder contents into your project at the expected path
3. Customize for your project's specific needs

### Examples

```bash
# Kiro
cp -r kiro/.kiro/ /path/to/your-project/.kiro/
cp kiro/AGENTS.md /path/to/your-project/
cp kiro/.kiroignore /path/to/your-project/

# Cursor
cp -r cursor/.cursor/ /path/to/your-project/.cursor/
cp cursor/AGENTS.md /path/to/your-project/
cp cursor/.cursorignore /path/to/your-project/

# Windsurf / Cascade (preferred .devin path)
cp -r windsurf/.devin/ /path/to/your-project/.devin/
cp windsurf/AGENTS.md /path/to/your-project/
# Optional legacy fallback:
# cp -r windsurf/.windsurf/ /path/to/your-project/.windsurf/

# Claude Code
cp claude-code/CLAUDE.md /path/to/your-project/
cp -r claude-code/.claude/ /path/to/your-project/.claude/

# Antigravity
cp antigravity/AGENTS.md /path/to/your-project/
cp -r antigravity/.agents/ /path/to/your-project/.agents/

# GitHub Copilot
mkdir -p /path/to/your-project/.github
cp -r copilot/.github/ /path/to/your-project/.github/

# Cline
cp -r cline/.clinerules/ /path/to/your-project/.clinerules/
cp -r cline/.cline/ /path/to/your-project/.cline/

# Aider
cp aider/.aider.conf.yml /path/to/your-project/
cp aider/CONVENTIONS.md /path/to/your-project/
cp aider/.aiderignore /path/to/your-project/

# Amazon Q
cp -r amazon-q/.amazonq/ /path/to/your-project/.amazonq/

# Gemini (CLI + Code Assist)
cp gemini/GEMINI.md /path/to/your-project/
cp -r gemini/.gemini/ /path/to/your-project/.gemini/
```

## What's Included

All tool configs enforce the same general-purpose conventions (see [`shared/topics/`](shared/topics/)):

### Agent Behavior
- Only commit/push/deploy when explicitly asked
- No auto-starting dev servers
- Read existing code before writing new code
- Match existing project patterns and style

### Git Commits
- [Conventional Commits](https://www.conventionalcommits.org/) format
- Git safety (no force push, no hard reset, no config changes)
- No AI co-author trailers

### Performance
- Minimize re-renders, bundle size, API round-trips
- Avoid N+1 queries
- No heavy deps without clear need

### Code Quality
- TypeScript strict mode
- Explicit error handling
- Early returns over nesting

### Security
- Never commit secrets
- Parameterized queries
- Input validation
- Pinned dependency versions

## Folder trees (project-level)

Each tool template mirrors the **documented project paths** so you can expand beyond base conventions.

### Kiro — `kiro/`

```text
AGENTS.md
.kiroignore
.kiro/
  steering/          # product, tech, structure + topic rules (inclusion modes)
  skills/            # on-demand SKILL.md packages
  agents/            # custom agent profiles
  hooks/             # event automation (*.json)
  specs/             # requirements → design → tasks
  prompts/           # CLI reusable prompts
  settings/          # mcp.json.example
```

### Cursor — `cursor/`

```text
AGENTS.md
.cursorignore
.cursor/
  rules/             # *.mdc with alwaysApply / globs / description
  skills/
  agents/
  commands/
  hooks.json.example
  hooks/
```

### Others (summary)

| Tool | Expandable dirs |
|------|-----------------|
| Windsurf | `.devin/rules/`, `AGENTS.md`, `.windsurf/rules/` fallback |
| Claude Code | `.claude/rules/`, `skills/`, `agents/`, `commands/` |
| Antigravity | `.agents/rules/`, `skills/`, `workflows/` |
| Copilot | `.github/instructions/`, `.github/agents/` |
| Cline | `.clinerules/`, `.cline/{rules,skills,agents}/` |
| Amazon Q | `.amazonq/rules/*.md` |
| Gemini | `GEMINI.md`, `.gemini/styleguide.md`, `config.yaml.example` |
| Aider | `.aider.conf.yml`, `CONVENTIONS.md`, `.aiderignore` |

Empty capability folders include a short `README.md` with the doc link and how to add the first file.

## Customization

1. Edit [`shared/topics/`](shared/topics/) (source of truth)
2. Update the matching tool-specific files
3. For project-specific guidance, add more files in that tool's rules/steering folder

Examples:

- **Kiro**: add `.kiro/steering/*.md` with `inclusion: always|fileMatch|manual|auto`
- **Cursor**: add `.cursor/rules/*.mdc` (use `globs` for file-specific rules)
- **Windsurf**: add `.devin/rules/*.md` (use `trigger: glob` for file-specific)
- **Claude Code**: add `.claude/rules/*.md` or append to `CLAUDE.md`
- **Copilot**: add `.github/instructions/*.instructions.md` with `applyTo`

## Global Installation

Some tools also support user-level config (applies across projects):

| Tool | Global Location |
|------|----------------|
| Kiro | `~/.kiro/steering/`, `~/.kiro/skills/`, `~/.kiro/agents/`, `~/.kiro/hooks/`, `~/.kiro/powers/` |
| Cursor | `~/.cursor/skills/`, `~/.cursor/agents/`, `~/.cursor/hooks.json` (User Rules via Settings UI) |
| Claude Code | `~/.claude/CLAUDE.md`, `~/.claude/rules/`, `~/.claude/skills/` |
| Aider | `~/.aider.conf.yml` |
| Gemini CLI | `~/.gemini/GEMINI.md` |

## File Format Reference

### Kiro (steering)
```yaml
---
inclusion: always          # always | fileMatch | manual | auto
fileMatchPattern: "**/*.ts"  # when inclusion is fileMatch
---

# Rule content in markdown
```

### Cursor (.mdc)
```yaml
---
description: Short description for when AI decides to load this rule
globs: "**/*.ts"        # Optional: file pattern for auto-loading
alwaysApply: true       # true = always loaded, false = conditional
---

# Rule content in markdown
```

### Windsurf / Devin (.md with frontmatter)
```yaml
---
trigger: always_on      # always_on | manual | model_decision | glob
description: "Human-readable description"
globs:                  # Required when trigger is glob
  - "src/**/*.tsx"
---

# Rule content in markdown
```

### Copilot path instructions
```yaml
---
applyTo: "**/*.{ts,tsx}"
---

# Instruction content
```

### All Others
Plain markdown — no special syntax required (unless the tool's docs add frontmatter).

## Limits

- **Windsurf**: ~6,000 chars per rule / ~12,000 chars total active
- **Cursor**: Keep each rule focused (~500 lines max recommended)
- **Others**: No documented hard limits, but shorter = better for context efficiency

## Contributing

1. Edit `shared/topics/` with your proposed change
2. Update the relevant tool-specific files to match
3. Submit a PR

## License

MIT
