---
type: Tool
title: winget (Windows Package Manager)
description: Microsoft's command-line package manager, built into Windows 10 1809+ and Windows 11 via App Installer.
resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/
tags:
  - windows
  - package-manager
  - open-source
platforms:
  - Windows 10 1809+
  - Windows 11
  - Windows Server 2025
license: MIT
pricing: Free
sources:
  - id: winget
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/
    title: Use WinGet to install and manage applications
  - id: cli-repo
    resource: https://github.com/microsoft/winget-cli
    title: microsoft/winget-cli
---
# winget (Windows Package Manager)

Microsoft's command-line tool for finding, installing, upgrading, removing and configuring apps on Windows 10, Windows 11 and Windows Server 2025. It is the client for the Windows Package Manager service.[^winget] The client is open source under the MIT licence.[^cli-repo]

## Availability

winget ships with **App Installer**, a system component updated through the Microsoft Store, on Windows 11 and recent Windows 10. It requires Windows 10 version 1809 (build 17763) or later. If App Installer is missing, install it from the Microsoft Store.[^winget]

## Usage

```powershell
winget search <name>
winget install <id>
winget upgrade --all
winget export -o apps.json   # save installed apps to a file
winget import -i apps.json   # reinstall them on another machine
```

These commands come from Microsoft's docs. Other commands include `list`, `uninstall`, `pin` and `configure`.[^winget]

You don't need to run winget as administrator. Installers that need elevation show a normal Windows prompt. In an administrator terminal there's no prompt, so only install apps you trust.[^winget]

Packages come from the community repository at `microsoft/winget-pkgs`, and anyone can submit one.[^winget]

## See also

- [Windows platform tools](../concepts/windows-platform-tools.md), including the [winget vs Chocolatey recommendation](../concepts/windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback)
- [Chocolatey](./chocolatey.md)

[^winget]: [Use WinGet to install and manage applications](https://learn.microsoft.com/en-us/windows/package-manager/winget/)
[^cli-repo]: Source repository: [microsoft/winget-cli](https://github.com/microsoft/winget-cli)
