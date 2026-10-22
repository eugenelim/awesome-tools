---
type: Tool
title: Delve
description: A debugger for Go, run as the dlv command and used by editors through the Debug Adapter Protocol.
resource: https://github.com/go-delve/delve
tags:
  - go
  - debugger
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: delve
    resource: https://github.com/go-delve/delve
    title: go-delve/delve README
  - id: install
    resource: https://github.com/go-delve/delve/tree/master/Documentation/installation
    title: Delve installation
  - id: usage
    resource: https://github.com/go-delve/delve/blob/master/Documentation/usage/dlv.md
    title: dlv command-line options
  - id: editors
    resource: https://github.com/go-delve/delve/blob/master/Documentation/EditorIntegration.md
    title: Delve editor integration
  - id: packages
    resource: https://formulae.brew.sh/formula/delve
    title: "Homebrew: delve"
---
# Delve

A debugger for Go. Licensed under MIT.[^delve]

- **Subcommands:** `dlv debug` compiles and debugs a main package, `dlv test` debugs a test binary, `dlv exec` runs a prebuilt binary, `dlv attach` attaches to a running process and `dlv core` examines a core dump.[^usage]
- **Editors:** `dlv dap` starts a headless Debug Adapter Protocol server. The project lists integrations for VS Code (the Go extension), GoLand, Vim/Neovim and Emacs.[^usage] [^editors]
- **Releases:** prebuilt binaries for Linux, macOS and Windows are on GitHub Releases, with cosign-signed checksums.[^install]

## Install

The documented install is `go install github.com/go-delve/delve/cmd/dlv@latest` (Go 1.16 or later). On macOS you also need the command line developer tools (`xcode-select --install`).[^install]

| Platform | Command |
| --- | --- |
| macOS | `brew install delve` |
| Windows | `go install github.com/go-delve/delve/cmd/dlv@latest` |
| Linux | `go install github.com/go-delve/delve/cmd/dlv@latest` |

On 2026-10-21 the latest release was v1.27.2, and Homebrew had the same. There's no winget or Chocolatey package.[^packages]

## Use

```sh
dlv debug github.com/me/foo/cmd/foo -- -arg1 value
dlv test github.com/me/foo/pkg/baz
dlv attach <pid>
```

## See also

- [Go developer tools](../concepts/go-tools.md)
- [Go dev environments](../concepts/go-dev-environments.md)

[^delve]: [go-delve/delve README](https://github.com/go-delve/delve)
[^install]: [Delve installation](https://github.com/go-delve/delve/tree/master/Documentation/installation)
[^usage]: [dlv command-line options](https://github.com/go-delve/delve/blob/master/Documentation/usage/dlv.md)
[^editors]: [Delve editor integration](https://github.com/go-delve/delve/blob/master/Documentation/EditorIntegration.md)
[^packages]: Homebrew: [delve](https://formulae.brew.sh/formula/delve); [go-delve/delve releases](https://github.com/go-delve/delve/releases); versions checked 2026-10-21
