---
type: Tool
title: GitHub CLI (gh)
description: GitHub's official command-line tool for working with repositories, pull requests, issues and more from the terminal.
resource: https://cli.github.com/
tags:
  - git
  - github
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: gh-repo
    resource: https://github.com/cli/cli
    title: cli/cli README
  - id: gh-macos
    resource: https://github.com/cli/cli/blob/trunk/docs/install_macos.md
    title: Installing gh on macOS
  - id: gh-windows
    resource: https://github.com/cli/cli/blob/trunk/docs/install_windows.md
    title: Installing gh on Windows
  - id: gh-linux
    resource: https://github.com/cli/cli/blob/trunk/docs/install_linux.md
    title: Installing gh on Linux and BSD
  - id: gh-auth
    resource: https://cli.github.com/manual/gh_auth_login
    title: gh auth login manual
---
# GitHub CLI (gh)

GitHub's official command-line tool, `gh`, licensed under MIT.[^gh-repo] It's separate from Git: Git manages your repository, while `gh` talks to GitHub itself. On Windows, install [Git for Windows](../concepts/windows-platform-tools.md#1-always-git-for-windows-includes-git-bash) as well.

## Install

| Platform | Official method | Command |
| --- | --- | --- |
| macOS | Homebrew | `brew install gh` |
| Windows | winget | `winget install --id GitHub.cli --source winget` |
| Debian, Ubuntu, Raspberry Pi | GitHub's apt repository | see below |
| Fedora, RHEL, CentOS, Amazon Linux, openSUSE | GitHub's rpm repository | see below |

The GitHub CLI maintainers support the Homebrew formula,[^gh-macos] and Microsoft supports the winget package.[^gh-windows] Every platform also has precompiled binaries on the [releases page](https://github.com/cli/cli/releases/latest).[^gh-repo] On macOS, the `.pkg` installers are currently unsigned.[^gh-macos]

**Windows:** the installer changes `PATH`. In Windows Terminal, open a **new window** afterwards; a new tab isn't enough.[^gh-windows] `choco install gh` also works, but the GitHub CLI team lists Chocolatey as community-maintained and doesn't support it.[^gh-windows] That matches this bundle's [winget-first recommendation](../concepts/windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback).

**Debian, Ubuntu, Raspberry Pi**, from GitHub's install docs:[^gh-linux]

```bash
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

**Fedora and other dnf5-based systems:**[^gh-linux]

```bash
sudo dnf install dnf5-plugins
sudo dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
```

GitHub signs its Linux packages; the install docs list the key fingerprints to check.[^gh-linux]

## Sign in

```sh
gh auth login                          # interactive setup
gh auth login --hostname <your-host>   # GitHub Enterprise Server
```

By default, `gh auth login` signs in through your web browser and stores the token in your system's credential store.[^gh-auth]

## Upgrade

`brew upgrade gh` on macOS,[^gh-macos] or `winget upgrade --id GitHub.cli --source winget` on Windows.[^gh-windows]

## See also

- [Git and GitHub tools](../concepts/git-tools.md)
- [GitHub Copilot CLI](./github-copilot.md)

[^gh-repo]: [cli/cli README](https://github.com/cli/cli)
[^gh-macos]: [Installing gh on macOS](https://github.com/cli/cli/blob/trunk/docs/install_macos.md)
[^gh-windows]: [Installing gh on Windows](https://github.com/cli/cli/blob/trunk/docs/install_windows.md)
[^gh-linux]: [Installing gh on Linux and BSD](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)
[^gh-auth]: [gh auth login manual](https://cli.github.com/manual/gh_auth_login)
