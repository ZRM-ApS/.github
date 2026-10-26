# Contributing

Guidelines for contributing to ZRM repositories.

## Getting Started

1. Clone the repository
2. Install dependencies as described in the project's README
3. Create a new branch from `main` (or `dev` if the project uses one)

## Branching

We follow [Conventional Branch 1.1.0](https://conventionalbranch.org/), using the short prefixes that match our commit types.

### Long-lived branches

| Branch | Environment | Notes |
|--------|-------------|-------|
| `main` | Production | Always deployable. No direct pushes. |
| `preprod` | Preprod | Only in projects with a preprod environment. |
| `dev` | Development | Integration branch, where the project uses one. |

Changes move in one direction: work branches merge into `dev`, `dev` is promoted to `preprod`, and `preprod` is promoted to `main`. Projects without `dev` or `preprod` skip that step. Promote with a pull request, never by pushing.

Do not create a separate `prod` branch: `main` is production.

### Work branches

Format: `<type>/<description>`, or `<type>/<task-id>-<description>` when there is a task.

| Prefix | Use for |
|--------|---------|
| `feat/` | New features |
| `fix/` | Bug fixes |
| `hotfix/` | Urgent production fixes. Branch from `main`, then merge back into `preprod` and `dev` |
| `docs/` | Documentation only |
| `chore/` | Build, tooling, dependency updates |
| `refactor/`, `test/`, `perf/`, `ci/` | Same meaning as the commit types below |
| `release/` | Release preparation, e.g. `release/v1.2.0` |

Branches created by tools keep their own prefixes, such as `claude/` and `dependabot/`.

### Naming rules

- Lowercase letters `a-z`, digits `0-9` and hyphens only. No uppercase, underscores, spaces or Danish letters (æ, ø, å).
- Dots only in version numbers.
- Short and descriptive: `feat/add-pdf-export`, not `feat/Add_PDF_Export`.

## Commit Messages

Use this format:

```
type: short description
```

**Types:**

| Type | Use for |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, whitespace (no logic change) |
| `refactor` | Code restructuring (no behavior change) |
| `test` | Adding or updating tests |
| `chore` | Build, tooling, dependency updates |

**Rules:**
- Keep the subject line under 72 characters
- Use imperative mood: "add export" not "added export"
- Reference issues when applicable: `fix: resolve login timeout (#42)`

**Examples:**
```
feat: add price calculator export to PDF
fix: resolve null pointer in user lookup
chore: upgrade Node.js to v20
```

## Pull Requests

- Create a PR for all changes — no direct pushes to `main` or `dev`
- Use the [PR template](/.github/PULL_REQUEST_TEMPLATE.md) (auto-filled on new PRs)
- Keep PRs focused: one feature or fix per PR
- Request review from at least one team member
- Link related issues in the PR description

## Code Style

- Follow existing patterns in the repository
- Use project linter and formatter configs where available
- For JavaScript/Node.js projects, prefer TypeScript
- Write self-documenting code; add comments only where the logic isn't obvious

## AI-Assisted Development

We use AI tools (Claude Code, Cursor, Copilot, etc.) across projects. To keep collaboration smooth:

### Project Files to Commit

| File/Directory | Purpose |
|----------------|---------|
| `CLAUDE.md` | Project-level instructions for Claude Code — conventions, architecture notes, key commands |
| `.claude/settings.json` | Shared Claude Code permissions and tool configs |
| `.cursorrules` | Project conventions for Cursor |
| `.github/copilot-instructions.md` | Repository-level instructions for GitHub Copilot |
| `.ai/` | Shared prompts, templates, or agent configs used across the team |

### Files to NOT Commit

| File/Directory | Purpose |
|----------------|---------|
| `.claude/settings.local.json` | Personal Claude Code permissions (already in `.gitignore`) |
| `.claude/todos/`, `.claude/plans/` | Session-specific working state |
| `.cursor/` | Local Cursor state |

### Guidelines

- Keep `CLAUDE.md` up to date when project conventions change — it's the AI's onboarding doc
- Review AI-generated code with the same rigor as human-written code
- AI-authored commits must not include `Co-Authored-By` or any other AI attribution (commits, PRs, tags)
- Don't commit AI conversation logs or session artifacts
- When adding new shared AI config files, document their purpose in the project README

## Issues

- Use the provided [issue templates](/.github/ISSUE_TEMPLATE/) for bug reports and feature requests
- Reference issues in commits and PRs using `#issue-number`
- For anything that doesn't fit a template, open a blank issue
