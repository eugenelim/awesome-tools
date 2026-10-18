---
type: Tool
title: SigmaOS
description: WebKit-based macOS browser built around workspaces, vertical tabs and an AI assistant, with Chromium extension support.
resource: https://sigmaos.com/
tags:
  - browser
  - macos
  - ai
platforms:
  - macOS
pricing: Free (Personal); Pro from $20/month
sources:
  - id: sigmaos
    resource: https://sigmaos.com/
    title: SigmaOS homepage and Homebrew entry
---
# SigmaOS

A macOS browser built in SwiftUI on Safari's WebKit engine. It organises tabs into workspaces and includes an AI assistant called Airis.[^sigmaos]

## Features

From the SigmaOS site:[^sigmaos]

- Workspaces with vertical tabs. Tabs can be marked done like tasks, or locked to keep them.
- Split screen, Focus Mode, and single-key shortcuts such as `W` for a new workspace and `D` to mark a page done.
- Lazy Search: press space to search tabs, the web, commands and bookmarks.
- Airis can answer questions about the page you're on and search the web for you. Unlimited use requires Pro.
- Runs Chromium extensions despite using WebKit.
- Passwords are stored in Apple Keychain, and WebKit's Intelligent Tracking Protection is built in.
- Separate profiles per workspace for different logins, page suspension to save RAM, and a built-in ad blocker.
- Imports logins, cookies and history from your previous browser, and syncs your setup across Macs through a SigmaOS account.

## Pricing

The Personal plan is free. Pro starts at $20 a month and adds unlimited Airis use; students and educators get 50% off.[^sigmaos]

## Platforms

macOS only. iOS and Windows are announced as "coming soon".[^sigmaos]

## Install

```sh
brew install --cask sigmaos
```

Requires macOS 12 or later.[^sigmaos]

## See also

- [Web browsers](../concepts/web-browsers.md)
- [Firefox Developer Edition](./firefox-developer-edition.md)

[^sigmaos]: [SigmaOS homepage](https://sigmaos.com/) and [Homebrew: sigmaos](https://formulae.brew.sh/cask/sigmaos)
