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
  - id: install
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/install
    title: winget install command
  - id: upgrade
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/upgrade
    title: winget upgrade command
  - id: pinning
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/pinning
    title: winget pin command
  - id: configure
    resource: https://learn.microsoft.com/en-us/windows/package-manager/winget/configure
    title: winget configure command
  - id: cli-repo
    resource: https://github.com/microsoft/winget-cli
    title: microsoft/winget-cli
---
# winget (Windows Package Manager)

Microsoft's command-line tool for finding, installing, upgrading, removing and configuring apps on Windows 10, Windows 11 and Windows Server 2025. It is the client for the Windows Package Manager service.[^winget] The client is open source under the MIT licence.[^cli-repo] Every winget command in this bundle assumes it's available.

Packages come from the community repository at `microsoft/winget-pkgs`, where anyone can submit one, and from the Microsoft Store (`msstore`).[^winget] [^install]

## Set up

winget ships with **App Installer**, a system component updated through the Microsoft Store on desktop Windows and through Windows Update on Windows Server 2025. It needs Windows 10 version 1809 (build 17763) or later.[^winget]

1. Check it's there:[^winget]

   ```powershell
   winget --version
   winget --info      # version, licence links and group policies
   ```

2. If `winget` isn't found right after your first sign-in, Windows may still be registering it. Ask for it in PowerShell:[^winget]

   ```powershell
   Add-AppxPackage -RegisterByFamilyName -MainPackage Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
   ```

3. If App Installer is missing, install it from the Microsoft Store. Windows Sandbox has neither the Store nor winget; there, install the `Microsoft.WinGet.Client` PowerShell module and run `Repair-WinGetPackageManager -AllUsers`.[^winget]

4. Sources have their own terms of use, which winget asks you to accept. Scripts can accept them up front with `--accept-source-agreements`.[^install]

You don't need to run winget as administrator. Installers that need elevation show a normal Windows prompt. In an administrator terminal there's no prompt, so only install apps you trust.[^winget] Settings live in a `settings.json` file that `winget settings` opens.[^winget]

## Common commands

| Command | What it does |
| --- | --- |
| `winget search <name>` | Search for a package |
| `winget show --id <id>` | Show a package's details and the installer winget would use |
| `winget install --id <id> -e` | Install exactly that package ID |
| `winget install <id> <id> ...` | Install several packages in sequence |
| `winget install --id <id> --version <v>` | Install a specific version |
| `winget list` | List installed packages |
| `winget upgrade` | List packages with an upgrade available |
| `winget upgrade --id <id>` | Upgrade one package |
| `winget upgrade --all` | Upgrade everything with an upgrade available |
| `winget uninstall --id <id>` | Remove a package |
| `winget pin add --id <id>` / `winget pin remove --id <id>` | Hold a package at its version, or release it |
| `winget export -o apps.json` | Save installed packages to a file |
| `winget import -i apps.json` | Install every package in that file on another machine |
| `winget configure -f <file>` | Apply a configuration file that sets up the machine |
| `winget source update` | Refresh package sources |

The commands and options are from Microsoft's docs.[^winget] [^install] [^upgrade] [^pinning] [^configure]

By default the query is a case-insensitive substring match on name, ID and moniker, so `winget install git` may match several packages. `--id <id> -e` matches one ID exactly, and `--source winget` picks the community repository when a package is in more than one source.[^install] For an unattended install, add `--silent --accept-package-agreements --accept-source-agreements`.[^install]

Run `winget upgrade` on its own first to preview what `--all` will change. Packages that don't report a version are skipped unless you add `--include-unknown`, and pinned ones unless you add `--include-pinned`.[^upgrade] Only run `winget configure` on a file you trust.[^configure]

## See also

- [Package managers](../concepts/package-managers.md)
- [Windows platform tools](../concepts/windows-platform-tools.md), including the [winget vs Chocolatey recommendation](../concepts/windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback)
- [Local machine setup](../concepts/local-machine-setup.md#windows)
- [Chocolatey](./chocolatey.md)
- [Homebrew](./homebrew.md), the macOS and Linux equivalent

[^winget]: [Use WinGet to install and manage applications](https://learn.microsoft.com/en-us/windows/package-manager/winget/)
[^install]: [winget install command](https://learn.microsoft.com/en-us/windows/package-manager/winget/install)
[^upgrade]: [winget upgrade command](https://learn.microsoft.com/en-us/windows/package-manager/winget/upgrade)
[^pinning]: [winget pin command](https://learn.microsoft.com/en-us/windows/package-manager/winget/pinning)
[^configure]: [winget configure command](https://learn.microsoft.com/en-us/windows/package-manager/winget/configure)
[^cli-repo]: Source repository: [microsoft/winget-cli](https://github.com/microsoft/winget-cli)
