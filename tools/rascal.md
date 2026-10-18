---
type: Tool
title: Rascal
description: Free, open-source, keyboard-first Finder replacement for macOS with dual panes, vim keys and a disk treemap.
resource: https://tryrascal.org/
tags:
  - file-manager
  - macos
  - open-source
platforms:
  - macOS
license: MIT
pricing: Free
sources:
  - id: rascal
    resource: https://tryrascal.org/
    title: Rascal homepage and repository
---
# Rascal

A keyboard-first Finder replacement for macOS. It is free with no paid tier, open source (MIT), works locally with no account, and has no telemetry. It is developed by a single maintainer (`chang-07` on GitHub), with the repository created in May 2026.[^rascal]

## Features

From the Rascal site:[^rascal]

- A fuzzy command palette (⌘⇧P) and vim keys (`hjkl`, `/`, `dd`, `gg`).
- Dual panes, tabs, and four view modes: List, Icon, Column and Gallery.
- A live, colour-coded disk treemap of any folder.
- 17 built-in themes, plus custom themes written in JSON.
- Finder tags, and saved searches pinned to the sidebar.

## Requirements

macOS 13 or later, on Apple silicon or Intel.[^rascal]

## Install

```sh
brew install --cask chang-07/tap/rascal
```

This installs from the developer's own Homebrew tap, not homebrew/cask.[^rascal]

Rascal is ad-hoc signed, so macOS blocks it on first open. Right-click the app and choose **Open**. If macOS still blocks it or says it's "damaged", run:[^rascal]

```sh
xattr -cr /Applications/Rascal.app
```

That command removes macOS's quarantine flag from the app. Rascal can also be built from source.[^rascal]

## See also

- [File managers](../concepts/file-managers.md)
- [Swift Salamander](./swift-salamander.md)

[^rascal]: [Rascal homepage](https://tryrascal.org/) and [repository](https://github.com/chang-07/rascal)
