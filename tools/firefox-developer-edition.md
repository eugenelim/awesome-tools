---
type: Tool
title: Firefox Developer Edition
description: Mozilla's Firefox build for web developers, with beta DevTools and developer-oriented defaults.
resource: https://www.firefox.com/en-US/channel/desktop/developer/
tags:
  - browser
  - web-development
  - devtools
platforms:
  - macOS
  - Windows
  - Linux
pricing: Free
sources:
  - id: firefox-dev
    resource: /sources/firefox-developer-edition.md
    title: Firefox Developer Edition page and Homebrew entry
---
# Firefox Developer Edition

Mozilla's Firefox build for web developers. It ships the latest developer tools while they are still in beta.[^firefox-dev]

## Features

From the Firefox site:[^firefox-dev]

- Uses its own profile and install path, so it can run alongside Release or Beta Firefox.
- Browser and remote debugging, the dark theme and the developer toolbar button are on by default.
- DevTools: Page Inspector, Web Console, JavaScript Debugger, Network Monitor, Storage Panel and Responsive Design Mode.
- CSS Grid inspector, a fonts panel, and greyed-out CSS declarations that have no effect on the page.
- Multi-line Console Editor and WebSocket Inspector.
- Sends feedback to Mozilla automatically.

## Platforms

Windows (including ARM64), macOS and Linux (64-bit and ARM64), plus an APT repository for Debian-based distributions. It no longer supports Windows 8.1 and below or macOS 10.14 and below.[^firefox-dev]

## Install

```sh
brew install --cask firefox@developer-edition
```

[^firefox-dev]

## See also

- [Web browsers](../concepts/web-browsers.md)

[^firefox-dev]: [Firefox Developer Edition page and Homebrew entry](../sources/firefox-developer-edition.md)
