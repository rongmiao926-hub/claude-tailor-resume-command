# Claude Tailor Resume Command

This repository contains a Claude custom command at `.claude/commands/tailor-resume.md`.

## Install

```bash
mkdir -p ~/.claude/commands
curl -L https://raw.githubusercontent.com/rongmiao926-hub/claude-tailor-resume-command/main/.claude/commands/tailor-resume.md \
  -o ~/.claude/commands/tailor-resume.md
```

Restart Claude Code after installation if the command does not appear immediately.

## Usage

```text
/tailor-resume ~/Documents/resumes https://example.com/job/12345
```
