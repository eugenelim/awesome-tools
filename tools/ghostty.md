---
type: Tool
title: Ghostty
description: Fast, feature-rich, native terminal emulator for macOS and Linux with GPU acceleration.
resource: https://ghostty.org/
tags:
  - terminal
  - macos
  - linux
platforms:
  - macOS
  - Linux
sources:
  - id: ghostty
    resource: https://ghostty.org/docs/about
    title: Ghostty Docs and About Ghostty
  - id: homebrew
    resource: https://formulae.brew.sh/cask/ghostty
    title: "Homebrew: ghostty"
---
# Ghostty

A terminal emulator that aims to be fast, feature-rich and native at the same time. Mitchell Hashimoto started it as a passion project.[^ghostty]

## Features

From the Ghostty docs:[^ghostty]

- Native GUIs: Swift with AppKit/SwiftUI on macOS, Zig with GTK4 on Linux. Tabs and splits are native widgets.
- Platform-specific default keybindings.
- macOS integrations: Quick Look, force touch, secure input, window state restore and a drop-down terminal.
- Kitty graphics protocol, light/dark mode notifications and hyperlinks.
- Runs with no configuration; hundreds of config options and built-in themes, with separate light and dark themes.
- Built on `libghostty`, a cross-platform C-ABI core for terminal emulation, fonts and rendering. Its API is not yet stable.

## Platforms

Prebuilt binaries for macOS. On Linux, install a distro package or build from source.[^ghostty]

## Install

```sh
brew install --cask ghostty
```

Requires macOS 13 or later.[^homebrew]

## See also

- [Terminal emulators](../concepts/terminal-emulators.md)

[^ghostty]: [Ghostty Docs](https://ghostty.org/docs) and [About Ghostty](https://ghostty.org/docs/about)
[^homebrew]: [Homebrew: ghostty](https://formulae.brew.sh/cask/ghostty)
