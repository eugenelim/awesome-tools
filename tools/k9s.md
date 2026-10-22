---
type: Tool
title: k9s
description: Terminal UI for navigating, watching and managing Kubernetes clusters.
resource: https://k9scli.io/
tags:
  - kubernetes
  - cli
  - tui
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: k9s
    resource: https://github.com/derailed/k9s
    title: derailed/k9s README
  - id: packages
    resource: https://formulae.brew.sh/formula/k9s
    title: "Homebrew: k9s; winget: Derailed.k9s; Chocolatey: k9s"
---
# k9s

A terminal UI for Kubernetes clusters. It continually watches the cluster for changes and lets you navigate, observe and manage resources from one screen. It's free, open source under Apache-2.0, and maintained by an individual developer who accepts sponsorship.[^k9s] [^packages]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install k9s`[^packages] |
| Windows (recommended) | `winget install k9s`[^k9s] |
| Windows (alternatives) | `choco install k9s` or `scoop install k9s`[^k9s] |

The README's macOS example uses the project's tap (`brew install derailed/k9s/k9s`); the `k9s` formula in homebrew-core had the same version.[^k9s] [^packages] All three package managers had 0.51.0 on 2026-10-21.[^packages]

## Use

```sh
k9s                # start in your current kubectl context
k9s -n mycoolns    # start in a given namespace
```

Quit with `:quit`, `:q` or `Ctrl-C`.[^k9s]

## See also

- [Containers and Kubernetes](../concepts/containers.md)
- [kubectl](./kubectl.md)

[^k9s]: [derailed/k9s README](https://github.com/derailed/k9s)
[^packages]: Homebrew: [k9s](https://formulae.brew.sh/formula/k9s); winget: [Derailed.k9s](https://github.com/microsoft/winget-pkgs/tree/master/manifests/d/Derailed/k9s); Chocolatey: [k9s](https://community.chocolatey.org/packages/k9s); versions checked 2026-10-21
