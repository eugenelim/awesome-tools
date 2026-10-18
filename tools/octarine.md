---
type: Tool
title: Octarine
description: Private, local-first Markdown note-taking app with a one-time licence.
resource: https://octarine.app/
tags:
  - notes
  - markdown
  - knowledge-management
platforms:
  - macOS
  - Windows
  - Linux
  - iOS
pricing: Free; Personal $79 one-time; Team $129/seat one-time (beta)
sources:
  - id: octarine
    resource: https://octarine.app/
    title: Octarine homepage and pricing
  - id: homebrew
    resource: https://formulae.brew.sh/cask/octarine
    title: "Homebrew: octarine"
---
# Octarine

A Markdown note-taking app that keeps notes as plain Markdown files stored where you choose. A single developer builds it, and it has no venture funding.[^octarine]

## Features

From the vendor site:[^octarine]

- Quick Capture over any app, an Inbox for unsorted items, and Daily Desk notes that carry open tasks forward.
- Split panes, links to a specific heading, and links that keep working when notes move.
- Note Types (property templates), filtered Views and full-text search.
- Ask Octarine and Writing Assistant can edit notes. They work with your own API key, a local LLM, or a Claude Code, OpenCode or ChatGPT subscription.
- Publishing and comments on shared notes; Teams for private sharing within a company.

## Pricing

| Plan | Price |
| --- | --- |
| Free | $0 |
| Personal | $79 one-time, up to 3 devices |
| Team | $129 per seat, one-time (beta) |

There is no subscription. Every licence includes future updates and covers macOS, Windows and Linux, plus the iOS app, which is in TestFlight.[^octarine]

## Install

```sh
brew install --cask octarine
```

[^homebrew]

## See also

- [Knowledge management](../concepts/knowledge-management.md)

[^octarine]: [Octarine homepage](https://octarine.app/) and [pricing](https://octarine.app/pricing)
[^homebrew]: [Homebrew: octarine](https://formulae.brew.sh/cask/octarine)
