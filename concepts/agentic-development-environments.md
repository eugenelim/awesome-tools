---
type: Category
title: Agentic development environments
description: Applications for running and supervising multiple AI coding agents, combining terminals, agent sessions and git worktrees.
---
# Agentic development environments

Applications for running and supervising several AI coding agents at once. They combine terminals, agent sessions and git worktrees. VelaTerm and Orca are desktop apps; herdr is a single binary that runs inside an existing terminal.

| | [VelaTerm](../tools/velaterm.md) | [Orca](../tools/orca.md) | [herdr](../tools/herdr.md) |
| --- | --- | --- | --- |
| Form | Desktop app (Tauri 2) | Desktop app | Single Rust binary in your terminal |
| Licence | MIT | MIT | Apache-2.0 |
| Organising unit | Session tree | Worktree per task | Panes in a background server |
| Multi-agent | Plan / Execute mode; cross-session messaging | Same prompt to multiple agents, then compare | Agents spawn, prompt and wait on each other via socket API |
| Agent status | Live session states | Usage tracking | Working / blocked / idle per pane |
| Remote | SSH, E2EE browser, iOS/Android | SSH worktrees, iOS/Android | SSH machines in one window |
| Platforms | macOS, Windows, Linux | macOS, Windows, Linux | macOS, Linux, Windows |

See also [terminal emulators](./terminal-emulators.md) and [AI coding agents](./ai-coding-agents.md).
