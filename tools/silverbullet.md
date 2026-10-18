---
type: Tool
title: SilverBullet
description: Open-source Markdown knowledge management with Space Lua scripting, available as a desktop app or self-hosted server.
resource: https://silverbullet.md/
tags:
  - notes
  - markdown
  - knowledge-management
  - self-hosted
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - Web
license: MIT (Server and sb CLI)
pricing: Desktop free for personal use; Server free
sources:
  - id: silverbullet
    resource: /sources/silverbullet-homepage.md
    title: SilverBullet homepage
  - id: homebrew
    resource: /sources/homebrew-api.md
    title: Homebrew API snapshot
---
# SilverBullet

An open-source knowledge management system that stores everything as plain Markdown files in a folder you control. It can be used for personal notes, a team wiki, documentation kept alongside code, or a shared family space.[^silverbullet]

## Features

From the project homepage:[^silverbullet]

- Space Lua, a built-in scripting language whose scripts are stored as pages in the space.
- Queries over notes, written in Space Lua.
- Links, backlinks and an object graph.
- Team features: task assignment with @mentions, comments, live edits.
- Notes are ordinary files that any editor or git can work with.

## Deployment

| Option | Notes |
| --- | --- |
| Desktop | Native app for macOS, Windows and Linux; free for personal use |
| Server | Self-hosted single container, used from any browser; open source and free |
| Hosted | Third-party providers run Server |

Desktop syncs with any Server. Server and the `sb` CLI are MIT licensed.[^silverbullet]

## Install

No Homebrew cask or formula.[^homebrew]

## See also

- [Knowledge management](../concepts/knowledge-management.md)
- [Obsidian](./obsidian.md)
- [OpenKnowledge](./openknowledge.md)

[^silverbullet]: [SilverBullet homepage](../sources/silverbullet-homepage.md)
[^homebrew]: [Homebrew API snapshot](../sources/homebrew-api.md)
