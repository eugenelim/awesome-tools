---
type: Tool
title: Windows Subsystem for Linux (WSL)
description: Windows feature for running Linux distributions without a separate VM or dual boot.
resource: https://learn.microsoft.com/en-us/windows/wsl/
tags:
  - windows
  - linux
  - open-source
platforms:
  - Windows 10 2004+ (build 19041+)
  - Windows 11
license: MIT
sources:
  - id: wsl
    resource: https://learn.microsoft.com/en-us/windows/wsl/install
    title: WSL About and Install docs
---
# Windows Subsystem for Linux (WSL)

A Windows feature for running Linux distributions such as Ubuntu, Debian and Kali without a separate virtual machine or dual booting. It is open source (MIT).[^wsl]

## Features

From Microsoft's docs:[^wsl]

- Install distributions from the Microsoft Store, import others from a TAR file, or build your own.
- Each distribution gets its own isolated Linux file system.
- Linux CLI tools, languages and services run unmodified, and each distribution's own package manager works.
- Windows apps can be called from Linux and Linux apps from Windows.
- Linux GUI apps run on the Windows desktop.
- GPU acceleration for machine-learning workloads.
- WSL 2 is the default. It runs a real Linux kernel in a lightweight VM, giving faster file-system performance and full system-call compatibility compared with WSL 1. Each distribution can use WSL 1 or WSL 2.

## Install

Requires Windows 10 version 2004 or later (build 19041+) or Windows 11. In an administrator PowerShell, run the following, then restart:[^wsl]

```powershell
wsl --install
```

This installs Ubuntu by default. To choose a different distribution:[^wsl]

```powershell
wsl --list --online
wsl --install -d <DistroName>
```

You'll create a Linux username and password on first launch.[^wsl]

## See also

- [Windows platform tools](../concepts/windows-platform-tools.md)
- [Chocolatey](./chocolatey.md)

[^wsl]: [What is WSL](https://learn.microsoft.com/en-us/windows/wsl/about) and [Install WSL](https://learn.microsoft.com/en-us/windows/wsl/install)
