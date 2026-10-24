---
type: Tool
title: Paper
description: Design tool with an HTML/CSS canvas that AI agents can read and write through MCP.
resource: https://paper.design/
tags:
  - design
  - ui
  - mcp
  - ai-agents
platforms:
  - macOS
  - Web
pricing: Free; Pro $20/editor/month ($16 billed yearly); Organizations by contract
sources:
  - id: paper
    resource: https://paper.design/
    title: Paper homepage and pricing
  - id: homebrew
    resource: https://formulae.brew.sh/cask/paper-design
    title: "Homebrew: paper-design"
---
# Paper

A design tool for interfaces and prototypes. Its canvas is built on HTML and CSS, so designs export as code.[^paper] [^homebrew] It runs as a desktop app and in the browser.[^paper]

## Features

From the vendor site:[^paper]

- The desktop app connects to IDE and CLI agents through MCP.
- Agents can sync design tokens, styles and components between a codebase and the canvas.
- Layers can pull data from files, a CMS, databases or APIs.
- Copy can be edited on the canvas and sent back to the codebase by an agent.
- Agents can handle repetitive work such as responsive variants and consistency checks.

## Pricing

| Plan | Price | Notes |
| --- | --- | --- |
| Free | $0 | Unlimited viewers and editors; 100 MCP tool calls/week |
| Pro | $20/editor/month ($16 billed yearly) | 1M MCP tool calls/week; video export |
| Organizations | Contact sales | SAML/SSO, admin controls |

Viewer seats are always free.[^paper]

## Install

```sh
brew install --cask paper-design
```

Requires macOS 13 or later on Apple silicon.[^homebrew]

## See also

- [Design tools](../concepts/design-tools.md)
- [Penpot](./penpot.md)

[^paper]: [Paper homepage](https://paper.design/) and [pricing](https://paper.design/pricing)
[^homebrew]: [Homebrew: paper-design](https://formulae.brew.sh/cask/paper-design)
