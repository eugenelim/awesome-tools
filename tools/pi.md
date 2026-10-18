---
type: Tool
title: Pi
description: Minimal, extensible coding agent CLI and agent toolkit from Earendil.
resource: https://github.com/earendil-works/pi
tags:
  - ai-agents
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
sources:
  - id: pi
    resource: https://github.com/earendil-works/pi
    title: earendil-works/pi README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/pi-coding-agent
    title: "Homebrew: pi-coding-agent"
---
# Pi

A minimal, extensible agent harness and coding agent CLI. You can customise it with extensions, skills, prompt templates and themes, and share them as Pi packages through npm or git. It doesn't include sub-agents or plan mode by default. MIT licensed.[^pi]

## Features

From the README:[^pi]

- Can run interactively, in print or JSON mode, over RPC, or through the Pi TypeScript SDK.
- Run `/login` to connect a provider subscription or API key.
- No built-in permission system: Pi runs with the launching user's permissions. The README covers sandboxing it in a micro-VM via the Gondolin extension, in Docker, or with OpenShell.
- Monorepo packages: `pi-coding-agent` (the CLI), `pi-ai` (a multi-provider LLM API), `pi-agent-core`, `pi-tui`, `pi-durable`, `pi-telemetry` and `chord`.

[VelaTerm](./velaterm.md) and [Orca](./orca.md) both list Pi among the agents they run.

## Install

```sh
brew install pi-coding-agent
```

This is a Homebrew formula, not a cask.[^homebrew] The upstream options are the install script `curl -fsSL https://pi.dev/install.sh | sh`, which pins dependencies and updates with `pi update`, or `npm install -g --ignore-scripts @earendil-works/pi-coding-agent`. Either way it needs Node.js 22.19 or newer.[^pi]

## See also

- [AI coding agents](../concepts/ai-coding-agents.md)

[^pi]: [earendil-works/pi README](https://github.com/earendil-works/pi)
[^homebrew]: [Homebrew: pi-coding-agent](https://formulae.brew.sh/formula/pi-coding-agent)
