---
type: Tool
title: ty
description: A Python type checker and language server written in Rust, from Astral; currently in beta.
resource: https://docs.astral.sh/ty/
tags:
  - python
  - type-checker
  - language-server
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: ty
    resource: https://github.com/astral-sh/ty
    title: astral-sh/ty README
  - id: ty-docs
    resource: https://docs.astral.sh/ty/installation/
    title: ty installation, module discovery and migration docs
  - id: packages
    resource: https://formulae.brew.sh/formula/ty
    title: "Homebrew: ty; winget: astral-sh.ty"
---
# ty

A Python type checker and language server written in Rust, made by Astral, the company behind uv and [Ruff](./ruff.md). Licensed under MIT.[^ty]

- **Beta.** ty uses `0.0.x` versions and has no stable API yet; breaking changes, including to diagnostics, can land in any release. For a stable checker, use [mypy](./mypy.md).[^ty]
- **Language server:** code navigation, completions, code actions, auto-import, inlay hints and hover help, with integrations for VS Code, PyCharm and Neovim.[^ty]
- **Configurable:** rule levels, per-file overrides and suppression comments (`# ty: ignore[rule]`). The docs have a guide for moving from mypy or Pyright.[^ty] [^ty-docs]
- Officially supports code that targets Python 3.10 and later.[^ty]

## Install

| Platform | Command |
| --- | --- |
| Any (recommended) | `uv add --dev ty` (per project) or `uv tool install ty@latest` (global) |
| macOS | `brew install ty` |
| Windows (recommended) | `winget install astral-sh.ty` |
| Windows (alternative) | `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/ty/install.ps1 \| iex"` |
| Linux | `curl -LsSf https://astral.sh/ty/install.sh \| sh` or `brew install ty` |

The docs recommend adding ty as a project dev dependency so everyone uses the same version.[^ty-docs] Since any release can break things, that pin matters more than usual. There's no Chocolatey package. On 2026-10-21, PyPI and Homebrew had 0.0.90 but winget had 0.0.87.[^packages]

## Use

```sh
uvx ty check          # try it without installing
uv run ty check       # in a uv project
```

ty finds third-party packages in the active virtual environment or a `.venv` in the project root; `uv run` takes care of that.[^ty-docs]

## See also

- [mypy](./mypy.md)
- [Python developer tools](../concepts/python-tools.md)
- [Python dev environments](../concepts/python-dev-environments.md)

[^ty]: [astral-sh/ty README](https://github.com/astral-sh/ty)
[^ty-docs]: [Installing ty](https://docs.astral.sh/ty/installation/), [Module discovery](https://docs.astral.sh/ty/modules/) and [Coming from mypy or pyright](https://docs.astral.sh/ty/coming-from-mypy-or-pyright/)
[^packages]: Homebrew: [ty](https://formulae.brew.sh/formula/ty); winget: [astral-sh.ty](https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/astral-sh/ty); versions checked 2026-10-21
