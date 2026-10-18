---
type: Guide
title: Python dev environments
description: "Managing Python versions and project environments: uv vs pyenv, with a recommendation."
tags:
  - python
  - version-manager
  - guide
sources:
  - id: uv
    resource: https://docs.astral.sh/uv/guides/install-python/
    title: uv README and Python version docs
  - id: pyenv
    resource: https://github.com/pyenv/pyenv
    title: pyenv README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/uv
    title: "Homebrew: uv, pyenv"
---
# Python dev environments

## Recommendation: use uv

Use **uv** to install and switch Python versions. Reach for pyenv only when you need something uv can't do (see [when pyenv still fits](#when-pyenv-still-fits)).

Why:

- **No compiling.** uv installs prebuilt Python builds from the python-build-standalone project.[^uv] pyenv builds most versions from source, so you need build dependencies installed first.[^pyenv]
- **Native Windows support.** uv supports macOS, Linux and Windows.[^uv] pyenv doesn't support Windows and only works inside [WSL](../tools/wsl.md); even there, the Pythons it installs aren't native Windows builds. For Windows, it points you to the separate `pyenv-win` fork.[^pyenv]
- **One tool instead of several.** uv replaces pip, pip-tools, pipx, poetry, pyenv, twine and virtualenv.[^uv] pyenv only switches versions and doesn't manage virtual environments; that takes a separate plugin such as pyenv-virtualenv.[^pyenv]
- **Works with existing pyenv projects.** Both tools read `.python-version` files. `uv python pin` writes one, just as `pyenv local` does.[^uv] [^pyenv]
- **Downloads Python for you.** uv fetches a missing Python version the first time a command needs it, and it also respects `requires-python` in `pyproject.toml`.[^uv]

## Comparison

| | uv | pyenv |
| --- | --- | --- |
| Scope | Packages, projects, lockfile, tools, Python versions | Python versions only |
| How Python is installed | Prebuilt python-build-standalone binaries | Mostly compiled from source |
| Distributions | CPython, PyPy | CPython, PyPy, Stackless, Jython and more |
| Windows | Native | Not supported (use WSL or pyenv-win) |
| Version file | `.python-version` (`uv python pin`) | `.python-version` (`pyenv local`) |
| Global default | `uv python pin --global` | `pyenv global` |
| How it switches | Each command selects the interpreter; versioned executables are added to PATH | Shim directory on PATH |
| Licence | Apache-2.0 | MIT |

Sources: uv[^uv], pyenv[^pyenv].

## When pyenv still fits

- You need a distribution uv doesn't provide, such as Stackless or Jython.[^pyenv] [^uv]
- You need a custom build with your own `configure` options or compiler flags.[^pyenv]
- You want bare `python` and `python3` commands that follow the current directory, without running everything through uv. uv only installs versioned executables like `python3.12` unless you pass the experimental `--default` flag.[^uv]

## Setup with uv

```sh
brew install uv                 # or: curl -LsSf https://astral.sh/uv/install.sh | sh
uv python install 3.12 3.13     # install versions
uv python pin 3.12              # write .python-version for this project
uv python pin --global 3.13     # personal default
uv venv                         # create .venv (downloads Python if missing)
uv python upgrade               # move to latest patch releases
```

The uv commands are from its docs.[^uv] The Homebrew formula is `uv`.[^homebrew] On Windows, use `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`.[^uv]

## Setup with pyenv (if needed)

```sh
brew install pyenv
# install Python build dependencies first
pyenv install 3.12
pyenv local 3.12
```

These commands are from the pyenv README.[^pyenv]

## See also

- [Node.js dev environments](./node-dev-environments.md)
- [Local machine setup](./local-machine-setup.md)

[^uv]: [uv README](https://github.com/astral-sh/uv), [Installing Python](https://docs.astral.sh/uv/guides/install-python/) and [Python versions](https://docs.astral.sh/uv/concepts/python-versions/)
[^pyenv]: [pyenv README](https://github.com/pyenv/pyenv)
[^homebrew]: Homebrew: [uv](https://formulae.brew.sh/formula/uv), [pyenv](https://formulae.brew.sh/formula/pyenv)
