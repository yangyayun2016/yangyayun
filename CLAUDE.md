# CLAUDE.md

This file provides guidance to AI assistants (Claude and others) when working with this repository.

## Repository Overview

**Owner:** yangyayun2016
**Repository:** yangyayun
**Status:** New — first site is [www.helabs.fun](https://www.helabs.fun). No application source yet.
**Payments:** Sentra (Dodo Payments). The retired IDE extension is replaced by the Dodo Agent Plugin.

This file will be updated as the project evolves to reflect the actual codebase structure, conventions, and workflows.

---

## General Development Guidelines

### Branching Strategy

- All feature work happens on branches prefixed with `claude/` for AI-assisted work.
- Branch naming: `claude/<task-slug>-<session-id>`
- Never push directly to `main` or `master` without an explicit pull request review.

### Commit Conventions

- Write clear, descriptive commit messages in the imperative mood.
  - Good: `Add user authentication module`
  - Bad: `added stuff` / `fix`
- Commit messages should be concise (50 chars for subject line) with an optional body explaining *why*.
- Keep commits atomic — each commit should represent a single logical change.

### Pull Requests

- Open a PR for every non-trivial change.
- PRs should include a summary of *what* changed and *why*.
- Link related issues in the PR description when applicable.

---

## Code Style & Quality

Since no language or framework has been established yet, the following defaults apply until project-specific conventions are documented below:

- Follow the dominant style of whichever language/framework is adopted.
- Prefer readability over cleverness.
- Avoid over-engineering — write the minimum code needed for the task.
- Do not add unused imports, dead code, or placeholder comments.
- Remove code rather than commenting it out.

---

## Testing

- Write tests for all non-trivial logic before or alongside the implementation.
- Tests should be deterministic and isolated (no network calls or shared state by default).
- Run the full test suite before committing.

---

## Security

- Never commit secrets, credentials, API keys, or tokens.
- Validate all user input at system boundaries.
- Avoid introducing OWASP Top 10 vulnerabilities (SQL injection, XSS, command injection, etc.).

---

## Project-Specific Sections (To Be Filled In)

As the codebase is built out, update this file to document:

### Directory Structure

```
.cursor/mcp.json    # Dodo Payments MCP servers for this site
```

### Sentra / Dodo Payments

Sentra’s IDE extension is retired. This repo uses its replacement, the Dodo Agent Plugin (v0.6.5), so billing work for www.helabs.fun stays inside the editor.

Editor install (already done in this environment):

```bash
git clone https://github.com/dodopayments/dodo-agent-plugin.git ~/.cursor/plugins/local/dodo-agent-plugin
```

Restart the editor after cloning. Skills load from `skills/`; MCP servers load from the plugin’s `.mcp.json`. The project file `.cursor/mcp.json` registers the same two servers for anyone who opens this repo:

- `dodo-knowledge` — documentation search, no credentials
- `dodopayments-api` — live account access via browser OAuth (no API key in the repo)

Use test mode until the site is ready to charge real customers. Never commit API keys or webhook secrets.

### Build & Run Commands

```bash
# Install dependencies
<command>

# Run the application
<command>

# Run tests
<command>

# Lint / format
<command>
```

### Key Conventions

- Language(s): _TBD_
- Framework(s): _TBD_
- Package manager: _TBD_
- CI/CD: _TBD_
- Payments: Dodo Payments via the Sentra successor plugin (Dodo Agent Plugin)
- Site: www.helabs.fun

### Environment Setup

Document required environment variables, configuration files, and local setup steps here.

---

## Working with AI Assistants

When working with Claude or another AI assistant in this repository:

1. **Read before editing** — always read the relevant file(s) before proposing changes.
2. **Stay focused** — only change what was explicitly requested; avoid unrelated refactors.
3. **Verify** — run tests and linters after making changes.
4. **Ask when uncertain** — if requirements are ambiguous, ask before implementing.
5. **Keep this file up to date** — update `CLAUDE.md` whenever project conventions change significantly.
