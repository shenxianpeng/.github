# Contributing

Thank you for your interest in contributing! Here are a few guidelines to help get started.

## Getting Started

1. Fork the repository and create a new branch from `main`.
2. Make your changes, following the conventions already in use.
3. Open a pull request with a clear description of what you changed and why.

## Reporting Bugs

Please open an issue using the **Bug Report** template and include as much detail as possible.

## Suggesting Features

Please open an issue using the **Feature Request** template describing the problem you'd like to solve and your proposed solution.

## Pull Request Guidelines

- Keep changes focused — one fix or feature per PR.
- Ensure pre-commit checks pass locally before opening a PR (`pre-commit run --all-files`).
- Update documentation when your change affects documented behavior.

## Reusable Workflows

If you are adding or modifying a reusable workflow under `.github/workflows/`, please ensure:

- The workflow uses `on: workflow_call` so it can be called from other repositories.
- All required secrets are declared in `secrets:` so callers know what to provide.
- Inputs have sensible defaults where possible and are documented with `description:`.
