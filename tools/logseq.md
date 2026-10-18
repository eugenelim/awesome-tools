---
type: Tool
title: Logseq
description: Privacy-first, open-source knowledge management and collaboration app supporting Markdown and Org-mode.
resource: https://logseq.com/
tags:
  - notes
  - markdown
  - knowledge-management
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - Android
  - iOS
  - Web
license: AGPL-3.0
sources:
  - id: logseq
    resource: https://github.com/logseq/logseq
    title: Logseq README, release and Homebrew entry
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/logseq
    title: "Chocolatey: logseq"
---
# Logseq

An open-source knowledge management and collaboration app focused on privacy, longevity and user control. It works with Markdown and Org-mode files and includes PDF annotation, task management, plugins and themes. It is licensed under AGPL-3.0.[^logseq]

## DB version

Logseq is introducing a database version ("DB graphs") that comes with a new iOS app and real-time collaboration (RTC) for syncing graphs across devices and with other people. The DB version is in beta and the iOS app and RTC are in alpha, and the project warns that **data loss is possible**, so back up regularly. A web build is available at app.logseq.com.[^logseq]

## Platforms

Release 2.0.2 includes builds for macOS (Apple silicon and Intel), Windows, Linux (x86_64 and arm64) and Android. Linux also has an install script.[^logseq]

## Install

```sh
brew install --cask logseq
```

Requires macOS 12 or later.[^logseq]

On Windows with [Chocolatey](./chocolatey.md). The package was at version 0.10.15 on 2026-10-19, behind the 2.0.2 release, so the GitHub download is newer.[^choco-pkg]

```powershell
choco install logseq
```

## See also

- [Knowledge management](../concepts/knowledge-management.md)
- [Obsidian](./obsidian.md)

[^logseq]: [logseq/logseq README](https://github.com/logseq/logseq), [latest release](https://github.com/logseq/logseq/releases/latest) and [Homebrew: logseq](https://formulae.brew.sh/cask/logseq)

[^choco-pkg]: [Chocolatey: logseq](https://community.chocolatey.org/packages/logseq)
