---
type: Overview
title: Local machine setup
description: All tools in this bundle by category, platform, licence and Homebrew install command.
---
# Local machine setup

Every tool in this bundle, grouped by category. Details and sources are on each tool page.

| Tool | Category | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Bitwarden](../tools/bitwarden.md) | [Password manager](./password-managers.md) | ✓ | ✓ | ✓ | Open source |
| [Ghostty](../tools/ghostty.md) | [Terminal emulator](./terminal-emulators.md) | ✓ | | ✓ | |
| [VelaTerm](../tools/velaterm.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |
| [Orca](../tools/orca.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |
| [Zed](../tools/zed.md) | [Code editor](./code-editors.md) | ✓ | ✓ | ✓ | GPL-3.0-or-later |
| [Pi](../tools/pi.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | MIT |
| [Obsidian](../tools/obsidian.md) | [Knowledge management](./knowledge-management.md) | ✓ | | | Proprietary |
| [SilverBullet](../tools/silverbullet.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | MIT |
| [OpenKnowledge](../tools/openknowledge.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Swift Salamander](../tools/swift-salamander.md) | [File manager](./file-managers.md) | ✓ | | | Proprietary |
| [Wick](../tools/wick.md) | [macOS utility](./macos-utilities.md) | ✓ | | | |

A blank cell means the captured sources don't state it.

## Homebrew

```sh
brew install --cask bitwarden
brew install --cask ghostty
brew install --cask stablyai/orca/orca
brew install --cask zed
brew install pi-coding-agent
brew install --cask obsidian
brew install --cask c0desurfer/tap/swift-salamander
brew install node git && npm install -g @inkeep/open-knowledge
```

VelaTerm, SilverBullet and Wick have no Homebrew cask or formula. Install them from their websites.
