---
type: Tool
title: fd
description: Simple, fast alternative to find, with smart case and gitignore-aware defaults.
resource: https://github.com/sharkdp/fd
tags:
  - cli
  - search
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0 OR MIT
pricing: Free
sources:
  - id: fd
    resource: https://github.com/sharkdp/fd
    title: sharkdp/fd README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/fd
    title: "Homebrew: fd"
---
# fd

A program to find entries in your filesystem: a simple, fast alternative to `find` with opinionated defaults. You write `fd PATTERN` instead of `find -iname '*PATTERN*'`. Patterns are regular expressions by default, and globs are also supported. Searches are case-insensitive unless the pattern contains an uppercase letter. Hidden files and `.gitignore` matches are skipped by default.[^fd]

## Install

```sh
brew install fd
```

Homebrew lists the licence as Apache-2.0 or MIT.[^homebrew]

## Common commands

From the README:[^fd]

```sh
fd netfl              # entries whose name contains "netfl", recursively
fd '^x.*rc$' /etc     # regex search in a given directory
fd -H pre-commit      # include hidden files
fd -I pattern         # include files matched by .gitignore
fd -e zip -x unzip    # run a command for each result (in parallel)
fd -e cpp -e h -X rg 'std::cout'  # run one command with all results
```

## See also

- [Command-line utilities](../concepts/command-line-utilities.md)
- [ripgrep](./ripgrep.md)

[^fd]: [sharkdp/fd README](https://github.com/sharkdp/fd)
[^homebrew]: [Homebrew: fd](https://formulae.brew.sh/formula/fd)
