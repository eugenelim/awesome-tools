---
type: Tool
title: Forel
description: Open-source, on-device folder automation for macOS; a Hazel alternative that runs from the menu bar.
resource: https://github.com/lab421/forel
tags:
  - macos
  - automation
  - utility
  - menu-bar
  - open-source
platforms:
  - macOS
license: GPL-3.0
sources:
  - id: forel
    resource: https://github.com/lab421/forel
    title: lab421/forel README
---
# Forel

A folder-automation app for macOS that runs from the menu bar and describes itself as an open-source alternative to Hazel. It watches folders and acts on files that match rules you define. Everything runs on your Mac, with no cloud service and no AI API keys. Licensed under GPL-3.0.[^forel]

It is a single maintainer's spare-time project, created in June 2026.[^forel]

## Features

From the README:[^forel]

- Rules match on filename, extension, kind, size, date, tags, colour label or file contents.
- On-device OCR, so rules can match text in images and scanned PDFs.
- Real-time folder watching using macOS FSEvents, for any number of folders.
- Actions: move, copy, rename, tag, trash, delete, or run a custom Bash script.
- **Dry Run** previews matches and planned actions without changing anything; **Run Now** applies rules to files already in a folder.
- History, plus undo for supported actions. Script actions can't be undone.
- Rules can be switched on or off from the menu bar.

## Install

```sh
brew install --cask lab421/tap/forel
```

This installs from the project's own Homebrew tap. Forel requires macOS 13 or later; building from source needs Swift 6 and macOS 14. A `.dmg` is also available on the GitHub releases page.[^forel]

## See also

- [macOS utilities](../concepts/macos-utilities.md)
- [File managers](../concepts/file-managers.md)

[^forel]: [lab421/forel README](https://github.com/lab421/forel)
