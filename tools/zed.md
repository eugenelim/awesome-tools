---
type: Tool
title: Zed
description: High-performance, multiplayer, open-source code editor from the creators of Atom and Tree-sitter.
resource: https://zed.dev/
tags:
  - code-editor
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: GPL-3.0-or-later (Apache-2.0 components where marked)
sources:
  - id: zed
    resource: /sources/zed-homepage.md
    title: Zed homepage
  - id: zed-readme
    resource: /sources/zed-github-readme.md
    title: zed-industries/zed README
  - id: zed-install
    resource: /sources/zed-installation-docs.md
    title: Installing Zed
  - id: homebrew
    resource: /sources/homebrew-api-zed-pi.md
    title: Homebrew API snapshot (Zed and Pi)
---
# Zed

A high-performance, multiplayer code editor from the creators of Atom and Tree-sitter.[^zed-readme] It describes itself as "open source" with "AI optional".[^zed] It is developed by Zed Industries, Inc., a for-profit company.[^zed-readme]

## Related projects

Zed Industries also develops these:[^zed]

- Agent Client Protocol: "Connect any client to any agent."
- GPUI: a GPU-accelerated UI framework for Rust.
- Tree-sitter: incremental parsing for programming languages.
- Delta: a multiplayer environment for coding with agents, powered by DeltaDB.

## Platforms

- macOS 12 or later on Intel or Apple silicon, with partial support for macOS 10.15 and 11.[^zed-install]
- Windows 10 (1903+) and Windows 11 (22H2+), 64-bit.[^zed-install]
- Linux on x86_64 and aarch64; requires a Vulkan 1.3 driver.[^zed-install]
- No web version yet.[^zed-readme]

## Licence

GPL-3.0-or-later, with Apache-2.0 components where marked.[^zed-readme]

## Install

```sh
brew install --cask zed
```

For the preview build, use `brew install --cask zed@preview`.[^zed-install] [^homebrew] On Windows, run `winget install -e --id ZedIndustries.Zed`. On Linux, run `curl -f https://zed.dev/install.sh | sh`.[^zed-install]

## See also

- [Code editors](../concepts/code-editors.md)

[^zed]: [Zed homepage](../sources/zed-homepage.md)
[^zed-readme]: [zed-industries/zed README](../sources/zed-github-readme.md)
[^zed-install]: [Installing Zed](../sources/zed-installation-docs.md)
[^homebrew]: [Homebrew API snapshot (Zed and Pi)](../sources/homebrew-api-zed-pi.md)
