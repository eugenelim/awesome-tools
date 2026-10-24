---
type: Tool
title: tree
description: Shows the contents of directories as an indented tree, with optional colour, HTML, XML and JSON output.
resource: https://oldmanprogrammer.net/source.php?dir=projects/tree
tags:
  - cli
  - files
  - open-source
platforms:
  - macOS
  - Linux
license: GPL-2.0-or-later
pricing: Free
sources:
  - id: tree
    resource: https://oldmanprogrammer.net/source.php?dir=projects/tree
    title: tree project page and README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/tree
    title: "Homebrew: tree"
---
# tree

A small utility that shows directories as a tree. It can also output HTML (`-H`), XML and JSON, limit the depth (`-L`) and skip files matched by `.gitignore` (`--gitignore`). The current version is 2.3.2, under GPLv2.[^tree]

## Install

```sh
brew install tree
```

Homebrew lists the licence as GPL-2.0-or-later.[^homebrew]

## Common commands

Using options named in the README:[^tree]

```sh
tree -L 2             # two levels deep
tree --gitignore      # skip files matched by .gitignore
```

## See also

- [Command-line utilities](../concepts/command-line-utilities.md)

[^tree]: [tree project page](https://oldmanprogrammer.net/source.php?dir=projects/tree) and README
[^homebrew]: [Homebrew: tree](https://formulae.brew.sh/formula/tree)
