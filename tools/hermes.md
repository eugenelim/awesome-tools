---
type: Tool
title: Hermes Agent
description: Nous Research's open-source, self-hosted personal AI agent that learns skills from experience and works across chat apps.
resource: https://hermes-agent.nousresearch.com/
tags:
  - ai-agents
  - personal-assistant
  - self-hosted
  - open-source
platforms:
  - macOS
  - Linux
  - Windows
  - Android (Termux)
license: MIT
sources:
  - id: hermes
    resource: https://github.com/NousResearch/hermes-agent
    title: Hermes Agent README and Homebrew entries
---
# Hermes Agent

An open-source (MIT) personal AI agent from Nous Research. It creates skills from experience and improves them as it uses them, searches its own past conversations, and builds a model of you across sessions. You run it yourself on a laptop, a VPS, a GPU cluster or serverless infrastructure.[^hermes]

## Features

From the README:[^hermes]

- Works with any model provider (Nous Portal, OpenRouter, OpenAI, your own endpoint and others); switch with `hermes model`.
- A full terminal UI, plus one gateway that connects it to Telegram, Discord, Slack, WhatsApp, Signal and email.
- A built-in cron scheduler for unattended jobs.
- Spawns isolated subagents to run work in parallel.
- Seven execution backends: local, Docker, SSH, Singularity, Modal, Daytona and Vercel Sandbox.
- `hermes claw migrate` imports an existing OpenClaw setup.
- Optional Nous Portal subscription: one account covering 300+ models, plus web search, image generation, text-to-speech and a cloud browser.

## Platforms

Linux, macOS, WSL2, native Windows, and Android via Termux.[^hermes]

## Install

```sh
brew install hermes-agent           # CLI
brew install --cask hermes-desktop  # desktop app
```

[^hermes] Other options are `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash` on Linux, macOS or WSL2, or `iex (irm https://hermes-agent.nousresearch.com/install.ps1)` in PowerShell. Then run `hermes setup`.[^hermes]

## See also

- [Personal AI agents](../concepts/personal-ai-agents.md)
- [Muse](./muse.md)

[^hermes]: [NousResearch/hermes-agent README](https://github.com/NousResearch/hermes-agent); Homebrew: [hermes-agent](https://formulae.brew.sh/formula/hermes-agent) and [hermes-desktop](https://formulae.brew.sh/cask/hermes-desktop)
