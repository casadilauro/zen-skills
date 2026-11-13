# Python Tooling

Follow the repository.

Inspect `pyproject.toml` and existing configuration before choosing tools.

Potential tools include:

- Ruff
- Black
- pytest
- mypy
- pyright
- ty
- uv
- tox
- nox

Do not introduce competing tools without a concrete reason.

## Package Management

Use the project's selected package manager.

Do not introduce Poetry, uv, pip-tools, pipenv, or another manager merely
because you prefer it.

## Formatting

Use the configured formatter.

Do not manually fight formatting rules.

## Linting

Use the configured linter.

Fix meaningful warnings rather than globally suppressing them.

## Type Checking

Use the configured checker and strictness level.

Do not rewrite large portions of unrelated code solely to satisfy a newly
introduced checker.

## Tests

Run the smallest relevant tests during iteration.

Run broader project checks before completion when practical.

## Configuration

Prefer consolidating tool configuration in the repository's established
location.

Avoid duplicate configuration files expressing conflicting rules.
