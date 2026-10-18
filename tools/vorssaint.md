---
type: Tool
title: Vorssaint
description: Free, open-source macOS menu bar toolkit that bundles dozens of utilities you can install individually.
resource: https://vorssaint.com/
tags:
  - macos
  - utility
  - menu-bar
  - open-source
platforms:
  - macOS
license: GPL-3.0-or-later
pricing: Free
sources:
  - id: vorssaint
    resource: https://github.com/vorssaint/vorssaint-utils
    title: vorssaint/vorssaint-utils README
  - id: homebrew
    resource: https://formulae.brew.sh/cask/vorssaint
    title: "Homebrew: vorssaint"
---
# Vorssaint

A macOS menu bar toolkit that brings many small utilities together under one icon. You install only the features you want; the ones you remove stop loading and drop out of the interface. It's free, has no account, telemetry or subscription, and is licensed GPL-3.0-or-later. The Vorssaint name and look are trademarked separately.[^vorssaint]

## Features

From the README, grouped as there:[^vorssaint]

- **Sound:** per-app volume (including boost above 100%) without an audio driver, per-app output device, output switcher, microphone tools.
- **System:** CPU, GPU, memory, temperature and battery monitor, fan control (beta), menu bar readouts, network speed test, alerts.
- **Windows and Dock:** app switcher with live previews, window snapping, Dock window previews, quit-on-close, and protection against accidental ⌘Q and ⌘W.
- **Keyboard and mouse:** text snippets, smooth and linear scrolling, pointer acceleration control, side buttons, middle click, key debounce.
- **Clipboard and files:** clipboard history, paste as plain text, a drag-and-drop file shelf, Finder cut/paste and F2 rename, tracking-link cleaner.
- **Everyday tools:** a Dynamic Island around the camera notch, a Command Bar, a radial menu and a scratchpad.
- **AI agent tracking:** shows usage limits, tokens, models and live work for Claude, Codex, OpenCode and GitHub Copilot.
- **Capture:** screenshots with annotation, screen recording with editing, offline text recognition, colour picker.
- **App management:** app updates, cleaner, uninstaller, a Homebrew manager, and a port manager for processes listening on network ports.
- **Energy and display:** keep-awake, per-display brightness control, extra XDR brightness.

## Privacy

It works locally with no analytics. The network is used only for actions you can see, such as update checks, the speed test, Homebrew actions and links you choose to share. Every permission is optional.[^vorssaint]

## Install

```sh
brew install --cask vorssaint
```

Requires an Apple silicon Mac with macOS 14 or later.[^homebrew] [^vorssaint] Builds are signed with an Apple Developer ID and notarized; a disk image is also available on the GitHub releases page.[^vorssaint]

## See also

- [macOS utilities](../concepts/macos-utilities.md)

[^vorssaint]: [vorssaint/vorssaint-utils README](https://github.com/vorssaint/vorssaint-utils)
[^homebrew]: [Homebrew: vorssaint](https://formulae.brew.sh/cask/vorssaint)
