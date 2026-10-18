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
    resource: /sources/logseq-github.md
    title: Logseq README, release and Homebrew entry
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

## See also

- [Knowledge management](../concepts/knowledge-management.md)
- [Obsidian](./obsidian.md)

[^logseq]: [Logseq README, release and Homebrew entry](../sources/logseq-github.md)
