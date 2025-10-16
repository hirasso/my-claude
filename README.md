# My Claude Config

Personal configuration repo for [Claude Code CLI](https://www.claude.com/product/claude-code) with persistent development preferences.

## What is this?

Version-controlled workspace where `CLAUDE.md` automatically loads my preferences into every Claude session. Alternative to repeating preferences or using the web interface.

## How it works

Claude Code reads `CLAUDE.md` from:
- Global: `~/.claude/CLAUDE.md`
- Project: `<project-root>/CLAUDE.md`

This repo stores my preferences for conversational sessions.

## What's configured?

See [CLAUDE.md](CLAUDE.md):
- Environment: macOS, fish, VS Code
- Code style & workflow rules
- Communication preferences

## Usage

```bash
cd /path/to/my-claude
claude  # Preferences auto-loaded
```

You can make the instructions global by copying them to to `~/.claude/CLAUDE.md`.