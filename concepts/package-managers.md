---
type: Category
title: Package managers
description: Command-line tools that install, upgrade and remove the other tools in this bundle.
---
# Package managers

Command-line tools that install, upgrade and remove the other tools in this bundle. Set one up first; the install commands on every tool page assume it.

| Tool | Licence | Platforms | Set up |
| --- | --- | --- | --- |
| [Homebrew](../tools/homebrew.md) | BSD-2-Clause | macOS 15+, Linux, WSL | [install script, then `brew shellenv`](../tools/homebrew.md#set-up) |
| [winget](../tools/winget.md) | MIT | Windows 10 1809+, Windows 11, Windows Server 2025 | [built in via App Installer](../tools/winget.md#set-up) |
| [Chocolatey](../tools/chocolatey.md) | Apache-2.0 (open source edition) | Windows | [install script in an administrator PowerShell](../tools/chocolatey.md#install) |

On Windows, use winget first and Chocolatey only for packages winget lacks; see [Windows platform tools](./windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback).

## Everyday commands side by side

| Task | Homebrew | winget |
| --- | --- | --- |
| Search | `brew search <name>` | `winget search <name>` |
| Details | `brew info <name>` | `winget show --id <id>` |
| Install | `brew install <formula>` or `brew install --cask <app>` | `winget install --id <id> -e` |
| List installed | `brew list` | `winget list` |
| See what's outdated | `brew outdated` | `winget upgrade` |
| Upgrade everything | `brew update && brew upgrade` | `winget upgrade --all` |
| Hold a version | `brew pin <formula>` | `winget pin add --id <id>` |
| Remove | `brew uninstall <name>` | `winget uninstall --id <id>` |
| Save and restore a setup | `brew bundle dump`, then `brew bundle` | `winget export -o apps.json`, then `winget import -i apps.json` |

Sources are on the [Homebrew](../tools/homebrew.md#common-commands) and [winget](../tools/winget.md#common-commands) pages.
