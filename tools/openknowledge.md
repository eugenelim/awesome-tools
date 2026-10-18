---
type: Tool
title: OpenKnowledge
description: Open-source WYSIWYG Markdown editor and knowledge base for humans and AI agents, with MCP and agent skills.
resource: https://openknowledge.ai/
tags:
  - notes
  - markdown
  - knowledge-management
  - ai-agents
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - Web
license: GPL-3.0
pricing: Free
sources:
  - id: ok-docs
    resource: /sources/openknowledge-docs-overview.md
    title: OpenKnowledge docs overview
  - id: ok-github
    resource: /sources/openknowledge-github.md
    title: inkeep/open-knowledge on GitHub
---
# OpenKnowledge

A WYSIWYG Markdown editor for co-writing knowledge bases and documents with AI agents you already use, such as Claude, Codex, Cursor, OpenCode, Pi, OpenClaw and Antigravity.[^ok-docs] It is free, open source under GPL-3.0, and maintained by Inkeep.[^ok-github]

## Features

The docs describe it as three layers:[^ok-docs]

1. A WYSIWYG editor that supports interactive HTML and JS, Mermaid diagrams, LaTeX, video and PDF.
2. An MCP server and agent skills that let agents search, edit, organise and maintain the knowledge base.
3. Plain `.md` or `.mdx` files in the project, version-controlled with git.

Other features listed in the docs:[^ok-docs]

- Skills Studio, for writing and finding agent skills.
- In-app agent chat, or handing work off to an external agent app or the built-in terminal UI.
- Comments that an agent can resolve.
- Git-based auto-sync with a team.
- Graph and wiki-link views.
- Remote connections from agents and other devices.
- Starter packs, including an Open Knowledge Format (OKF) pack and plugin.
- Import from Obsidian and Notion.

## Platforms

Desktop apps for macOS 13 or later, Windows and Linux. A local web app and CLI run on any platform, including Intel Macs.[^ok-docs] Desktop installers: DMG on Apple silicon Macs, a per-user Setup installer on Windows 10+ (x64/Arm64), and deb or rpm packages on Linux (x64/arm64).[^ok-github]

## Install (CLI / web app)

Requires Node.js 24+ and git.[^ok-github]

```sh
npm install -g @inkeep/open-knowledge
cd your-project
ok init
ok start --open
```

## See also

- [Knowledge management](../concepts/knowledge-management.md)
- [Obsidian](./obsidian.md)
- [SilverBullet](./silverbullet.md)

[^ok-docs]: [OpenKnowledge docs overview](../sources/openknowledge-docs-overview.md)
[^ok-github]: [inkeep/open-knowledge on GitHub](../sources/openknowledge-github.md)
