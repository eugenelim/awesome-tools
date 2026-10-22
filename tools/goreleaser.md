---
type: Tool
title: GoReleaser
description: Release automation that builds, archives, packages, signs and publishes artifacts from a YAML configuration file.
resource: https://goreleaser.com/
tags:
  - go
  - release
  - ci
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Freemium
sources:
  - id: intro
    resource: https://goreleaser.com/getting-started/intro/
    title: GoReleaser Introduction
  - id: goreleaser
    resource: https://github.com/goreleaser/goreleaser
    title: goreleaser/goreleaser repository
  - id: pro
    resource: https://goreleaser.com/pro/
    title: GoReleaser Pro
  - id: install
    resource: https://goreleaser.com/getting-started/install/oss/
    title: Install GoReleaser
  - id: quickstart
    resource: https://goreleaser.com/getting-started/quick-start/
    title: GoReleaser Quick Start
  - id: packages
    resource: https://formulae.brew.sh/formula/goreleaser
    title: "Homebrew: goreleaser; winget: goreleaser.goreleaser; Chocolatey: goreleaser"
---
# GoReleaser

Release automation: you write a YAML configuration file and one command builds, archives, packages, signs and publishes your artifacts. It supports Go, Rust, Zig, JavaScript and TypeScript (Node.js, Bun and Deno) and Python.[^intro] The open-source edition is MIT-licensed.[^goreleaser]

- **Supply chain:** signed checksums, a software bill of materials and reproducible binaries.[^intro]
- **CI:** made to run in CI; you download and run it in your build script.[^intro]
- **GoReleaser Pro** is "a paid, closed-source GoReleaser distribution": a separate binary, activated with a licence key. Its extras include macOS `.pkg`/`.dmg` and Windows NSIS/MSI installers, npm publishing, monorepo support, nightly builds and split/merge builds.[^pro]

## Install

The docs list the project's own Homebrew tap first and mark the homebrew-core formula and the Chocolatey package as "Community Owned". They warn the homebrew-core formula "might be slightly outdated".[^install]

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask goreleaser/tap/goreleaser` or `brew install goreleaser` |
| Windows (recommended) | `winget install goreleaser.goreleaser` |
| Windows (alternatives) | `choco install goreleaser`, or Scoop from the project's bucket |
| Linux | the project's apt/yum repositories, `sudo snap install --classic goreleaser`, or `go install github.com/goreleaser/goreleaser/v2@latest` |

The install commands are from the docs.[^install] On 2026-10-21 the latest release was v2.18.3, and the homebrew-core formula, winget and Chocolatey all had it. Pro is a separate winget package, `goreleaser.goreleaser-pro`.[^packages]

## Use

```sh
goreleaser init                          # write a starter .goreleaser.yaml
goreleaser check                         # validate the config
goreleaser release --snapshot --clean    # local test release, nothing published
goreleaser build --single-target --clean # build for the current platform only
```

These commands are from the quick start.[^quickstart]

## See also

- [Go developer tools](../concepts/go-tools.md)
- [Go dev environments](../concepts/go-dev-environments.md)

[^intro]: [GoReleaser Introduction](https://goreleaser.com/getting-started/intro/)
[^goreleaser]: [goreleaser/goreleaser repository](https://github.com/goreleaser/goreleaser)
[^pro]: [GoReleaser Pro](https://goreleaser.com/pro/)
[^install]: [Install GoReleaser](https://goreleaser.com/getting-started/install/oss/)
[^quickstart]: [GoReleaser Quick Start](https://goreleaser.com/getting-started/quick-start/)
[^packages]: Homebrew: [goreleaser](https://formulae.brew.sh/formula/goreleaser); winget: [goreleaser.goreleaser](https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/goreleaser/goreleaser); Chocolatey: [goreleaser](https://community.chocolatey.org/packages/goreleaser); versions checked 2026-10-21
