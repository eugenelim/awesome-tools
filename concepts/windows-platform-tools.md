---
type: Category
title: Windows platform tools
description: Foundational tools, package manager recommendation (winget vs Chocolatey) and shell setup for a Windows development machine.
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
  - id: winget
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/
    title: Use WinGet to install and manage applications
  - id: choco-disclaimer
    resource: https://docs.chocolatey.org/en-us/community-repository/community-packages-disclaimer/
    title: Chocolatey community packages disclaimer
  - id: pkg-compare
    resource: https://github.com/microsoft/winget-pkgs
    title: winget-pkgs and Chocolatey community package versions, 2026-10-19
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
| [winget](../tools/winget.md) | Package manager (built in) | MIT | Included with App Installer on Windows 10 1809+ and 11 |
| [Chocolatey](../tools/chocolatey.md) | Package manager | Apache-2.0 | PowerShell one-liner (admin) |
| [WSL](../tools/wsl.md) | Linux distributions on Windows | MIT | `wsl --install` (admin) |

## Package managers: winget first, Chocolatey as fallback

Install with **winget** when a package exists, and use **Chocolatey** for tools winget lacks or only has in preview.

Why winget first:

- **Nothing to set up.** winget ships with Windows 10 1809+ and Windows 11 through App Installer.[^winget] Chocolatey has to be installed by running a remote PowerShell script after relaxing the execution policy.[^choco]
- **No admin shell needed.** winget asks for elevation only when an installer needs it.[^winget] The Chocolatey install command expects an administrative shell.[^choco]
- **Installers come from the vendor.** winget manifests point at the publisher's own download, for example `onecommander.com/OneCommanderSetup3.108.0.0.msi`.[^pkg-compare]
- **Chocolatey advises against company use of its community repository.** It says organisational use "is not recommended" and suggests a self-hosted Chocolatey server. Its packages are maintained by the community and "may not be supported by the original software vendor".[^choco-disclaimer]
- **More often current for the tools here.** Versions checked on 2026-10-19:[^pkg-compare]

| Tool | winget | Chocolatey |
| --- | --- | --- |
| Logseq | 2.0.2 | 0.10.15 |
| FreeCommander XE | 2026 build 941 | 2016 |
| Multi Commander | 16.5 build 3221 | not listed |
| Bitwarden | 2026.10.0 | 2026.9.1 |
| Claude Code | 2.1.302 | 2.1.292 |
| Codex | 0.161.0 | 0.163.0 |
| Git | 2.55.0.5 | 2.56.0.2 |
| herdr | preview builds only | 0.9.5 |
| Hermes Desktop | not listed | 0.22.2 |

When to use Chocolatey instead:

- **The tool isn't on winget, or only as a preview:** for example herdr and Hermes Desktop.
- **Chocolatey has a newer build that you need:** for example Codex and Git on 2026-10-19.

Compare with `winget show <id>` and `choco info <id>` first. Neither repository is run by the software vendors; the winget and Chocolatey Git packages, for example, aren't maintained by the Git for Windows project.[^git-win]

For company machines, check whether IT already manages one of them. Chocolatey's own guidance for organisations is a self-hosted internal repository.[^choco-disclaimer]

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

[^winget]: [Use WinGet to install and manage applications](https://learn.microsoft.com/en-us/windows/package-manager/winget/)
[^choco-disclaimer]: [Chocolatey community packages disclaimer](https://docs.chocolatey.org/en-us/community-repository/community-packages-disclaimer/)
[^pkg-compare]: Package manifests in [microsoft/winget-pkgs](https://github.com/microsoft/winget-pkgs) and the [Chocolatey community repository](https://community.chocolatey.org/packages), checked 2026-10-19
