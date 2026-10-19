---
type: Tool
title: Multi Commander
description: Free, tabbed dual-panel Windows file manager with scripting, plug-ins and archive, FTP and registry browsing.
resource: https://multicommander.com/
tags:
  - file-manager
  - windows
platforms:
  - Windows
license: Freeware
pricing: Free (donations welcome)
sources:
  - id: multicommander
    resource: https://multicommander.com/
    title: Multi Commander homepage and downloads
  - id: winget
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MathiasSvensson/MultiCommander
    title: "winget: MathiasSvensson.MultiCommander"
---
# Multi Commander

A tabbed, dual-panel replacement for Windows Explorer. It's free to download and use, and accepts donations.[^multicommander] winget lists it as freeware.[^winget]

## Features

From the Multi Commander site:[^multicommander]

- Dual panes with tabs, caching for folders with thousands of files, and detail, list and thumbnail views.
- Long tasks run in the background while you keep working.
- Browses inside archives (Zip, 7-Zip, Rar, Tar, gz, bz2), with auto-unpack and auto-sort plug-ins for copies and moves.
- Rule-based multi-rename with undo, and a viewer for files of any size.
- Views and changes file permissions, and can take ownership of files.
- Edits the Windows Registry, treats FTP (with SSL/TLS) as a file system, and browses network shares.
- A script engine, plus extensions and plug-ins with an open SDK.
- Picture tools (EXIF) and audio tools (MP3 tags).

## Requirements

Windows 7 through 11 and Windows Server 2008 R2 / 2012 R2; the site lists XP to 11. The current installer (16.5, build 3221) is 64-bit, and the site says the normal version no longer runs on XP.[^multicommander]

## Install

```powershell
winget install MathiasSvensson.MultiCommander
```

The winget package is at the current version (16.5, build 3221).[^winget] There's no Chocolatey package. The site also offers a portable version, which it says to download only from multicommander.com.[^multicommander]

A Microsoft Store edition, Multi Commander SE, can't delete or overwrite files in `C:\Windows`.[^multicommander]

## See also

- [File managers](../concepts/file-managers.md)
- [OneCommander](./onecommander.md)
- [FreeCommander](./freecommander.md)

[^multicommander]: [Multi Commander homepage](https://multicommander.com/), [about](https://multicommander.com/about) and [downloads](https://multicommander.com/downloads)
[^winget]: [winget: MathiasSvensson.MultiCommander](https://github.com/microsoft/winget-pkgs/tree/master/manifests/m/MathiasSvensson/MultiCommander)
