---
type: Tool
title: Figma
description: Proprietary, browser-based collaborative interface design tool, with desktop apps for macOS and Windows, Dev Mode and an MCP server for AI agents.
resource: https://www.figma.com/
tags:
  - design
  - prototyping
  - collaboration
platforms:
  - Web
  - macOS
  - Windows
license: Proprietary
pricing: Free Starter plan; paid seats from $3/month
sources:
  - id: pricing
    resource: https://www.figma.com/pricing/
    title: Figma pricing
  - id: desktop
    resource: https://help.figma.com/hc/en-us/articles/5601429983767-Guide-to-the-Figma-desktop-app
    title: Guide to the Figma desktop app
  - id: mcp
    resource: https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server
    title: Guide to the Figma MCP server
  - id: packages
    resource: https://formulae.brew.sh/cask/figma
    title: "Homebrew: figma; winget: Figma.Figma; Chocolatey: figma"
---
# Figma

A collaborative design tool for interfaces and prototypes. It runs in the browser, and the desktop apps for macOS and Windows have the same features.[^desktop] For an open-source design tool you can host yourself, see [Penpot](./penpot.md).

## Desktop app or browser

The desktop app is optional. It adds:[^desktop]

- **Local fonts:** use fonts installed on your machine without installing Figma's font installer.
- **Notifications:** from the menu bar on a Mac or the system tray on Windows; these are desktop-only.
- **Tabs and windows:** each file opens in a tab, with pinned tabs, tab groups, split view and multiple windows.
- **Plugin and widget development.**

It needs macOS 12 or later (Intel or Apple silicon), or 64-bit Windows 10 or later; there's a separate Windows Arm download. There's no Linux app.[^desktop]

## AI agents: the MCP server

Figma's MCP server gives AI agents design context for generating code, and can create and change Figma content on the canvas.[^mcp]

- **Remote server:** connects to `https://mcp.figma.com/mcp` without the desktop app. Figma calls it the best choice for most users.[^mcp]
- **Desktop server:** runs through the desktop app, for specific organisation and enterprise needs. It needs a Dev or Full seat on a paid plan.[^mcp]
- **Writing to the canvas:** needs the remote server, and a Full seat to write outside your drafts. It's free during the beta.[^mcp]

It's available on every plan, including the free Starter plan; check Figma's plans page for usage limits.[^mcp]

## Pricing

Paid plans are priced per seat, with three seat types:[^pricing]

| Plan | Full seat | Dev seat | Collab seat | Notes |
| --- | --- | --- | --- | --- |
| Starter | $0 | | | Unlimited drafts; 150 AI credits a day, up to 500 a month |
| Professional | $16/month | $12/month | $3/month | Advanced Dev Mode inspection and the MCP server |
| Organization | $55/month | $25/month | $5/month | Billed annually |
| Enterprise | $90/month | $35/month | $5/month | Billed annually |

Prices from Figma's pricing page on 2026-10-24; paid seats also include monthly AI credits.[^pricing]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask figma` |
| Windows | `winget install Figma.Figma` |
| Any | figma.com in a browser |

On 2026-10-24 Homebrew had 126.9.16, and the cask updates itself. winget had 126.9.9. Chocolatey's `figma` is at 116.12.2, well behind, so it isn't listed.[^packages]

## See also

- [Design tools](../concepts/design-tools.md)
- [Penpot](./penpot.md)
- [Paper](./paper.md)

[^pricing]: [Figma pricing](https://www.figma.com/pricing/), checked 2026-10-24
[^desktop]: [Guide to the Figma desktop app](https://help.figma.com/hc/en-us/articles/5601429983767-Guide-to-the-Figma-desktop-app)
[^mcp]: [Guide to the Figma MCP server](https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server)
[^packages]: Homebrew: [figma](https://formulae.brew.sh/cask/figma); winget: [Figma.Figma](https://github.com/microsoft/winget-pkgs/tree/master/manifests/f/Figma/Figma); Chocolatey: [figma](https://community.chocolatey.org/packages/figma); checked 2026-10-24
