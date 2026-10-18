---
type: Tool
title: Obsidian
description: Local-first note-taking app that stores notes as plain Markdown files, with links, graph, canvas and plugins.
resource: https://obsidian.md/
tags:
  - notes
  - markdown
  - knowledge-management
pricing: Free; paid Sync and Publish add-ons
sources:
  - id: obsidian
    resource: https://obsidian.md/
    title: Obsidian homepage
  - id: homebrew
    resource: https://formulae.brew.sh/cask/obsidian
    title: "Homebrew: obsidian"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/obsidian
    title: "Chocolatey: obsidian"
---
# Obsidian

A free note-taking app that keeps notes on your device as plain-text Markdown files. Notes are available offline and stay in an open format.[^obsidian]

## Features

From the vendor homepage:[^obsidian]

- Links between notes, an interactive graph view, and Canvas, an infinite board for laying out ideas.
- Thousands of community plugins and themes on an open API, for example Calendar, Kanban, Dataview, Outliner and Tasks.
- Sync, a paid add-on: end-to-end encrypted, one year of version history, shared vaults, selective sync.
- Publish, a paid add-on: publish notes as a website with themes, custom domains and password protection.
- Web Clipper.

## Install

```sh
brew install --cask obsidian
```

Requires macOS 12 or later.[^homebrew]

On Windows with [Chocolatey](./chocolatey.md):[^choco-pkg]

```powershell
choco install obsidian
```

## See also

- [Knowledge management](../concepts/knowledge-management.md)
- [SilverBullet](./silverbullet.md)
- [OpenKnowledge](./openknowledge.md)

[^obsidian]: [Obsidian homepage](https://obsidian.md/)
[^homebrew]: [Homebrew: obsidian](https://formulae.brew.sh/cask/obsidian)

[^choco-pkg]: [Chocolatey: obsidian](https://community.chocolatey.org/packages/obsidian)
