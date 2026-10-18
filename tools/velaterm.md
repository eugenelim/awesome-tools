---
type: Tool
title: VelaTerm
description: Open-source terminal and coding-agent manager that organises agent sessions in a project tree.
resource: https://velaterm.com/
tags:
  - terminal
  - ai-agents
  - ade
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - Web
  - iOS
  - Android
license: MIT
sources:
  - id: velaterm
    resource: https://velaterm.com/
    title: VelaTerm homepage
  - id: homebrew
    resource: https://formulae.brew.sh/
    title: Homebrew catalogue (no package found)
---
# VelaTerm

An agentic development environment (ADE) that runs terminals and coding-agent sessions in one native app, arranged as a tree of projects, groups and sessions. Open source under the MIT licence.[^velaterm]

## Features

From the vendor homepage:[^velaterm]

- Managed sessions for Claude Code, Codex, OpenCode, Copilot, Cursor, Antigravity, Cline and Pi, with live status and resume.
- Each session can be viewed as a conversation or as a terminal.
- `vspawn` creates child sessions, optionally each in its own git worktree.
- `vsearch`, `vrefer` and `vtell` let sessions search, read and message each other.
- Plan / Execute mode: a planner session splits a task among executor sessions working in parallel worktrees.
- Session knowledge base, local Markdown notes, and `vkb` lookup over saved knowledge, notes and a local code graph.
- Built-in Markdown editor, code editor, image viewer and browser.

## Platforms

Desktop apps for macOS, Windows and Linux, built on Tauri 2. Also usable in a browser over end-to-end encrypted HTTPS and from iOS and Android apps. Remote machines connect over SSH, a pairing link or an account.[^velaterm]

## Install

No Homebrew cask or formula.[^homebrew]

## See also

- [Agentic development environments](../concepts/agentic-development-environments.md)
- [Orca](./orca.md)

[^velaterm]: [VelaTerm homepage](https://velaterm.com/)
[^homebrew]: [Homebrew catalogue](https://formulae.brew.sh/): no VelaTerm package as of 2026-10-18
