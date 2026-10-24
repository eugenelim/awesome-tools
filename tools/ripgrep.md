---
type: Tool
title: ripgrep (rg)
description: Fast recursive search for a regex pattern that skips gitignored, hidden and binary files by default.
resource: https://github.com/BurntSushi/ripgrep
tags:
  - cli
  - search
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Unlicense OR MIT
pricing: Free
sources:
  - id: ripgrep
    resource: https://github.com/BurntSushi/ripgrep
    title: BurntSushi/ripgrep README and COPYING
  - id: homebrew
    resource: https://formulae.brew.sh/formula/ripgrep
    title: "Homebrew: ripgrep"
---
# ripgrep (rg)

A line-oriented search tool that recursively searches the current directory for a regex pattern. By default it respects `.gitignore` rules and skips hidden files and directories and binary files; `rg -uuu` turns that filtering off. The command is `rg`. Dual-licensed under MIT or the Unlicense.[^ripgrep]

## Install

With Homebrew:[^homebrew]

```sh
brew install ripgrep
```

## Common commands

From the README:[^ripgrep]

```sh
rg pattern            # search the current directory, recursively
rg -tpy foo           # only Python files
rg -Tjs foo           # exclude JavaScript files
rg -uuu pattern       # also search ignored, hidden and binary files
```

## See also

- [Command-line utilities](../concepts/command-line-utilities.md)
- [fd](./fd.md)

[^ripgrep]: [BurntSushi/ripgrep](https://github.com/BurntSushi/ripgrep) README and COPYING
[^homebrew]: [Homebrew: ripgrep](https://formulae.brew.sh/formula/ripgrep)
