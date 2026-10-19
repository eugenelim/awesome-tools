---
type: Overview
title: Local machine setup
description: All tools in this bundle by category, platform and licence, with Homebrew and Windows install commands.
---
# Local machine setup

Every tool in this bundle, grouped by category. Details and sources are on each tool page.

| Tool | Category | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Bitwarden](../tools/bitwarden.md) | [Password manager](./password-managers.md) | ✓ | ✓ | ✓ | Open source |
| [Docker CLI](../tools/docker-cli.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Firefox Developer Edition](../tools/firefox-developer-edition.md) | [Web browser](./web-browsers.md) | ✓ | ✓ | ✓ | |
| [Rill](../tools/rill.md) | [Web browser](./web-browsers.md) | ✓ (Apple silicon) | | | |
| [SigmaOS](../tools/sigmaos.md) | [Web browser](./web-browsers.md) | ✓ | | | |
| [Ghostty](../tools/ghostty.md) | [Terminal emulator](./terminal-emulators.md) | ✓ | | ✓ | |
| [VelaTerm](../tools/velaterm.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |
| [Orca](../tools/orca.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |
| [herdr](../tools/herdr.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Zed](../tools/zed.md) | [Code editor](./code-editors.md) | ✓ | ✓ | ✓ | GPL-3.0-or-later |
| [Antigravity](../tools/antigravity.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | |
| [Claude Code](../tools/claude-code.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | |
| [Codex](../tools/codex.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [GitHub Copilot CLI](../tools/github-copilot.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | |
| [Hermes Agent](../tools/hermes.md) | [Personal AI agent](./personal-ai-agents.md) | ✓ | ✓ | ✓ | MIT |
| [Muse](../tools/muse.md) | [Personal AI agent](./personal-ai-agents.md) | ✓ | | | |
| [Pi](../tools/pi.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | MIT |
| [Obsidian](../tools/obsidian.md) | [Knowledge management](./knowledge-management.md) | ✓ | | | |
| [Logseq](../tools/logseq.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | AGPL-3.0 |
| [Octarine](../tools/octarine.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | |
| [SilverBullet](../tools/silverbullet.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | MIT |
| [OpenKnowledge](../tools/openknowledge.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Paper](../tools/paper.md) | [Design tool](./design-tools.md) | ✓ (Apple silicon) | | | |
| [openGym](../tools/opengym.md) | [Health and fitness](./health-and-fitness.md) | ✓ (Docker) | ✓ (Docker) | ✓ (Docker) | AGPL-3.0 |
| [Protégé](../tools/protege.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | BSD-2-Clause-Views |
| [VocBench](../tools/vocbench.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | Open source |
| [FreeCommander](../tools/freecommander.md) | [File manager](./file-managers.md) | | ✓ | | Freeware |
| [Multi Commander](../tools/multicommander.md) | [File manager](./file-managers.md) | | ✓ | | Freeware |
| [OneCommander](../tools/onecommander.md) | [File manager](./file-managers.md) | | ✓ | | Proprietary |
| [Rascal](../tools/rascal.md) | [File manager](./file-managers.md) | ✓ | | | MIT |
| [Swift Salamander](../tools/swift-salamander.md) | [File manager](./file-managers.md) | ✓ | | | |
| [Chocolatey](../tools/chocolatey.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | Apache-2.0 |
| [WSL](../tools/wsl.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | MIT |
| [Forel](../tools/forel.md) | [macOS utility](./macos-utilities.md) | ✓ | | | GPL-3.0 |
| [Vorssaint](../tools/vorssaint.md) | [macOS utility](./macos-utilities.md) | ✓ (Apple silicon) | | | GPL-3.0-or-later |
| [Wick](../tools/wick.md) | [macOS utility](./macos-utilities.md) | ✓ | | | |

A blank cell means the captured sources don't state it.

## Homebrew

```sh
brew install --cask bitwarden
brew install --cask ghostty
brew install docker docker-compose docker-buildx colima   # Docker CLI without Docker Desktop
brew install --cask firefox@developer-edition
brew install --cask sigmaos
brew install --cask stablyai/orca/orca
brew install herdr
brew install --cask zed
brew install pi-coding-agent
brew install hermes-agent
brew install --cask hermes-desktop
brew install --cask claude-code
brew install --cask codex
brew install copilot-cli        # not `copilot`, which is AWS's ECS tool
brew install --cask antigravity
brew install --cask obsidian
brew install --cask octarine
brew install --cask logseq
brew install --cask paper-design
brew install --cask c0desurfer/tap/swift-salamander
brew install --cask chang-07/tap/rascal
brew install --cask lab421/tap/forel
brew install --cask vorssaint
brew install node git && npm install -g @inkeep/open-knowledge
brew install openjdk@17   # Java 17+ for VocBench
```

VelaTerm, SilverBullet, Wick, VocBench, Rill and openGym (Docker) have no Homebrew package. The Protégé and Muse casks are disabled. Install these from their websites.

## Windows

Run these in an administrator PowerShell. See [Chocolatey](../tools/chocolatey.md) and [WSL](../tools/wsl.md) for requirements.

```powershell
# WSL (Windows 10 2004+ or Windows 11), then restart
wsl --install

# Chocolatey
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Then, with Chocolatey (package pages are linked from each tool page):

```powershell
choco install git                 # Git for Windows, includes Git Bash
choco install docker-cli          # client only; run Docker Engine in WSL 2
choco install bitwarden
choco install claude-code
choco install codex
choco install github-copilot-cli
choco install antigravity
choco install herdr
choco install hermes-desktop
choco install zed-editor          # not `zed`, which is an unrelated tool
choco install obsidian
choco install logseq              # lags the GitHub release
choco install uv
choco install fnm
choco install onecommander        # Pro licence needed for commercial use
```

With winget (for tools whose Chocolatey packages are missing or outdated):

```powershell
winget install MarekJasinski.FreeCommanderXE
winget install MathiasSvensson.MultiCommander
```

These have no Chocolatey package: Octarine, Firefox Developer Edition, Orca (the `orca` package is Microsoft's MSI editor), VelaTerm, SilverBullet, OpenKnowledge, Protégé, VocBench and Pi. Install them from their websites. See [Windows platform tools](./windows-platform-tools.md) for the recommended shell setup.
