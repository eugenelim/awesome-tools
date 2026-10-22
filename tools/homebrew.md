---
type: Tool
title: Homebrew
description: The package manager for macOS and Linux, installing command-line tools (formulae) and apps (casks).
resource: https://brew.sh/
tags:
  - macos
  - linux
  - package-manager
  - cli
  - open-source
platforms:
  - macOS 15+
  - Linux
  - WSL
license: BSD-2-Clause
pricing: Free
sources:
  - id: brew
    resource: https://brew.sh/
    title: Homebrew homepage
  - id: installation
    resource: https://docs.brew.sh/Installation
    title: Homebrew installation docs
  - id: manpage
    resource: https://docs.brew.sh/Manpage
    title: Homebrew manpage (brew commands)
  - id: repo
    resource: https://github.com/Homebrew/brew
    title: Homebrew/brew repository
---
# Homebrew

The package manager for macOS, Linux and WSL. **Formulae** are command-line tools, libraries and services; **casks** are prebuilt apps, fonts and plugins.[^brew] Homebrew itself is licensed under BSD-2-Clause.[^repo] Every Homebrew command in this bundle assumes it's installed.

Each package goes into its own folder in the **Cellar**, and its files are symlinked into the Homebrew prefix. Homebrew doesn't install files outside its prefix, though cask apps go into `/Applications`.[^brew]

| Platform | Prefix |
| --- | --- |
| macOS, Apple silicon | `/opt/homebrew` |
| macOS, Intel | `/usr/local` |
| Linux and WSL | `/home/linuxbrew/.linuxbrew` |

## Requirements

- macOS 15 (Sequoia) or later on supported hardware. Apple silicon is fully supported; Intel Macs are Tier 3.[^installation] [^brew]
- The Command Line Tools for Xcode, only to build formulae from source. Bottles and casks on Apple silicon install without them.[^installation]
- `bash` to run the installer.[^installation]

## Set up

1. Run the installer in Terminal, a Linux shell or WSL. It explains each step and waits before changing anything:[^brew]

   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   On Apple silicon there's also a `.pkg` installer on the Homebrew/brew releases page.[^installation]

2. Add Homebrew to your shell. Without this step Homebrew won't work. Use your prefix from the table above, and `~/.bashrc` instead of `~/.zshrc` for bash:[^installation]

   ```sh
   echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc
   eval "$(/opt/homebrew/bin/brew shellenv)"
   ```

3. Check the install, and optionally turn off analytics:[^manpage]

   ```sh
   brew doctor
   brew analytics off
   ```

After installation you don't need `sudo` for formulae, but some casks and system services still ask for it.[^installation] On 2026-10-21 the latest release was 7.0.10 (2026-10-19).[^repo]

## Common commands

| Command | What it does |
| --- | --- |
| `brew search <text>` | Search formula and cask names; `/text/` is a regular expression |
| `brew info <name>` | Show a package's version, dependencies and caveats |
| `brew install <formula>` | Install a command-line tool |
| `brew install --cask <cask>` | Install an app |
| `brew uninstall <name>` | Remove a package |
| `brew list` | List installed packages |
| `brew leaves` | List formulae that nothing else depends on, the ones you asked for |
| `brew update` | Fetch the newest Homebrew and package definitions |
| `brew outdated` | List packages with a newer version |
| `brew upgrade` | Upgrade all outdated, unpinned packages; name packages to upgrade only those |
| `brew upgrade --greedy` | Also upgrade casks that update themselves or use `version :latest` |
| `brew pin <formula>` / `brew unpin <formula>` | Hold a package at its current version |
| `brew autoremove` | Remove dependencies that are no longer needed |
| `brew cleanup` | Remove old versions and downloads more than 120 days old |
| `brew doctor` | Check for problems |
| `brew uses --installed <formula>` | Show installed packages that depend on a formula |
| `brew tap <user>/<repo>` | Add a third-party repository of formulae and casks |

All commands are from the Homebrew manpage.[^manpage] A routine update is:

```sh
brew update && brew upgrade && brew cleanup
```

### Services

`brew services` runs a formula as a background service, using `launchctl` on macOS and `systemctl` on Linux. Without `sudo`, services start at login; with `sudo`, at boot.[^manpage]

```sh
brew services list
brew services start postgresql@18
brew services restart postgresql@18
brew services stop postgresql@18
```

### Brewfile

`brew bundle` records and restores a whole setup from a `Brewfile`. It covers formulae, casks, taps, Mac App Store apps, VS Code extensions and more, including WinGet packages on WSL.[^manpage] [^brew]

```sh
brew bundle dump        # write a Brewfile of what's installed
brew bundle             # install and upgrade everything in ./Brewfile
brew bundle check       # exit successfully if everything is installed
brew bundle cleanup     # uninstall what's not in the Brewfile
```

`brew bundle cleanup` asks before removing anything, unless you pass `--force`.[^manpage] Keep the Brewfile in version control to set up a new Mac in one command.

## See also

- [Package managers](../concepts/package-managers.md)
- [Local machine setup](../concepts/local-machine-setup.md#homebrew)
- [winget](./winget.md), the Windows equivalent

[^brew]: [Homebrew homepage](https://brew.sh/)
[^installation]: [Homebrew installation docs](https://docs.brew.sh/Installation)
[^manpage]: [Homebrew manpage](https://docs.brew.sh/Manpage)
[^repo]: [Homebrew/brew repository](https://github.com/Homebrew/brew) (licence) and [releases](https://github.com/Homebrew/brew/releases); checked 2026-10-21
