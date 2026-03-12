# Tailor Resume for Claude

> ✨ Turn multiple resume versions and one or more JDs into a Word resume that is actually tailored for the target role.

## 🚀 Get Started In 3 Steps

1. Install Claude Code
2. Install this `tailor-resume` command
3. Tell it where your resumes are, where the JD is, and ask it to tailor the resume

For example:

```text
/tailor-resume Help me tailor my resume. My resumes are in ~/Documents/resumes/, my JDs are in ~/Documents/jds/, and I want a Word resume tailored for this role.
```

## ⚠️ Before you start

This repository is not Claude Code itself. It is a custom command that needs to be installed inside Claude Code.

So before using this repository, install Claude Code first.

## 🖥️ Install Claude Code first

If you do not have Claude Code yet:

1. Open Anthropic's official quickstart: [Claude Code Quickstart](https://code.claude.com/docs/en/quickstart)
2. Follow Anthropic's setup instructions.
3. On macOS, Linux, and WSL, Anthropic currently recommends the native installer:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

4. After installation, run `claude` in your terminal.
5. Log in with your Claude account when prompted.
6. Then come back and install this `tailor-resume` command.

If you are on Windows or another environment, follow the official quickstart for the latest supported install path.

This repository provides a custom Claude Code command at `.claude/commands/tailor-resume.md`. 🎯

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

## 🔧 Then install this command

```bash
mkdir -p ~/.claude/commands
curl -L https://raw.githubusercontent.com/rongmiao926-hub/claude-tailor-resume-command/main/.claude/commands/tailor-resume.md \
  -o ~/.claude/commands/tailor-resume.md
```

If the command does not appear immediately, restart Claude Code.

## 💬 Beginner-Friendly Usage

After installation, the only thing you need to remember is: start with `/tailor-resume`, then tell Claude where your resumes are and where the JD is, as if you were chatting normally.

For example:

```text
/tailor-resume Help me tailor my resume. My resumes are in ~/Documents/resumes/. Please build one experience pool from all my resume versions, compare it against this JD, ask me about any missing evidence, and generate a targeted Word resume.
```

```text
/tailor-resume Help me tailor my resume. My resumes are in ~/Documents/resumes/, and the JD link is here: https://example.com/job/12345
```

```text
/tailor-resume Help me tailor my resume. My resumes are in ~/Documents/resumes/, and all JD screenshots are in ~/Documents/jd-screenshots/
```

```text
/tailor-resume Help me tailor my resume. My resumes are in ~/Documents/resumes/. Please reuse the formatting from ~/Documents/resumes/final-resume.docx and tailor my resume for the JD below: ...
```

## 📝 Notes

- If you only provide PDF resumes, the command can usually reuse the content but not the original layout.
- If you provide many JDs at once, it will identify the job list first and let you confirm whether to generate all outputs.
- Results are usually best when at least one `.docx` resume is available as the style reference.
