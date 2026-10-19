---
type: Tool
title: Google Antigravity
description: Google's desktop platform for launching, monitoring and coordinating parallel AI agents.
resource: https://antigravity.google/
tags:
  - ai-agents
  - ade
  - google
platforms:
  - macOS
  - Windows
  - Linux
sources:
  - id: antigravity
    resource: https://antigravity.google/product/antigravity-2
    title: Google Antigravity 2 product page
  - id: homebrew
    resource: https://formulae.brew.sh/cask/antigravity
    title: "Homebrew: antigravity"
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/Google/Antigravity
    title: "winget: Google.Antigravity"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/antigravity
    title: "Chocolatey: antigravity"
---
# Google Antigravity

Google's desktop app for running several AI agents in parallel across projects, described as "Your AI agents' central command center".[^antigravity] Homebrew lists it as an "Agent orchestration platform".[^homebrew]

## Features

From the product page:[^antigravity]

- One interface to launch, monitor and coordinate agents.
- Subagents created on demand to split up complex problems.
- Agents can run on a cron schedule in the background.
- Artifacts that show an agent's progress.
- Skills, MCP servers and JSON hooks, set globally or per workspace.
- Projects that group conversations across folders, with scoped permissions.
- Voice prompts transcribed with Gemini audio models.

The page also announces Gemini 4 Argon for Google AI Pro and Ultra subscribers.[^antigravity]

## Platforms

macOS (Apple silicon and Intel), Windows, Linux and Googlebook.[^antigravity]

## Install

```sh
brew install --cask antigravity
```

Requires macOS 13 or later.[^homebrew]

On Windows with [winget](./winget.md) (recommended):[^winget-pkg]

```powershell
winget install Google.Antigravity
```

Or with [Chocolatey](./chocolatey.md):[^choco-pkg]

```powershell
choco install antigravity
```

## See also

- [Agentic development environments](../concepts/agentic-development-environments.md)
- [AI coding agents](../concepts/ai-coding-agents.md)

[^antigravity]: [Google Antigravity 2 product page](https://antigravity.google/product/antigravity-2)
[^homebrew]: [Homebrew: antigravity](https://formulae.brew.sh/cask/antigravity)

[^choco-pkg]: [Chocolatey: antigravity](https://community.chocolatey.org/packages/antigravity)

[^winget-pkg]: [winget: Google.Antigravity](https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/Google/Antigravity)
