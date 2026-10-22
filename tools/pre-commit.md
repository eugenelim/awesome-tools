---
type: Tool
title: pre-commit
description: A framework for managing and running multi-language Git pre-commit hooks.
resource: https://pre-commit.com/
tags:
  - python
  - git
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: pre-commit
    resource: https://pre-commit.com/
    title: pre-commit documentation
  - id: uv-tools
    resource: https://docs.astral.sh/uv/guides/tools/
    title: uv tools guide
  - id: packages
    resource: https://formulae.brew.sh/formula/pre-commit
    title: "Homebrew: pre-commit; PyPI: pre-commit"
---
# pre-commit

A framework for managing and maintaining multi-language Git pre-commit hooks. It's written in Python but works for any project. Licensed under MIT.[^pre-commit]

- You list hooks in `.pre-commit-config.yaml`; pre-commit installs them and runs them before every commit.[^pre-commit]
- **Any language:** pre-commit installs each hook's toolchain itself (for example, downloading and building Node to run eslint), without root access.[^pre-commit]

## Install

| Platform | Command |
| --- | --- |
| Any (recommended) | `uv tool install pre-commit` |
| macOS | `brew install pre-commit` |

The docs install it with `pip install pre-commit`, or offer a zero-dependency `.pyz` zipapp on GitHub releases.[^pre-commit] `uv tool install` puts a package's commands on `PATH` in their own environment.[^uv-tools] There's no winget or Chocolatey package. On 2026-10-21, PyPI and Homebrew both had 4.7.0.[^packages]

## Use

```sh
pre-commit sample-config > .pre-commit-config.yaml   # starter config
pre-commit install                                    # set up the Git hook
pre-commit run --all-files                            # run every hook on every file
pre-commit autoupdate                                 # update hooks to their latest tags
```

Run `pre-commit install` after cloning any project that uses it.[^pre-commit] [Ruff](./ruff.md) and [mypy](./mypy.md) both publish hooks.

## See also

- [Python developer tools](../concepts/python-tools.md)
- [Git and GitHub tools](../concepts/git-tools.md)

[^pre-commit]: [pre-commit documentation](https://pre-commit.com/) and [pre-commit/pre-commit](https://github.com/pre-commit/pre-commit)
[^uv-tools]: [uv: Using tools](https://docs.astral.sh/uv/guides/tools/)
[^packages]: Homebrew: [pre-commit](https://formulae.brew.sh/formula/pre-commit); PyPI: [pre-commit](https://pypi.org/project/pre-commit/); versions checked 2026-10-21
