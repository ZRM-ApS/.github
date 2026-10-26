# .github

Organization-wide GitHub defaults for [ZRM ApS](https://zrm.dk).

This repository contains community health files and templates that apply across all repositories in the ZRM-ApS organization. Individual repos can override any of these by defining their own versions.

## Contents

| File | Purpose |
|------|---------|
| [profile/README.md](profile/README.md) | Organization profile shown at [github.com/ZRM-ApS](https://github.com/ZRM-ApS) |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Development conventions — branching, commits, PRs, code style |
| [SECURITY.md](SECURITY.md) | How to report security vulnerabilities |
| [LICENSE](LICENSE) | Default proprietary license |
| [.github/ISSUE_TEMPLATE/](.github/ISSUE_TEMPLATE/) | Bug report and feature request forms |
| [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) | Default pull request template |

## How Defaults Work

GitHub automatically applies these files to any repository in the organization that does not define its own. For example:

- A repo without `CONTRIBUTING.md` will use this one
- A repo with its own `.github/ISSUE_TEMPLATE/` will use its own templates, not these
- The org profile (`profile/README.md`) is always read from this repo

For more details, see [GitHub's documentation on default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).
