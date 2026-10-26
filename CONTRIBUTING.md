# Contributing

Guidelines for contributing to ZRM repositories.

## Getting Started

1. Clone the repository
2. Install dependencies as described in the project's README
3. Create a new branch from `main` (or `dev` if the project uses one)

## Branching

| Branch | Purpose |
|--------|---------|
| `main` | Production-ready code. Protected — no direct pushes. |
| `dev` | Integration branch (where applicable). |
| `feature/<short-description>` | New features |
| `fix/<short-description>` | Bug fixes |
| `hotfix/<short-description>` | Urgent production fixes |

Keep branch names lowercase and hyphenated: `feature/add-pdf-export`, not `feature/Add_PDF_Export`.

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
