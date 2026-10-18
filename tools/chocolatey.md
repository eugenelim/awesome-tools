---
type: Tool
title: Chocolatey
description: Package manager for Windows that wraps installers, executables, zips and scripts into packages.
resource: https://chocolatey.org/
tags:
  - windows
  - package-manager
  - open-source
platforms:
  - Windows
license: Apache-2.0 (open source edition)
sources:
  - id: choco
    resource: https://chocolatey.org/install
    title: Chocolatey install page
---
# Chocolatey

A package manager for Windows. It wraps installers, executables, zips and scripts into packages, and integrates with SCCM, Puppet and Chef. There are open-source and commercial editions; the open-source CLI is licensed under Apache-2.0.[^choco]

## Requirements

- A supported Windows client or server OS.[^choco]
- PowerShell v3 or later to install from the website.[^choco]
- .NET Framework 4.8. The installer tries to install it if it's missing.[^choco]

## Install

In an administrative PowerShell, check that `Get-ExecutionPolicy` doesn't return `Restricted`, then run:[^choco]

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

The command downloads and runs `https://community.chocolatey.org/install.ps1`, and Chocolatey recommends reading that script before you run it. Non-admin installs are also supported. Afterwards, run `choco -?` to confirm it works.[^choco]

## See also

- [Windows platform tools](../concepts/windows-platform-tools.md)
- [WSL](./wsl.md)

[^choco]: [Chocolatey install page](https://chocolatey.org/install)
