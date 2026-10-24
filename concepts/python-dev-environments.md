---
type: Guide
title: Python dev environments
description: "Managing Python versions and project environments: uv vs pyenv, with a recommendation and everyday uv commands."
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
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/astral-sh/uv
    title: "winget: astral-sh.uv"
  - id: choco
    resource: https://community.chocolatey.org/packages/uv
    title: "Chocolatey: uv"
  - id: uv-projects
    resource: https://docs.astral.sh/uv/guides/projects/
    title: "uv docs: Working on projects"
  - id: uv-deps
    resource: https://docs.astral.sh/uv/concepts/projects/dependencies/
    title: "uv docs: Managing dependencies"
  - id: uv-run
    resource: https://docs.astral.sh/uv/concepts/projects/run/
    title: "uv docs: Running commands in projects"
  - id: uv-sync
    resource: https://docs.astral.sh/uv/concepts/projects/sync/
    title: "uv docs: Locking and syncing"
  - id: uv-export
    resource: https://docs.astral.sh/uv/concepts/projects/export/
    title: "uv docs: Exporting a lockfile"
  - id: uv-tools
    resource: https://docs.astral.sh/uv/guides/tools/
    title: "uv docs: Using tools"
  - id: uv-scripts
    resource: https://docs.astral.sh/uv/guides/scripts/
    title: "uv docs: Running scripts"
  - id: uv-pip
    resource: https://docs.astral.sh/uv/pip/compile/
    title: "uv docs: Locking environments (uv pip)"
  - id: uv-cli
    resource: https://docs.astral.sh/uv/reference/cli/
    title: uv CLI reference
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
uv python update-shell          # add ~/.local/bin to PATH, for python3.12 and python3.13
uv python pin 3.12              # write .python-version for this project
uv python pin --global 3.13     # personal default
uv venv                         # create .venv (downloads Python if missing)
uv python upgrade               # move to latest patch releases
```

The uv commands are from its docs.[^uv] The Homebrew formula is `uv`.[^homebrew]

`uv python install` puts versioned executables such as `python3.13` in `~/.local/bin`. If that folder isn't on your `PATH`, `uv python update-shell` adds it; open a new terminal afterwards.[^uv]

### Which Python uv uses

uv downloads a missing Python the first time a command needs one, but only when it can't find a suitable Python already installed. It prefers Pythons it installed itself; after those, it uses a Python already on your system (Homebrew's, pyenv's or macOS's `/usr/bin/python3`) before downloading.[^uv]

- **Get the version you expect:** pin it, with `uv python pin` per project or `uv python pin --global` as your default. Install it first with `uv python install` so uv has its own copy.[^uv]
- **Never use system Pythons:** set `python-preference = "only-managed"` in `~/.config/uv/uv.toml`, or pass `--managed-python` (environment variable `UV_MANAGED_PYTHON`).[^uv] [^uv-cli]

### Keeping Python up to date

A pin such as `3.14` accepts any 3.14 release. uv uses the newest 3.14 it has installed, but doesn't download newer patch releases by itself.[^uv]

```sh
brew upgrade uv          # so uv knows about the newest Python releases
uv python upgrade 3.14   # latest 3.14 patch release
uv python upgrade        # or every Python uv installed
```

- **Virtual environments follow:** after an upgrade, uv prefers the new patch and keeps the old one. Virtual environments using that Python move to the new patch automatically, unless they were created with an exact patch, such as `uv venv -p 3.14.8`.[^uv]
- **No minor-version jumps:** uv never moves you from 3.14 to 3.15 on its own, because that can change dependency resolution. Change the pin to switch.[^uv]
- **uv-installed Pythons only:** upgrades don't apply to Homebrew's, pyenv's or other system Pythons.[^uv] On Windows, use `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`,[^uv] `winget install astral-sh.uv`[^winget-pkg] or `choco install uv`.[^choco]

## Everyday uv commands

Project commands work in a folder with a `pyproject.toml`. Prefer `uv add`, `uv run` and `uv sync` over installing packages into an activated environment.

### Projects

```sh
uv init my-project              # new project in a new folder
uv init                         # or in the current folder
uv run main.py                  # creates .venv and uv.lock on first run
```

| File | Purpose |
| --- | --- |
| `pyproject.toml` | Project metadata and declared dependencies |
| `.python-version` | The project's default Python version |
| `uv.lock` | Exact resolved versions for all platforms. Commit it; don't edit it by hand |
| `.venv/` | The project's virtual environment |

From the projects guide.[^uv-projects]

### Dependencies

```sh
uv add requests                 # add a dependency
uv add 'httpx>=0.20'            # with a version constraint
uv add git+https://github.com/encode/httpx  # from Git
uv add --dev pytest             # development dependency
uv add --group lint ruff        # another dependency group
uv add -r requirements.txt      # import from a requirements file
uv remove requests
uv tree                         # show the dependency tree
```

`uv add` and `uv remove` update `pyproject.toml`, `uv.lock` and the environment.[^uv-deps] [^uv-projects] `uv tree` is from the CLI reference.[^uv-cli]

### Running code

```sh
uv run app.py                   # run in the project environment
uv run pytest                   # run a tool installed in the project
uv run -- flask run -p 3000     # use -- before a command's own flags
uv run --with httpx==0.26.0 python -c "import httpx; print(httpx.__version__)"  # extra package for this run only
uv run --python 3.12 app.py     # pick a Python version
```

Before each run, `uv run` checks that the lockfile matches `pyproject.toml` and that the environment matches the lockfile.[^uv-run] [^uv-sync] For tools that need your project installed, such as pytest or mypy, use `uv run` rather than `uvx`.[^uv-tools]

### Lockfile and syncing

```sh
uv lock                         # create or update uv.lock
uv lock --check                 # fail if uv.lock is out of date
uv lock --upgrade               # upgrade every package
uv lock --upgrade-package requests  # upgrade one package
uv sync                         # make .venv match uv.lock exactly
uv sync --inexact               # keep packages that aren't in the lockfile
uv run --locked pytest          # fail instead of updating uv.lock (for CI)
uv run --frozen pytest          # use uv.lock without checking it
uv run --no-sync pytest         # don't check the environment
```

- **No automatic upgrades:** uv doesn't treat a lockfile as out of date when new package versions are released. Upgrade with `--upgrade` or `--upgrade-package`.[^uv-sync]
- **Exact syncing:** `uv sync` removes packages that aren't in the lockfile. `uv run` only adds missing ones, unless you pass `--exact`.[^uv-sync]
- **`--locked`:** errors if `uv.lock` is missing or needs updating. It works on `uv sync` and `uv run`, and `uv lock --check` is the equivalent for `uv lock`.[^uv-cli] [^uv-sync]

To hand the lockfile to tools that don't use uv:[^uv-export]

```sh
uv export --format requirements.txt --output-file requirements.txt
uv export --format pylock.toml --output-file pylock.toml
uv export --format cyclonedx1.5 --output-file sbom.json   # SBOM
```

### Command-line tools

```sh
uvx ruff check                  # run a tool in a temporary environment (same as uv tool run)
uvx ruff@0.3.0 check            # an exact version; ruff@latest for the newest
uv tool install ruff            # install and put it on PATH
uv tool list
uv tool upgrade ruff            # or: uv tool upgrade --all
uv tool uninstall ruff
uv tool update-shell            # add the tools folder to PATH
```

From the tools guide and CLI reference.[^uv-tools] [^uv-cli]

### Single-file scripts

```sh
uv add --script example.py 'requests<3' rich   # add inline (PEP 723) dependencies
uv run example.py                              # uv installs them before running
uv lock --script example.py                    # lock the script's dependencies
```

`uv add --script` writes a `# /// script` block at the top of the file:[^uv-scripts]

```python
# /// script
# dependencies = [
#   "requests<3",
#   "rich",
# ]
# ///
```

### pip-compatible commands

For projects managed with `requirements.txt` instead of `pyproject.toml` and `uv.lock`:[^uv-pip]

```sh
uv venv
uv pip compile requirements.in -o requirements.txt   # pin versions
uv pip sync requirements.txt                         # make the environment match exactly
uv pip install -r requirements.txt                   # install without removing anything
```

## Setup with pyenv (if needed)

```sh
brew install pyenv
# install Python build dependencies first
pyenv install 3.12
pyenv local 3.12
```

These commands are from the pyenv README.[^pyenv]

## See also

- [Python developer tools](./python-tools.md): Ruff, mypy, ty, pytest and pre-commit
- [Node.js dev environments](./node-dev-environments.md)
- [Go dev environments](./go-dev-environments.md)
- [Local machine setup](./local-machine-setup.md)

[^uv]: [uv README](https://github.com/astral-sh/uv), [Installing Python](https://docs.astral.sh/uv/guides/install-python/), [Python versions](https://docs.astral.sh/uv/concepts/python-versions/) and [Configuration files](https://docs.astral.sh/uv/concepts/configuration-files/)
[^pyenv]: [pyenv README](https://github.com/pyenv/pyenv)
[^homebrew]: Homebrew: [uv](https://formulae.brew.sh/formula/uv), [pyenv](https://formulae.brew.sh/formula/pyenv)

[^choco]: [Chocolatey: uv](https://community.chocolatey.org/packages/uv)

[^winget-pkg]: [winget: astral-sh.uv](https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/astral-sh/uv)

[^uv-projects]: [uv docs: Working on projects](https://docs.astral.sh/uv/guides/projects/)

[^uv-deps]: [uv docs: Managing dependencies](https://docs.astral.sh/uv/concepts/projects/dependencies/)

[^uv-run]: [uv docs: Running commands in projects](https://docs.astral.sh/uv/concepts/projects/run/)

[^uv-sync]: [uv docs: Locking and syncing](https://docs.astral.sh/uv/concepts/projects/sync/)

[^uv-export]: [uv docs: Exporting a lockfile](https://docs.astral.sh/uv/concepts/projects/export/)

[^uv-tools]: [uv docs: Using tools](https://docs.astral.sh/uv/guides/tools/)

[^uv-scripts]: [uv docs: Running scripts](https://docs.astral.sh/uv/guides/scripts/)

[^uv-pip]: [uv docs: Locking environments](https://docs.astral.sh/uv/pip/compile/)

[^uv-cli]: [uv CLI reference](https://docs.astral.sh/uv/reference/cli/)
