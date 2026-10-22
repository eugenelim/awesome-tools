---
type: Tool
title: golangci-lint
description: A Go linters runner that runs linters in parallel with caching and YAML configuration, and also formats code.
resource: https://golangci-lint.run/
tags:
  - go
  - linter
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: GPL-3.0
pricing: Free
sources:
  - id: golangci-lint
    resource: https://github.com/golangci/golangci-lint
    title: golangci/golangci-lint README
  - id: install
    resource: https://golangci-lint.run/docs/welcome/install/local/
    title: golangci-lint Local Installation
  - id: quickstart
    resource: https://golangci-lint.run/docs/welcome/quick-start/
    title: golangci-lint Quick Start
  - id: packages
    resource: https://formulae.brew.sh/formula/golangci-lint
    title: "Homebrew: golangci-lint; winget: GolangCI.golangci-lint; Chocolatey: golangci-lint"
---
# golangci-lint

A Go linters runner. It runs linters in parallel, uses caching, supports YAML configuration, integrates with major IDEs and includes over a hundred linters. Licensed under GPL-3.0.[^golangci-lint] [^packages]

- **Zero configuration:** runs with a default set of linters. Use `-E`/`--enable` and `-D`/`--disable` to choose others.[^quickstart]
- **Formatting:** `golangci-lint fmt` formats code with the configured formatters.[^quickstart]
- **Paths:** directories aren't analysed recursively unless you add `/...` to the path.[^quickstart]

## Install

The project recommends a prebuilt binary. Its docs say `go install`, the "tools pattern" and `go tool` installs "aren't guaranteed to work", because they compile locally with your own Go version and dependencies. They also warn that Homebrew "can use an unexpected version of Go to build the binary", and recommend the official formula over the old tap.[^install]

| Platform | Command |
| --- | --- |
| macOS | `brew install golangci-lint` |
| Windows (recommended) | `winget install GolangCI.golangci-lint` |
| Windows (alternatives) | `choco install golangci-lint` or `scoop install main/golangci-lint` |
| Linux | `curl -sSfL https://golangci-lint.run/install.sh \| sh -s -- -b $(go env GOPATH)/bin v2.15.0` |

On Windows, the install script also runs in Git Bash. The project doesn't maintain the Scoop package.[^install] On 2026-10-21 the latest release was v2.15.0; Homebrew and winget had 2.15.0 but Chocolatey had 2.14.0.[^packages]

## Use

```sh
golangci-lint run                      # same as: golangci-lint run ./...
golangci-lint run dir1 dir2/...        # specific directories
golangci-lint run --default=none -E errcheck
golangci-lint fmt                      # format code
```

These commands are from the quick start.[^quickstart]

## See also

- [Go developer tools](../concepts/go-tools.md)
- [Go dev environments](../concepts/go-dev-environments.md)

[^golangci-lint]: [golangci/golangci-lint README](https://github.com/golangci/golangci-lint)
[^install]: [golangci-lint Local Installation](https://golangci-lint.run/docs/welcome/install/local/)
[^quickstart]: [golangci-lint Quick Start](https://golangci-lint.run/docs/welcome/quick-start/)
[^packages]: Homebrew: [golangci-lint](https://formulae.brew.sh/formula/golangci-lint); winget: [GolangCI.golangci-lint](https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/GolangCI/golangci-lint); Chocolatey: [golangci-lint](https://community.chocolatey.org/packages/golangci-lint); versions checked 2026-10-21
