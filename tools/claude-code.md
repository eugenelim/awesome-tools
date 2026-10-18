---
type: Tool
title: Claude Code
description: Anthropic's agentic coding tool for the terminal, IDEs, web and Slack.
resource: https://claude.com/product/claude-code
tags:
  - ai-agents
  - cli
platforms:
  - macOS
  - Linux
  - Windows
sources:
  - id: claude-code
    resource: /sources/claude-code-github-readme.md
    title: anthropics/claude-code README and product page
  - id: homebrew
    resource: /sources/homebrew-api-agents.md
    title: Homebrew API snapshot (coding agents)
---
# Claude Code

Anthropic's agentic coding tool. It works on your codebase from the terminal: it edits files, runs commands, explains code and handles git workflows from natural-language instructions.[^claude-code]

## Features

From the README and product page:[^claude-code]

- Available in the terminal, VS Code, JetBrains IDEs, the web, iOS, Android and Slack, and by tagging @claude on GitHub.
- Supports plugins for custom commands and agents.
- Collects usage feedback (code acceptance or rejection, conversation data, `/bug` reports), as described in Anthropic's data-usage policy.

## Install

```sh
brew install --cask claude-code
```

`claude-code@latest` tracks newer releases.[^homebrew] Other options: `curl -fsSL https://claude.ai/install.sh | bash`, the recommended method on macOS and Linux, or `winget install Anthropic.ClaudeCode` on Windows. The npm package is deprecated. Run `claude` in a project directory to start.[^claude-code]

## See also

- [AI coding agents](../concepts/ai-coding-agents.md)

[^claude-code]: [anthropics/claude-code README and product page](../sources/claude-code-github-readme.md)
[^homebrew]: [Homebrew API snapshot (coding agents)](../sources/homebrew-api-agents.md)
