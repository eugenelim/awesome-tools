---
type: Tool
title: FreeCommander
description: Free dual-panel Windows file manager with archive handling, folder sync and a portable version.
resource: https://freecommander.com/
tags:
  - file-manager
  - windows
platforms:
  - Windows
license: Freeware
pricing: Free
sources:
  - id: freecommander
    resource: https://freecommander.com/en/summary/
    title: FreeCommander summary and downloads pages
  - id: winget
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MarekJasinski/FreeCommanderXE
    title: "winget: MarekJasinski.FreeCommanderXE"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/freecommander-xe
    title: "Chocolatey: freecommander-xe"
---
# FreeCommander

A free alternative to the standard Windows file manager.[^freecommander] winget lists it as freeware.[^winget] It can run portably: copy the install folder to a USB stick and use it on another computer.[^freecommander] The current edition is FreeCommander XE 2026.[^freecommander]

## Features

From the FreeCommander site:[^freecommander]

- Dual panels, arranged side by side or stacked (or a single panel), with tabs and an optional folder tree.
- Built-in viewer for hex, binary, text and images, including files inside archives.
- Reads and writes ZIP natively; RAR, 7z and others through plugins.
- Search (including inside archives), duplicate finder, MD5/SHA checksums, secure file wiping.
- Multi-rename tool, folder size calculation, folder comparison and synchronisation.
- Paths longer than 255 characters.
- Simple FTP/SFTP client (SFTP in the 64-bit build only), and access to phones and tablets.
- Configurable keyboard shortcuts, colour schemes, and multiple languages.

## Requirements

Windows, in 32-bit and 64-bit builds. The setup program doesn't work on Windows XP or Vista; use the portable version there.[^freecommander]

## Install

```powershell
winget install MarekJasinski.FreeCommanderXE
```

The winget package is at the current build (2026, build 941).[^winget] The Chocolatey packages are years out of date (`freecommander-xe` 2016.715 and `freecommander` 2009.2.2), so download from the site or use winget instead.[^choco-pkg]

## See also

- [File managers](../concepts/file-managers.md)
- [OneCommander](./onecommander.md)
- [Multi Commander](./multicommander.md)

[^freecommander]: [FreeCommander summary](https://freecommander.com/en/summary/) and [downloads](https://freecommander.com/en/downloads/)
[^winget]: [winget: MarekJasinski.FreeCommanderXE](https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MarekJasinski/FreeCommanderXE)
[^choco-pkg]: Chocolatey: [freecommander-xe](https://community.chocolatey.org/packages/freecommander-xe) and [freecommander](https://community.chocolatey.org/packages/freecommander)
