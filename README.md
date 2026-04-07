# my account wide settings

Central configuration repository for [@shenxianpeng](https://github.com/shenxianpeng)'s GitHub account.
Contains reusable workflows, default community health files, and shared configuration that applies across repositories.

## Reusable Workflows

All workflows under [`.github/workflows/`](.github/workflows/) are published as reusable workflows (`on: workflow_call`) and can be called from any repository.

### [`pre-commit.yml`](.github/workflows/pre-commit.yml)

Run [pre-commit](https://pre-commit.com/) hooks across all files.

```yaml
jobs:
  pre-commit:
    uses: shenxianpeng/.github/.github/workflows/pre-commit.yml@main
    with:
      commands: ""   # optional: extra setup commands to run before pre-commit
```

### [`codeql.yml`](.github/workflows/codeql.yml)

Run [CodeQL](https://codeql.github.com/) static analysis.

```yaml
jobs:
  codeql:
    uses: shenxianpeng/.github/.github/workflows/codeql.yml@main
    with:
      language: python   # default: python — also supports c-cpp, csharp, go, java-kotlin, javascript-typescript, ruby, swift
```

### [`release-drafter.yml`](.github/workflows/release-drafter.yml)

Draft the next release notes as pull requests are merged.

```yaml
jobs:
  release-drafter:
    uses: shenxianpeng/.github/.github/workflows/release-drafter.yml@main
```

### [`pr-labeler.yml`](.github/workflows/pr-labeler.yml)

Automatically label pull requests based on branch name and title.

```yaml
jobs:
  label:
    uses: shenxianpeng/.github/.github/workflows/pr-labeler.yml@main
```

### [`stale.yml`](.github/workflows/stale.yml)

Close stale issues and pull requests automatically.

```yaml
jobs:
  stale:
    uses: shenxianpeng/.github/.github/workflows/stale.yml@main
```

### [`mkdocs.yml`](.github/workflows/mkdocs.yml)

Build and deploy [MkDocs](https://www.mkdocs.org/) documentation to GitHub Pages.

```yaml
jobs:
  docs:
    uses: shenxianpeng/.github/.github/workflows/mkdocs.yml@main
```

### [`sphinx.yml`](.github/workflows/sphinx.yml)

Build and deploy [Sphinx](https://www.sphinx-doc.org/) documentation to GitHub Pages.

```yaml
jobs:
  docs:
    uses: shenxianpeng/.github/.github/workflows/sphinx.yml@main
    with:
      path-to-doc: docs/_build/html   # default: docs/_build/html
```

### [`py-publish.yml`](.github/workflows/py-publish.yml)

Build and publish a Python package to PyPI / TestPyPI.

```yaml
jobs:
  publish:
    uses: shenxianpeng/.github/.github/workflows/py-publish.yml@main
    secrets:
      PYPI_API_TOKEN: ${{ secrets.PYPI_API_TOKEN }}
      TEST_PYPI_API_TOKEN: ${{ secrets.TEST_PYPI_API_TOKEN }}
```

### [`snyk-container.yml`](.github/workflows/snyk-container.yml)

Scan a Docker image for vulnerabilities with [Snyk](https://snyk.io/).

```yaml
jobs:
  snyk:
    uses: shenxianpeng/.github/.github/workflows/snyk-container.yml@main
    with:
      image: myorg/myimage:latest
      dockerfile: Dockerfile          # default: Dockerfile
      severity-threshold: high        # default: high
    secrets:
      SNYK_TOKEN: ${{ secrets.SNYK_TOKEN }}
```

## Community Health Files

The following default community health files apply to all repositories in the account that do not have their own:

| File | Description |
|------|-------------|
| [`.github/ISSUE_TEMPLATE/bug_report.yml`](.github/ISSUE_TEMPLATE/bug_report.yml) | Bug report issue form |
| [`.github/ISSUE_TEMPLATE/feature_request.yml`](.github/ISSUE_TEMPLATE/feature_request.yml) | Feature request issue form |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | Pull request template |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution guidelines |
| [`SECURITY.md`](SECURITY.md) | Security policy and vulnerability reporting |

## Other Configuration

| File | Description |
|------|-------------|
| [`.github/FUNDING.yml`](.github/FUNDING.yml) | GitHub Sponsors / funding links |
| [`.github/dependabot.yml`](.github/dependabot.yml) | Dependabot version update schedule |
| [`.github/release-drafter.yml`](.github/release-drafter.yml) | Release Drafter label categories and template |
| [`.github/stale.yml`](.github/stale.yml) | Stale bot configuration (legacy probot) |
| [`.pre-commit-config.yaml`](.pre-commit-config.yaml) | Pre-commit hooks for this repository |
