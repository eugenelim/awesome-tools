---
type: Tool
title: Codex
description: OpenAI's open-source coding agent for the terminal, with IDE, desktop app and cloud variants.
resource: https://github.com/openai/codex
tags:
  - ai-agents
  - cli
  - open-source
platforms:
  - macOS
  - Linux
  - Windows
license: Apache-2.0
sources:
  - id: codex
    resource: https://github.com/openai/codex
    title: openai/codex README
  - id: homebrew
    resource: https://formulae.brew.sh/cask/codex
    title: "Homebrew: codex"
---
# Codex

OpenAI's lightweight coding agent that runs in the terminal. Licensed under Apache-2.0.[^codex]

## Variants

From the README:[^codex]

- **Codex CLI**: the terminal agent.
- **IDE extension** for VS Code, Cursor and Windsurf.
- **Desktop app**: run `codex app`.
- **Codex Web**: a cloud-based agent at chatgpt.com/codex.

Sign in with a ChatGPT Plus, Pro, Business, Edu or Enterprise plan, or use an API key.[^codex]

## Install

```sh
brew install --cask codex       # CLI
brew install --cask codex-app   # desktop app (macOS 12+)
```

[^codex] [^homebrew] Other options: `curl -fsSL https://chatgpt.com/codex/install.sh | sh` on macOS and Linux, a PowerShell installer on Windows, or `npm install -g @openai/codex`. Run `codex` to start.[^codex]

## See also

- [AI coding agents](../concepts/ai-coding-agents.md)

[^codex]: [openai/codex README](https://github.com/openai/codex)
[^homebrew]: [Homebrew: codex](https://formulae.brew.sh/cask/codex) and [codex-app](https://formulae.brew.sh/cask/codex-app)
