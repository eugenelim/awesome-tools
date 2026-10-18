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
| [Protégé](../tools/protege.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | BSD-2-Clause-Views |
| [VocBench](../tools/vocbench.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | Open source |
| [Rascal](../tools/rascal.md) | [File manager](./file-managers.md) | ✓ | | | MIT |
| [Swift Salamander](../tools/swift-salamander.md) | [File manager](./file-managers.md) | ✓ | | | |
| [Chocolatey](../tools/chocolatey.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | Apache-2.0 |
| [WSL](../tools/wsl.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | MIT |
| [Forel](../tools/forel.md) | [macOS utility](./macos-utilities.md) | ✓ | | | GPL-3.0 |
| [Wick](../tools/wick.md) | [macOS utility](./macos-utilities.md) | ✓ | | | |

A blank cell means the captured sources don't state it.

## Homebrew

```sh
brew install --cask bitwarden
brew install --cask ghostty
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
brew install node git && npm install -g @inkeep/open-knowledge
brew install openjdk@17   # Java 17+ for VocBench
```

VelaTerm, SilverBullet, Wick, VocBench and Rill have no Homebrew package. The Protégé and Muse casks are disabled. Install these from their websites.

## Windows

Run these in an administrator PowerShell. See [Chocolatey](../tools/chocolatey.md) and [WSL](../tools/wsl.md) for requirements.

```powershell
# WSL (Windows 10 2004+ or Windows 11), then restart
wsl --install

# Chocolatey
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
