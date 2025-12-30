# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a collection of reusable rules and knowledge documents for AI coding assistants (Claude Code, Cursor). It contains no executable code - only documentation files in `.mdc` format (Markdown with Configuration).

## Directory Structure

- **project-rules/** - Actionable rules for AI assistants (slash commands)
- **docs/** - Reference documentation and knowledge bases (Swift, MCP)
- **global-rules/** - Global Claude Code configuration and scripts for `~/.claude/CLAUDE.md`

## File Format

All rule files use `.mdc` extension with YAML frontmatter:
```yaml
---
description: Brief description
globs: ["**/*.swift"]  # File patterns (Cursor uses this)
alwaysApply: true/false
---
```
Cursor uses the frontmatter; Claude Code ignores it and reads only the markdown content.

## Installation Script

```bash
./install-project-rules.sh  # Installs slash commands to ~/.claude/CLAUDE.md
```

## Issue Tracking

This project uses **bd** (beads) for issue tracking:
```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --status in_progress
bd close <id>
bd sync               # Sync with git
```

## Contributing Rules

New rules must:
1. Use `.mdc` extension
2. Include YAML frontmatter with `description`, `globs`, `alwaysApply`
3. Be placed in the appropriate directory based on purpose
