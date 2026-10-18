---
type: Tool
title: Swift Salamander
description: Dual-pane file manager for Apple silicon Macs, in Early Access, with a free tier and a one-time Pro licence.
resource: https://swiftsalamander.app/
tags:
  - file-manager
  - macos
platforms:
  - macOS
pricing: Free; Pro $15 one-time (Early Access)
sources:
  - id: swiftsalamander
    resource: https://swiftsalamander.app/
    title: Swift Salamander homepage
---
# Swift Salamander

A dual-pane file manager for macOS that works with local folders, network shares and cloud storage. It is in Early Access, and the vendor advises keeping backups because bugs that could affect files are expected.[^swiftsalamander]

## Features

From the vendor homepage:[^swiftsalamander]

- One or two panes in the free version; three or four panes and named workspaces in Pro.
- 38 remote storage providers plus SFTP, SMB and WebDAV. Direct-connection passwords are stored in macOS Keychain; cloud credentials are stored in a local rclone config.
- Copy verification by hash (on by default), checked cross-volume moves, and an operation journal for recovering interrupted operations.
- Rust engine, APFS copy-on-write cloning, virtualised file lists.
- No usage telemetry.
- Pro tools: terminal, batch rename with preview, folder compare, disk analyser, duplicate finder, Git status, process and network analysers, app deleter, image compression.

## Requirements and pricing

- Apple silicon (M1 or newer) running macOS 13 or newer; Intel Macs are not supported.[^swiftsalamander]
- Free: $0, with no expiry; includes a 7-day Pro trial.[^swiftsalamander]
- Pro: $15 one-time during Early Access, rising at 1.0. Covers up to 3 Macs, includes 12 months of updates, and update renewal is $12.[^swiftsalamander]

## Install

```sh
brew install --cask c0desurfer/tap/swift-salamander
```

A Nix package is also offered.[^swiftsalamander]

## See also

- [File managers](../concepts/file-managers.md)

[^swiftsalamander]: [Swift Salamander homepage](https://swiftsalamander.app/)
