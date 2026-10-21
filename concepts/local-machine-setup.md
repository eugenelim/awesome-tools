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
| [GitHub CLI (gh)](../tools/github-cli.md) | [Git and GitHub tool](./git-tools.md) | ✓ | ✓ | ✓ | MIT |
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
| [winget](../tools/winget.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | MIT |
| [WSL](../tools/wsl.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | MIT |
| [Forel](../tools/forel.md) | [macOS utility](./macos-utilities.md) | ✓ | | | GPL-3.0 |
| [Vorssaint](../tools/vorssaint.md) | [macOS utility](./macos-utilities.md) | ✓ (Apple silicon) | | | GPL-3.0-or-later |
| [Wick](../tools/wick.md) | [macOS utility](./macos-utilities.md) | ✓ | | | |

A blank cell means the captured sources don't state it.

## Homebrew

```sh
brew install --cask bitwarden
brew install --cask ghostty
brew install gh
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

Use winget first and Chocolatey only as a fallback; [Windows platform tools](./windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback) explains why. winget is built into Windows 10 1809+ and Windows 11.

```powershell
# WSL (Windows 10 2004+ or Windows 11), run as administrator, then restart
wsl --install
```

With winget (IDs checked 2026-10-19):

```powershell
winget install Git.Git                          # Git for Windows, includes Git Bash
winget install --id GitHub.cli --source winget   # GitHub CLI (gh)
winget install Docker.DockerCLI                 # client only; run Docker Engine in WSL 2
winget install Bitwarden.Bitwarden
winget install Anthropic.ClaudeCode
winget install OpenAI.Codex
winget install GitHub.Copilot
winget install Google.Antigravity
winget install ZedIndustries.Zed
winget install Obsidian.Obsidian
winget install Logseq.Logseq
winget install astral-sh.uv
winget install Schniz.fnm
winget install jdx.mise
winget install MilosParipovic.OneCommander      # Pro licence needed for commercial use
winget install MarekJasinski.FreeCommanderXE
winget install MathiasSvensson.MultiCommander
```

With Chocolatey, for tools winget lacks or only has as a preview. Install Chocolatey first (administrator PowerShell; see [Chocolatey](../tools/chocolatey.md)):

```powershell
choco install herdr
choco install hermes-desktop
```

Every tool above except Multi Commander also has a Chocolatey package; IDs are on each tool page. Watch for the name traps: `zed` (use `zed-editor`), `orca` and `nvm`.

These have no Chocolatey package: Octarine, Firefox Developer Edition, Orca (the `orca` package is Microsoft's MSI editor), VelaTerm, SilverBullet, OpenKnowledge, Protégé, VocBench and Pi. Install them from their websites. See [Windows platform tools](./windows-platform-tools.md) for the recommended shell setup.
