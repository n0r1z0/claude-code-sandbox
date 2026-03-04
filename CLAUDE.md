# CLAUDE.md

This file provides guidance for AI assistants (like Claude) working in this repository.

## Repository Overview

**Repository:** `n0r1z0/claude-code-sandbox`
**Purpose:** A sandbox environment for experimenting with Claude Code workflows, tooling, and automation.

This repository is currently in its initial state. As code and structure are added, update this file to reflect the actual codebase.

## Repository Structure

```
claude-code-sandbox/
└── CLAUDE.md          # This file — AI assistant guidance
```

As the project grows, document new directories and their purposes here.

## Git Workflow

### Branch Naming
- Feature/task branches follow the pattern: `claude/<description>-<session-id>`
- Example: `claude/claude-md-mmc78t179xoqhbns-9zs04`

### Commit Conventions
- Write clear, descriptive commit messages in the imperative mood
- Keep commits focused on a single logical change
- Example: `Add initial project structure` not `Added stuff`

### Push Protocol
- Always use `git push -u origin <branch-name>` for first push of a branch
- Branch names must start with `claude/` and end with the matching session ID, or push will fail with HTTP 403
- If push fails due to network errors, retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s)

## Development Guidelines for AI Assistants

### General Principles
- Read files before editing them — never propose changes to code you haven't read
- Prefer editing existing files over creating new ones
- Avoid over-engineering: implement only what is directly requested
- Do not add comments, docstrings, or type annotations to code you didn't change
- Keep solutions minimal and focused

### Security
- Never introduce command injection, XSS, SQL injection, or other OWASP Top 10 vulnerabilities
- Validate input only at system boundaries (user input, external APIs)
- Do not commit secrets, credentials, or `.env` files

### Risky Actions — Always Confirm First
Before performing any of the following, confirm with the user:
- Deleting files, branches, or data
- Force-pushing or amending published commits
- Pushing to remote branches
- Modifying CI/CD pipelines or shared infrastructure
- Actions visible to others (creating PRs, posting comments, sending messages)

## Working with This Sandbox

Since this is a sandbox repository, it is safe to experiment. However, good habits still apply:
- Document what you build in this file as the project evolves
- Keep the git history clean and meaningful
- Treat each experiment as if it could become production code

## Updating This File

When the codebase changes significantly, update this CLAUDE.md to reflect:
- New directories and their purposes
- Dependencies and how to install them
- Build, test, and lint commands
- Environment variables required
- Any project-specific conventions or gotchas
