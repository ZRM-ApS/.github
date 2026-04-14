# ZRM-ApS .github Repository

This is the organization-wide defaults repo for [ZRM-ApS](https://github.com/ZRM-ApS). It contains community health files, issue/PR templates, and the org profile that apply across all repos.

## Repo Structure

- `profile/README.md` — Org profile shown at github.com/ZRM-ApS
- `CONTRIBUTING.md` — Dev conventions (branching, commits, PRs, AI tooling)
- `SECURITY.md` — Vulnerability reporting policy
- `LICENSE` — Default proprietary license
- `.github/ISSUE_TEMPLATE/` — Bug report and feature request forms (YAML)
- `.github/PULL_REQUEST_TEMPLATE.md` — Default PR checklist
- `.github/FUNDING.yml` — Sponsor button config

## Key Rules

- This repo **must be public** for org-wide defaults to work
- Files here are inherited by any org repo that doesn't define its own
- `profile/README.md` is always read from this repo (no override)
- Keep all content in English (dev tooling convention)
- No secrets, internal tooling details, or employee counts in any file — everything here is public-facing

## Editing Guidelines

- When updating `CONTRIBUTING.md`, remember it applies to all 21+ repos across different languages and stacks
- Issue templates use YAML form syntax, not markdown
- Test template changes by opening a new issue/PR in a repo that doesn't have its own templates
