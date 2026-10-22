---
type: Tool
title: mypy
description: A static type checker for Python that checks code annotated with PEP 484 type hints.
resource: https://www.mypy-lang.org/
tags:
  - python
  - type-checker
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: mypy
    resource: https://github.com/python/mypy
    title: python/mypy README and LICENSE
  - id: uv-deps
    resource: https://docs.astral.sh/uv/guides/tools/
    title: uv tools guide and development dependencies docs
  - id: packages
    resource: https://formulae.brew.sh/formula/mypy
    title: "Homebrew: mypy; PyPI: mypy"
---
# mypy

A static type checker for Python. You add type hints (PEP 484) and mypy warns when your code uses those types incorrectly, without running it. Licensed under MIT; three files in mypyc's runtime library are under the PSF 2 licence.[^mypy]

- **Gradual typing:** add hints a little at a time and fall back to dynamic typing where static typing is awkward. Hints don't change how the program runs.[^mypy]
- **Type system:** type inference, generics, callable types, tuple types, union types and structural subtyping.[^mypy]
- **Daemon mode** (`dmypy`) gives much faster incremental re-checks on large code bases.[^mypy]
- mypy is compiled with mypyc, which the project says makes it about four times faster than running interpreted.[^mypy]

## Install

| Platform | Command |
| --- | --- |
| Any (recommended) | `uv add --dev mypy`, then `uv run mypy` |
| macOS | `brew install mypy` |

The README installs it with `python3 -m pip install -U mypy`.[^mypy] In a uv project, add it as a development dependency. uv's docs say tools that need your project installed, like mypy, should run with `uv run` rather than `uvx`, or they run isolated from your project.[^uv-deps] There's no winget or Chocolatey package. On 2026-10-21, PyPI and Homebrew both had 2.4.0.[^packages]

## Use

```sh
mypy PROGRAM              # type-check a program
dmypy run -- PROGRAM      # daemon mode for fast incremental checks
```

The README also lists editor integrations (VS Code, Vim, Emacs, Sublime Text, PyCharm) and a [pre-commit](./pre-commit.md) hook from `pre-commit/mirrors-mypy`. It warns that by default this hook limits mypy's ability to analyse third-party dependencies.[^mypy]

## See also

- [ty](./ty.md): Astral's type checker, in beta
- [Python developer tools](../concepts/python-tools.md)
- [Python dev environments](../concepts/python-dev-environments.md)

[^mypy]: [python/mypy README](https://github.com/python/mypy) and [LICENSE](https://github.com/python/mypy/blob/master/LICENSE)
[^uv-deps]: [uv: Using tools](https://docs.astral.sh/uv/guides/tools/) and [Development dependencies](https://docs.astral.sh/uv/concepts/projects/dependencies/#development-dependencies)
[^packages]: Homebrew: [mypy](https://formulae.brew.sh/formula/mypy); PyPI: [mypy](https://pypi.org/project/mypy/); versions checked 2026-10-21
