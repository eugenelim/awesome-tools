---
type: Category
title: Windows platform tools
description: Foundational tools and the recommended shell setup for a Windows development machine.
sources:
  - id: cc-win
    resource: https://code.claude.com/docs/en/setup
    title: Claude Code setup (Windows)
  - id: git-win
    resource: https://git-scm.com/install/windows
    title: Git for Windows install page
  - id: wsl
    resource: https://learn.microsoft.com/en-us/windows/wsl/install
    title: Install WSL
  - id: choco
    resource: https://chocolatey.org/install
    title: Chocolatey install page
  - id: uv
    resource: https://github.com/astral-sh/uv
    title: uv README
  - id: pyenv
    resource: https://github.com/pyenv/pyenv
    title: pyenv README
  - id: node-vm
    resource: https://github.com/Schniz/fnm
    title: nvm and fnm READMEs
  - id: copilot
    resource: https://github.com/github/copilot-cli
    title: github/copilot-cli README
---
# Windows platform tools

Foundational tools for setting up a Windows development machine. This is the Windows counterpart to Homebrew and [macOS utilities](./macos-utilities.md).

| Tool | Purpose | Licence | Install |
| --- | --- | --- | --- |
| [Chocolatey](../tools/chocolatey.md) | Package manager | Apache-2.0 | PowerShell one-liner (admin) |
| [WSL](../tools/wsl.md) | Linux distributions on Windows | MIT | `wsl --install` (admin) |

## Recommended shell setup

Install **Git for Windows** on every machine. Use **PowerShell** for everyday work, and add **WSL 2** when a project needs Linux tooling or sandboxing.

### 1. Always: Git for Windows (includes Git Bash)

Git for Windows gives you Git and Git Bash.[^cc-win]

- [Claude Code](../tools/claude-code.md) recommends it on native Windows. With Git Bash installed, Claude Code runs commands in Bash; without it, it falls back to PowerShell.[^cc-win]
- Git Bash runs POSIX scripts that Windows doesn't run natively. Claude Code's release-signature checks, for example, need Git Bash or WSL.[^cc-win]
- [nvm](./node-dev-environments.md) runs under Git Bash as well as WSL.[^node-vm]

Install it with the official installer from git-scm.com, or with one of:[^git-win]

```powershell
winget install --id Git.Git -e --source winget
choco install git
```

The winget and Chocolatey packages aren't maintained by the Git for Windows project, so they can lag behind the official release.[^git-win]

### 2. Everyday: PowerShell, for Windows-native projects

Most tools in this bundle have native Windows installers that run from PowerShell:

- [Chocolatey](../tools/chocolatey.md)[^choco]
- [uv](./python-dev-environments.md)[^uv]
- [fnm](./node-dev-environments.md)[^node-vm]
- `wsl --install`[^wsl]
- [Claude Code](../tools/claude-code.md)[^cc-win]

[GitHub Copilot CLI](../tools/github-copilot.md) needs PowerShell v6 or later.[^copilot] Use this setup when the project and its tools are Windows-native; Claude Code's docs give the same guidance for native Windows.[^cc-win]

### 3. When the work is Linux-shaped: WSL 2

Use [WSL 2](../tools/wsl.md) when you need:

- **Linux toolchains**: distro packages, Linux services, or tools that don't run natively on Windows. For example, [pyenv](./python-dev-environments.md) only works inside WSL on Windows.[^pyenv] [^wsl]
- **Sandboxed agents**: Claude Code supports sandboxing on WSL 2, but not on native Windows or WSL 1.[^cc-win]

Install and run tools *inside* the WSL terminal. Claude Code, for example, is installed and launched from WSL, not from PowerShell, and doesn't need Git for Windows there.[^cc-win]

| Scenario | Shell | Examples |
| --- | --- | --- |
| Git, POSIX scripts, Claude Code's Bash tool | Git Bash (from Git for Windows) | `git`, `bash script.sh` |
| Windows-native projects and installers | PowerShell | Chocolatey, uv, fnm, Copilot CLI |
| Linux toolchains, sandboxed agents | WSL 2 | pyenv, Claude Code with sandboxing |

[^cc-win]: [Claude Code setup docs](https://code.claude.com/docs/en/setup)
[^git-win]: [Git for Windows install page](https://git-scm.com/install/windows)
[^wsl]: [Install WSL](https://learn.microsoft.com/en-us/windows/wsl/install)
[^choco]: [Chocolatey install page](https://chocolatey.org/install)
[^uv]: [uv README](https://github.com/astral-sh/uv)
[^pyenv]: [pyenv README](https://github.com/pyenv/pyenv)
[^node-vm]: [nvm README](https://github.com/nvm-sh/nvm) and [fnm README](https://github.com/Schniz/fnm)
[^copilot]: [github/copilot-cli README](https://github.com/github/copilot-cli)
