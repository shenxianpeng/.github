# .github

Account-wide defaults for [@shenxianpeng](https://github.com/shenxianpeng)'s repositories.

## Default community health files

Any repository in this account that doesn't have its own copy uses these:

- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to contribute
- [`SECURITY.md`](SECURITY.md) — how to report a vulnerability
- [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) — bug report and feature request forms
- [`.github/FUNDING.yml`](.github/FUNDING.yml) — sponsor button

A repository's own file always takes precedence.

## Reusable workflows

Call them from any repository:

```yaml
jobs:
  pre-commit:
    uses: shenxianpeng/.github/.github/workflows/pre-commit.yml@main
```

| Workflow | What it does |
|----------|--------------|
| [`pre-commit.yml`](.github/workflows/pre-commit.yml) | Run [pre-commit](https://pre-commit.com/) on all files |
| [`codeql.yml`](.github/workflows/codeql.yml) | [CodeQL](https://codeql.github.com/) static analysis |
| [`pr-labeler.yml`](.github/workflows/pr-labeler.yml) | Label PRs by branch name and title |
| [`release-drafter.yml`](.github/workflows/release-drafter.yml) | Draft release notes from merged PRs |
| [`stale.yml`](.github/workflows/stale.yml) | Close stale issues and PRs |
| [`mkdocs.yml`](.github/workflows/mkdocs.yml) | Deploy [MkDocs](https://www.mkdocs.org/) docs to GitHub Pages |
| [`sphinx.yml`](.github/workflows/sphinx.yml) | Deploy [Sphinx](https://www.sphinx-doc.org/) docs to GitHub Pages |
| [`py-publish.yml`](.github/workflows/py-publish.yml) | Publish a Python package to PyPI / TestPyPI |
| [`snyk-container.yml`](.github/workflows/snyk-container.yml) | Scan a container image with [Snyk](https://snyk.io/) |
| [`repokeeper-*.yml`](.github/workflows/) | [RepoKeeper](https://github.com/shenxianpeng/repokeeper) AI agents: labeler, agent, radar, patrol |

See each workflow file for its inputs and secrets.

## License

[MIT](LICENSE)
