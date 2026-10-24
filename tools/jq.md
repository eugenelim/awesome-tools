---
type: Tool
title: jq
description: Lightweight command-line JSON processor for slicing, filtering, mapping and transforming JSON.
resource: https://jqlang.org/
tags:
  - cli
  - json
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: jq
    resource: https://github.com/jqlang/jq
    title: jqlang/jq README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/jq
    title: "Homebrew: jq"
---
# jq

A lightweight, flexible command-line JSON processor, like `sed`, `awk` and `grep` for JSON. It's written in portable C with no runtime dependencies, and lets you slice, filter, map and transform structured data. Documentation and an online playground are at jqlang.org.[^jq]

## Install

```sh
brew install jq
```

Homebrew has version 1.8.2.[^homebrew] The project also publishes standalone binaries on its GitHub releases page and a Docker image.[^jq]

## Common commands

Read one field from a file, adapted from the README's Docker example:[^jq]

```sh
jq '.version' package.json
```

## See also

- [Command-line utilities](../concepts/command-line-utilities.md)

[^jq]: [jqlang/jq README](https://github.com/jqlang/jq)
[^homebrew]: [Homebrew: jq](https://formulae.brew.sh/formula/jq)
