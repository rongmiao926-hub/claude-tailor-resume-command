# Tailor Resume for Claude

This repository provides a custom Claude Code command at `.claude/commands/tailor-resume.md`.

Its purpose is not just to polish an existing resume. It turns the whole tailoring workflow into one command: absorb multiple resume versions, build a reusable experience pool, batch-read one or many JDs, identify gaps between your background and the role, ask follow-up questions to uncover missing evidence, then rewrite the resume for the target job and output a new Word file.

It is especially useful if you have edited different resume versions for different job directions and do not want valuable experience to stay scattered across old drafts.

## Key Capabilities

### 1. Multiple Resume Versions -> One Experience Pool

You can feed it every resume version you have. It extracts experience, projects, skills, and results from all versions and merges them into one complete experience pool, including details that disappeared from later drafts.

### 2. Batch JD Ingestion

You can feed multiple JDs at once. It supports pasted text, files, links, and screenshots, including folders filled with multiple job-posting images.

### 3. Gap Discovery Through Follow-Up Questions

It compares your background against the JD, finds the gaps, and asks targeted questions. Often the issue is not missing experience, but missing positioning. This helps uncover evidence you already have.

### 4. JD-Specific Rewrite

It rewrites your experience for the specific job using STAR logic. This is not generic keyword replacement. It changes emphasis and language so the resume reads like it was written for that role.

### 5. Keep Layout And Export To Word

It outputs a Word document. If you provide multiple `.docx` resumes, you can choose one as the style reference so the new resume inherits that layout as closely as possible.

## Install

```bash
mkdir -p ~/.claude/commands
curl -L https://raw.githubusercontent.com/rongmiao926-hub/claude-tailor-resume-command/main/.claude/commands/tailor-resume.md \
  -o ~/.claude/commands/tailor-resume.md
```

If the command does not appear immediately, restart Claude Code.

## Beginner-Friendly Usage

After installation, the only thing you need to remember is: start with `/tailor-resume`, then tell Claude where your resumes are and what JD you want to target.

For example:

```text
/tailor-resume ~/Documents/resumes Please build one experience pool from all my resume versions, compare it against this JD, ask me about any missing evidence, and generate a targeted Word resume.
```

```text
/tailor-resume ~/Documents/resumes https://example.com/job/12345
```

```text
/tailor-resume ~/Documents/resumes ~/Documents/jd-screenshots/
```

```text
/tailor-resume ~/Documents/resumes Please reuse the formatting from ~/Documents/resumes/final-resume.docx and tailor my resume for the JD below: ...
```

## Notes

- If you only provide PDF resumes, the command can usually reuse the content but not the original layout.
- If you provide many JDs at once, it will identify the job list first and let you confirm whether to generate all outputs.
- Results are usually best when at least one `.docx` resume is available as the style reference.
