---
type: Tool
title: Orca
description: Free, open-source agent development environment for running CLI coding agents in parallel git worktrees.
resource: https://www.onorca.dev/
tags:
  - ai-agents
  - ade
  - git
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - iOS
  - Android
license: MIT
pricing: Free
sources:
  - id: orca
    resource: https://www.onorca.dev/
    title: Orca homepage
  - id: orca-readme
    resource: https://github.com/stablyai/orca
    title: stablyai/orca README
  - id: homebrew
    resource: https://formulae.brew.sh/cask/orca
    title: "Homebrew: orca (plotly)"
---
# Orca

An agent development environment (ADE) that runs Claude Code, Codex and other CLI coding agents in parallel, each in its own git worktree, with terminals, diffs, a browser and a CLI in one app. Free and open source (MIT).[^orca]

## Features

From the vendor homepage:[^orca]

- Gives every task its own git worktree; one prompt can go to several agents and the best result gets merged.
- Works with more than 25 named agent CLIs and with any other CLI agent, using your existing subscriptions.
- Design Mode: a Chromium window per worktree; clicking an element sends its HTML, CSS and a screenshot to the agent.
- Line-level diff annotations, CI inspection, conflict resolution and PR creation; GitHub and Linear integration.
- SSH worktrees for running agents on a remote machine.
- Orca CLI that agents can use to drive Orca itself.
- Claude and Codex usage tracking and Codex account switching.
- WebGL terminal with unlimited splits and scrollback that persists across restarts.

## Platforms

Desktop apps for macOS, Windows and Linux, plus an iOS and Android companion app.[^orca]

## Install

```sh
brew install --cask stablyai/orca/orca
```

This installs from Orca's own tap.[^orca-readme] Use the full tap path: the `orca` cask in homebrew/cask is a different program, plotly's chart-image tool, and it is disabled.[^homebrew]

## See also

- [Agentic development environments](../concepts/agentic-development-environments.md)
- [VelaTerm](./velaterm.md)

[^orca]: [Orca homepage](https://www.onorca.dev/)
[^orca-readme]: [stablyai/orca README](https://github.com/stablyai/orca)
[^homebrew]: [Homebrew: orca](https://formulae.brew.sh/cask/orca) (the unrelated plotly cask)
