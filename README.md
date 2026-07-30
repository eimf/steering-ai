# steering-ai

General-purpose AI steering/rules files for every major AI coding assistant. Copy the folder for your tool into your project and customize.

## Supported Tools

| Tool | Location | Format |
|------|----------|--------|
| **Kiro** | `kiro/steering/*.md` | Plain markdown (auto-loaded from `.kiro/steering/`) |
| **Cursor** | `cursor/rules/*.mdc` | MDC (Markdown + YAML frontmatter) |
| **Windsurf / Cascade** | `windsurf/rules/*.md` | Markdown + YAML frontmatter |
| **Claude Code** | `claude-code/CLAUDE.md` | Plain markdown at project root |
| **Antigravity** | `antigravity/AGENTS.md` + `.agents/rules.md` | Plain markdown |
| **GitHub Copilot** | `copilot/.github/copilot-instructions.md` | Plain markdown |
| **Cline** | `cline/.cline/rules/conventions.md` | Plain markdown |
| **Aider** | `aider/.aider.conf.yml` + `CONVENTIONS.md` | YAML config + markdown |
| **Amazon Q** | `amazon-q/.amazonq/rules/conventions.md` | Plain markdown |
| **Gemini Code Assist** | `gemini/.gemini/styleguide.md` | Plain markdown |

## Quick Start

1. Pick your AI tool from the table above
2. Copy the corresponding folder contents into your project at the expected path
3. Customize for your project's specific needs

### Examples

```bash
# Kiro
cp -r kiro/steering/ /path/to/your-project/.kiro/steering/

# Cursor
cp -r cursor/rules/ /path/to/your-project/.cursor/rules/

# Windsurf / Cascade
cp -r windsurf/rules/ /path/to/your-project/.windsurf/rules/

# Claude Code
cp claude-code/CLAUDE.md /path/to/your-project/CLAUDE.md

# Antigravity
cp antigravity/AGENTS.md /path/to/your-project/AGENTS.md
cp -r antigravity/.agents/ /path/to/your-project/.agents/

# GitHub Copilot
mkdir -p /path/to/your-project/.github
cp copilot/.github/copilot-instructions.md /path/to/your-project/.github/

# Cline
cp -r cline/.cline/ /path/to/your-project/.cline/

# Aider
cp aider/.aider.conf.yml /path/to/your-project/
cp aider/CONVENTIONS.md /path/to/your-project/

# Amazon Q
cp -r amazon-q/.amazonq/ /path/to/your-project/.amazonq/

# Gemini Code Assist
cp -r gemini/.gemini/ /path/to/your-project/.gemini/
```

## What's Included

All tool configs enforce the same set of general-purpose conventions:

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

## Customization

The `shared/conventions.md` file is the single source of truth for all conventions. Edit it to change the base rules, then update the tool-specific files to match.

For project-specific rules (deployment playbooks, architecture docs, stack details), add additional files alongside these base conventions:

- **Kiro**: Add more `.md` files to `.kiro/steering/`
- **Cursor**: Add more `.mdc` files to `.cursor/rules/` (use `globs` for file-specific rules)
- **Windsurf**: Add more `.md` files to `.windsurf/rules/` (use `trigger: glob` for file-specific)
- **Claude Code**: Append sections to `CLAUDE.md`
- **Copilot**: Append sections to `.github/copilot-instructions.md`

## Global Installation

Some tools support global/user-level steering that applies to all projects:

| Tool | Global Location |
|------|----------------|
| Kiro | `~/.kiro/steering/` |
| Claude Code | `~/CLAUDE.md` |
| Aider | `~/.aider.conf.yml` |

## File Format Reference

### Cursor (.mdc)
```yaml
---
description: Short description for when AI decides to load this rule
globs: "**/*.ts"        # Optional: file pattern for auto-loading
alwaysApply: true       # true = always loaded, false = conditional
---

# Rule content in markdown
```

### Windsurf (.md with frontmatter)
```yaml
---
trigger: always_on      # always_on | manual | model_decision | glob
description: "Human-readable description"
globs:                  # Required when trigger is glob
  - "src/**/*.tsx"
---

# Rule content in markdown
```

### All Others
Plain markdown — no special syntax required.

## Limits

- **Windsurf**: 6,000 chars per rule / 12,000 chars total active
- **Cursor**: Similar per-rule and total budget
- **Others**: No documented hard limits, but shorter = better for context efficiency

## Contributing

1. Edit `shared/conventions.md` with your proposed change
2. Update the relevant tool-specific files to match
3. Submit a PR

## License

MIT
