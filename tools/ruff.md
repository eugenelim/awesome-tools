---
type: Tool
title: Ruff
description: A Python linter and code formatter written in Rust, from Astral, the makers of uv.
resource: https://docs.astral.sh/ruff/
tags:
  - python
  - linter
  - formatter
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: ruff
    resource: https://github.com/astral-sh/ruff
    title: astral-sh/ruff README
  - id: ruff-install
    resource: https://docs.astral.sh/ruff/installation/
    title: Installing Ruff
  - id: packages
    resource: https://formulae.brew.sh/formula/ruff
    title: "Homebrew: ruff; winget: astral-sh.ruff; Chocolatey: ruff"
---
# Ruff

A Python linter and code formatter written in Rust, made by Astral, the company behind uv and [ty](./ty.md). Licensed under MIT.[^ruff] [^packages]

- **Linter and formatter in one.** `ruff check` lints and `ruff format` formats.[^ruff]
- **Replaces several tools.** The project says Ruff can replace Flake8 (and dozens of plugins), Black, isort, pydocstyle, pyupgrade and autoflake, with drop-in parity with Flake8, isort and Black.[^ruff]
- **Over 900 built-in rules**, including re-implementations of Flake8 plugins such as flake8-bugbear. Many fixes apply automatically, for example removing unused imports.[^ruff]
- **Configured in `pyproject.toml`**, with cascading configuration for monorepos and caching of unchanged files.[^ruff]

## Install

| Platform | Command |
| --- | --- |
| Any (recommended) | `uv tool install ruff@latest` (global) or `uv add --dev ruff` (per project) |
| macOS | `brew install ruff` |
| Windows (recommended) | `winget install astral-sh.ruff` |
| Windows (alternatives) | `choco install ruff`, or `powershell -c "irm https://astral.sh/ruff/install.ps1 \| iex"` |
| Linux | `curl -LsSf https://astral.sh/ruff/install.sh \| sh`, `brew install ruff`, or your distribution's package |

The Ruff docs recommend uv.[^ruff] [^ruff-install] You can also run it without installing: `uvx ruff check`.[^ruff] On 2026-10-21, PyPI, Homebrew and winget had 0.17.1 but Chocolatey had 0.16.9, so winget is the better choice on Windows.[^packages]

## Use

```sh
ruff check            # lint the current directory
ruff check --fix      # lint and apply fixes
ruff format           # format the current directory
```

Ruff also runs as a [pre-commit](./pre-commit.md) hook from `astral-sh/ruff-pre-commit` (hook ids `ruff-check` and `ruff-format`), and has editor integrations, including a VS Code extension.[^ruff]

## See also

- [Python developer tools](../concepts/python-tools.md)
- [Python dev environments](../concepts/python-dev-environments.md)

[^ruff]: [astral-sh/ruff README](https://github.com/astral-sh/ruff)
[^ruff-install]: [Installing Ruff](https://docs.astral.sh/ruff/installation/)
[^packages]: Homebrew: [ruff](https://formulae.brew.sh/formula/ruff); winget: [astral-sh.ruff](https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/astral-sh/ruff); Chocolatey: [ruff](https://community.chocolatey.org/packages/ruff); versions checked 2026-10-21
