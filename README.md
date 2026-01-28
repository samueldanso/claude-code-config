# Claude Code Config

My personal Claude Code configuration — forked from [jarrodwatts/claude-code-config](https://github.com/jarrodwatts/claude-code-config) and customized for my workflow.

## Installation

### Option 1: Git Clone
```bash
git clone https://github.com/samueldanso/claude-code-config.git ~/claude-config-custom

# Copy to ~/.claude/ (won't overwrite existing)
cp -rn ~/claude-config-custom/rules ~/.claude/
cp -rn ~/claude-config-custom/skills ~/.claude/
cp -rn ~/claude-config-custom/agents ~/.claude/
cp -rn ~/claude-config-custom/commands ~/.claude/
cp -rn ~/claude-config-custom/hooks ~/.claude/
cp ~/claude-config-custom/CLAUDE.md ~/.claude/CLAUDE.md
```

### Option 2: Selective Install
```bash
# Clone elsewhere first
git clone https://github.com/samueldanso/claude-code-config.git /tmp/claude-config

# Copy what you need
cp -r /tmp/claude-config/rules/* ~/.claude/rules/
cp -r /tmp/claude-config/skills/* ~/.claude/skills/
cp -r /tmp/claude-config/agents/* ~/.claude/agents/
```

## Contents

### Rules (`.claude/rules/`)

Path-scoped instructions loaded automatically when working with matching files.

| File | Scope | Description |
|------|-------|-------------|
| `typescript.md` | `**/*.{ts,tsx}` | TypeScript conventions |
| `testing.md` | `**/*.{test,spec}.ts` | Testing patterns |
| `comments.md` | All files | Comment policy |

### Skills (`.claude/skills/`)

Model-invoked capabilities Claude applies automatically.

| Skill | Description |
|-------|-------------|
| `planning-with-files` | Manus-style persistent markdown planning |
| `react-useeffect` | React hooks best practices |
| `rigorous-coding` | Strict coding standards |
| `vercel-react-best-practices` | React/Next.js optimization |
| `web-design-guidelines` | UI/UX review |

### Agents (`.claude/agents/`)

Custom subagents for specialized tasks.

| Agent | Description |
|-------|-------------|
| `codebase-search` | Find files and implementations |
| `media-interpreter` | Extract info from PDFs/images |
| `open-source-librarian` | Research OSS with citations |
| `tech-docs-writer` | Create technical documentation |

### Commands (`.claude/commands/`)

Custom slash commands.

| Command | Description |
|---------|-------------|
| `interview` | Interactive planning/spec fleshing |
| `ui-expert` | Pixel-perfect UI implementation mode |

### Hooks (`.claude/hooks/`)

Scripts triggered by Claude Code events.

| Hook | Event | Description |
|------|-------|-------------|
| `keyword-detector.py` | UserPromptSubmit | Detects keywords in prompts |
| `check-comments.py` | PostToolUse (Write/Edit) | Validates comment policy |
| `skill-reminder.sh` | - | Skill reminders |
| `todo-enforcer.sh` | Stop | Ensures todos are tracked |

### CLAUDE.md

Personal global instructions loaded into every session.

## Recommended Plugins

Plugins I use alongside this config. Install via CLI:

### Official Plugins
```bash
claude plugin install frontend-design
claude plugin install code-review
claude plugin install typescript-lsp
claude plugin install plugin-dev
claude plugin install ralph-loop
```

### claude-hud (status line)

Add the marketplace first, then install:
```bash
claude plugin marketplace add jarrodwatts/claude-hud
claude plugin install claude-hud@claude-hud
```

## Credits

Based on [jarrodwatts/claude-code-config](https://github.com/jarrodwatts/claude-code-config)
