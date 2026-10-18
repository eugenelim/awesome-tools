---
type: Tool
title: GitHub Copilot CLI
description: GitHub Copilot's coding agent in the terminal, integrated with GitHub repositories, issues and pull requests.
resource: https://github.com/github/copilot-cli
tags:
  - ai-agents
  - cli
  - github
platforms:
  - macOS
  - Linux
  - Windows
pricing: Requires a Copilot subscription
sources:
  - id: copilot
    resource: https://github.com/github/copilot-cli
    title: github/copilot-cli README
  - id: homebrew
    resource: https://formulae.brew.sh/cask/copilot-cli
    title: "Homebrew: copilot-cli"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/github-copilot-cli
    title: "Chocolatey: github-copilot-cli"
---
# GitHub Copilot CLI

Brings GitHub Copilot's coding agent to the terminal. It uses the same agent harness as GitHub's Copilot coding agent.[^copilot]

## Features

From the README:[^copilot]

- Access to your repositories, issues and pull requests using your GitHub account.
- Can build, edit, debug and refactor code, and plan multi-step tasks.
- Ships with GitHub's MCP server and supports custom MCP servers.
- Every action is previewed and needs your approval.

Requires an active Copilot subscription. Organisation or enterprise admins can disable it.[^copilot]

## Install

```sh
brew install copilot-cli
```

`copilot-cli@prerelease` installs prereleases.[^copilot] Don't use `brew install copilot`: that formula is AWS's CLI for Amazon ECS and Fargate.[^homebrew] Other options are the install script (`curl -fsSL https://gh.io/copilot-install | bash`), `winget install GitHub.Copilot` on Windows, or `npm install -g @github/copilot`. Run `copilot` to start and `/login` to authenticate.[^copilot]

On Windows with [Chocolatey](./chocolatey.md):[^choco-pkg]

```powershell
choco install github-copilot-cli
```

## See also

- [AI coding agents](../concepts/ai-coding-agents.md)

[^copilot]: [github/copilot-cli README](https://github.com/github/copilot-cli)
[^homebrew]: [Homebrew: copilot-cli](https://formulae.brew.sh/cask/copilot-cli) and the unrelated [copilot](https://formulae.brew.sh/formula/copilot) formula

[^choco-pkg]: [Chocolatey: github-copilot-cli](https://community.chocolatey.org/packages/github-copilot-cli)
