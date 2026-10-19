---
type: Tool
title: OneCommander
description: Modern dual-pane Windows Explorer alternative with Miller columns, tabs and built-in preview.
resource: https://onecommander.com/
tags:
  - file-manager
  - windows
platforms:
  - Windows
license: Proprietary
pricing: Free for home use; Pro $30 lifetime (required for commercial use)
sources:
  - id: onecommander
    resource: https://onecommander.com/
    title: OneCommander homepage
  - id: winget
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MilosParipovic/OneCommander
    title: "winget: MilosParipovic.OneCommander"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/onecommander
    title: "Chocolatey: onecommander"
---
# OneCommander

A dual-pane replacement for Windows File Explorer, with Miller columns (macOS Finder-style column view) and tabs. It's free for home use with no ads or tracking; commercial use needs a Pro licence.[^onecommander]

## Features

From the OneCommander site:[^onecommander]

- Dual panes and tabs that persist between sessions.
- Miller-column navigation and adjustable file-detail columns.
- Built-in preview with the spacebar, with QuickLook and Seer support.
- DirectX-accelerated rendering and caching of thumbnails, icons and folder sizes.
- Paths longer than Windows' 260-character limit.
- RegEx batch renaming and batch image conversion.
- Per-folder to-do lists and notes.
- Themes in editable XAML, and a scripts menu that runs PowerShell, Batch, Python and other scripts on selected files.
- Doesn't collect or transmit personal data.

## Pricing

Free for home use. Professional or commercial use needs a Pro licence: $30, lifetime, with extra features and future updates.[^onecommander]

## Requirements

Windows 10 or 11, 64-bit (x64). A high-PPI screen is recommended. The v4 beta needs the .NET 10 runtime.[^onecommander]

## Install

```powershell
winget install MilosParipovic.OneCommander
choco install onecommander
```

Both packages are at version 3.108.0, matching the site's MSI installer.[^winget] [^choco-pkg] [^onecommander]

## See also

- [File managers](../concepts/file-managers.md)
- [FreeCommander](./freecommander.md)
- [Multi Commander](./multicommander.md)

[^onecommander]: [OneCommander homepage](https://onecommander.com/)
[^winget]: [winget: MilosParipovic.OneCommander](https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MilosParipovic/OneCommander)
[^choco-pkg]: [Chocolatey: onecommander](https://community.chocolatey.org/packages/onecommander)
