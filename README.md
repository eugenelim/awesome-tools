---
type: Readme
title: Awesome tools
description: How to use and contribute to this OKF bundle of local machine setup tools.
---
# Awesome tools

A catalogue of software tools for setting up a developer machine on macOS and Windows. Each tool has its own page covering what it does, which platforms it runs on, its licence and pricing, and how to install it.

The repo is an [Open Knowledge Format](https://github.com/GoogleCloudPlatform/open-knowledge-format) (OKF) v0.2 bundle: plain Markdown files with YAML frontmatter, joined by ordinary relative links.

## Start here

- [index.md](./index.md): every page in the bundle.
- [Local machine setup](./concepts/local-machine-setup.md): all tools in one table, plus Homebrew and Windows install commands.
- [Python dev environments](./concepts/python-dev-environments.md): uv vs pyenv.
- [Node.js dev environments](./concepts/node-dev-environments.md): fnm, mise, nvm and Volta.

## Tools by category

| Category | Tools |
| --- | --- |
| [AI coding agents](./concepts/ai-coding-agents.md) | [Claude Code](./tools/claude-code.md), [Codex](./tools/codex.md), [GitHub Copilot CLI](./tools/github-copilot.md), [Pi](./tools/pi.md) |
| [Agentic development environments](./concepts/agentic-development-environments.md) | [Antigravity](./tools/antigravity.md), [herdr](./tools/herdr.md), [Orca](./tools/orca.md), [VelaTerm](./tools/velaterm.md) |
| [Code editors](./concepts/code-editors.md) | [Zed](./tools/zed.md) |
| [Terminal emulators](./concepts/terminal-emulators.md) | [Ghostty](./tools/ghostty.md) |
| [Web browsers](./concepts/web-browsers.md) | [Firefox Developer Edition](./tools/firefox-developer-edition.md) |
| [Knowledge management](./concepts/knowledge-management.md) | [Logseq](./tools/logseq.md), [Obsidian](./tools/obsidian.md), [Octarine](./tools/octarine.md), [OpenKnowledge](./tools/openknowledge.md), [SilverBullet](./tools/silverbullet.md) |
| [Ontology editors](./concepts/ontology-editors.md) | [Protégé](./tools/protege.md), [VocBench](./tools/vocbench.md) |
| [Design tools](./concepts/design-tools.md) | [Paper](./tools/paper.md) |
| [Personal AI agents](./concepts/personal-ai-agents.md) | [Hermes Agent](./tools/hermes.md), [Muse](./tools/muse.md) |
| [Password managers](./concepts/password-managers.md) | [Bitwarden](./tools/bitwarden.md) |
| [File managers](./concepts/file-managers.md) | [Rascal](./tools/rascal.md), [Swift Salamander](./tools/swift-salamander.md) |
| [macOS utilities](./concepts/macos-utilities.md) | [Wick](./tools/wick.md) |
| [Windows platform tools](./concepts/windows-platform-tools.md) | [Chocolatey](./tools/chocolatey.md), [WSL](./tools/wsl.md) |

## Using the bundle

- **On GitHub:** start from this page or `index.md` and follow the links.
- **Locally:** clone the repo and open the folder in any Markdown editor or OKF-aware tool.

```sh
git clone https://github.com/eugenelim/awesome-tools.git
```

- **With an agent:** point it at `index.md`. Every page has a `type` and a one-line `description` in its frontmatter.

## Layout

```text
index.md       OKF root index (okf_version: "0.2")
concepts/      categories (type: Category), guides (type: Guide), overview (type: Overview)
tools/         one page per tool (type: Tool)
```

## Tool page format

```yaml
---
type: Tool
title: Ghostty
description: Fast, feature-rich, native terminal emulator for macOS and Linux.
resource: https://ghostty.org/
tags: [terminal, macos, linux]
platforms: [macOS, Linux]
# license / pricing: added only when the source states them
sources:
  - id: ghostty
    resource: /sources/ghostty-about.md
    title: Ghostty Docs and About Ghostty
---
```

The body has a summary, features, platforms, pricing where known, and an **Install** section with the Homebrew command, or a note when there isn't one. Claims are cited with footnotes whose labels match `sources[].id`.

## Sources

Every claim is taken from a snapshot of the vendor's own page or README, saved under `sources/`. That folder is listed in `.gitignore` and is not published, so citation links to `sources/` won't resolve on GitHub. Each tool's `resource` field links to the vendor site.

Facts were captured in October 2026. Prices, versions and platform support change, so check the vendor site before you rely on them.

## Adding a tool

1. Save the vendor page or README as a snapshot in `sources/<slug>.md` (`type: Source`, `resource:` the URL, `retrieved:` an ISO 8601 timestamp).
2. Create `tools/<slug>.md` in the format above. Leave out any field the source doesn't support.
3. Add the tool to its category page, the [overview](./concepts/local-machine-setup.md), [index.md](./index.md) and the table in this README.
4. Check Homebrew with `brew info --cask <name>` or `brew info <name>`. Watch for name collisions: `orca` and `copilot` are unrelated packages.

## Licence

This repo has no licence file yet.
