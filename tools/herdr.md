---
type: Tool
title: herdr
description: Terminal-based agent multiplexer that keeps coding-agent sessions running in a background server.
resource: https://herdr.dev/
tags:
  - terminal
  - ai-agents
  - multiplexer
  - open-source
platforms:
  - macOS
  - Linux
  - Windows
license: Apache-2.0
sources:
  - id: herdr
    resource: https://github.com/herdrdev/herdr
    title: herdrdev/herdr README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/herdr
    title: "Homebrew: herdr"
---
# herdr

A terminal multiplexer for coding agents. It runs Claude Code, Codex, Cursor, OpenCode, Grok and other agent CLIs in terminals held by a background server, without wrapping or replacing them. It ships as a single Rust binary that runs inside your existing terminal, and is licensed under Apache-2.0.[^herdr]

## Features

From the README:[^herdr]

- Agents keep working after you detach or lose an SSH connection. After a restart, herdr restores the layout and can resume supported agent sessions.
- Local and SSH machines in one window, with a combined agent list.
- Every pane is marked working, blocked or idle.
- A CLI and socket API that agents can use to spawn panes, prompt each other and wait on each other.
- tmux-style prefix keys as well as mouse support.
- Plugins.

## Install

```sh
brew install herdr
```

This is a Homebrew formula, not a cask.[^homebrew] [^herdr] Other options are `curl -fsSL https://herdr.dev/install.sh | sh` or `mise use -g herdr`. Run `herdr` to start it; `ctrl+b q` detaches.[^herdr]

## See also

- [Agentic development environments](../concepts/agentic-development-environments.md)
- [Terminal emulators](../concepts/terminal-emulators.md)

[^herdr]: [herdrdev/herdr README](https://github.com/herdrdev/herdr)
[^homebrew]: [Homebrew: herdr](https://formulae.brew.sh/formula/herdr)
