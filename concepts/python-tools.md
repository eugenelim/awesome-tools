---
type: Category
title: Python developer tools
description: Linting, formatting, type checking, testing and Git hook tools for Python projects.
---
# Python developer tools

Linting, formatting, type checking, testing and Git hook tools for Python projects. For installing Python and managing environments, see [Python dev environments](./python-dev-environments.md), which recommends uv; the commands below assume it.

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [Ruff](../tools/ruff.md) (linter and formatter) | MIT | `brew install ruff` | `winget install astral-sh.ruff` | `uv tool install ruff@latest` |
| [mypy](../tools/mypy.md) (type checker) | MIT | `uv add --dev mypy` | `uv add --dev mypy` | `uv add --dev mypy` |
| [ty](../tools/ty.md) (type checker, beta) | MIT | `brew install ty` | `winget install astral-sh.ty` | `uv tool install ty@latest` |
| [pytest](../tools/pytest.md) (testing) | MIT | `uv add --dev pytest` | `uv add --dev pytest` | `uv add --dev pytest` |
| [pre-commit](../tools/pre-commit.md) (Git hooks) | MIT | `brew install pre-commit` | `uv tool install pre-commit` | `uv tool install pre-commit` |

`uv add --dev` adds a tool to one project's development dependencies, so everyone on the project gets the same version; run it with `uv run`. `uv tool install` installs a command globally. Type checkers and pytest need your project installed, so run them with `uv run`, not `uvx`. See [mypy](../tools/mypy.md#install) and [pytest](../tools/pytest.md#install).

For a type checker, use [mypy](../tools/mypy.md), which is stable. [ty](../tools/ty.md) comes from Astral, like uv and Ruff, but it's in beta and its diagnostics can change between releases.
