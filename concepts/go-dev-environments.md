---
type: Guide
title: Go dev environments
description: Installing Go and managing Go versions per project with Go's built-in toolchain switching.
tags:
  - go
  - golang
  - version-manager
  - guide
sources:
  - id: toolchain
    resource: https://go.dev/doc/toolchain
    title: Go Toolchains
  - id: install
    resource: https://go.dev/doc/install
    title: Download and install Go
  - id: gopls
    resource: https://go.dev/gopls/
    title: gopls
  - id: homebrew
    resource: https://formulae.brew.sh/formula/go
    title: "Homebrew: go, gopls"
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/GoLang/Go
    title: "winget: GoLang.Go"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/golang
    title: "Chocolatey: golang"
---
# Go dev environments

## Recommendation: one Go install, no version manager

Install one recent Go and let Go's built-in **toolchain switching** handle per-project versions. Unlike Python and Node.js, Go doesn't need a separate version switcher such as uv or fnm.

- Since Go 1.21, the `go` command can use its bundled toolchain, other versions on `PATH`, or download versions as needed.[^toolchain]
- Each project's `go.mod` declares the minimum Go version (the `go` line) and can suggest a specific toolchain (the `toolchain` line).[^toolchain]
- With the default `GOTOOLCHAIN=auto`, the `go` command downloads a newer toolchain when a project asks for one.[^toolchain]
- Repackaged Go builds may change that default.[^toolchain] Homebrew's build keeps `GOTOOLCHAIN=auto`: checked on go1.27.1, it ships a `go.env` that sets it.[^homebrew] Run `go env GOTOOLCHAIN` to check yours.

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install go`[^homebrew] |
| Windows (recommended) | `winget install GoLang.Go`[^winget-pkg] |
| Windows (alternative) | `choco install golang`[^choco-pkg] |
| Any | Official installer from go.dev: `.pkg` on macOS, `.msi` on Windows, archive on Linux[^install] |

On Linux with the official archive, delete any existing `/usr/local/go` first; don't extract over an existing tree. Then add `/usr/local/go/bin` to `PATH`:[^install]

```sh
rm -rf /usr/local/go && tar -C /usr/local -xzf go<version>.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
```

## Set up `PATH` for installed tools

Tools installed with `go install` go to `$(go env GOPATH)/bin`, which defaults to `$HOME/go/bin`. Add it to `PATH`, for example in `~/.zshrc` on macOS or `~/.profile` on Linux:[^install]

```sh
export PATH="$PATH:$(go env GOPATH)/bin"
```

Then open a new terminal and check:[^install]

```sh
go version
```

## Pin a project's Go version

```sh
go mod init example.com/myapp       # creates go.mod with a go line
go get go@latest                     # require the latest released Go
go get go@1.22.1 toolchain@1.24rc1   # minimum 1.22.1, suggest go1.24rc1
go get toolchain@none                # remove the toolchain line
```

The `go get` commands are from Go's toolchain docs.[^toolchain]

## Editor support: gopls

`gopls` is Go's official language server, made by the Go team.[^gopls] Editors that use it include VS Code, [Zed](../tools/zed.md), Vim/Neovim, Emacs, Helix and Sublime Text. Some, such as VS Code, install and update it for you.[^gopls] To install it yourself:

```sh
go install golang.org/x/tools/gopls@latest
```

It's also packaged as `brew install gopls`.[^homebrew]

## See also

- [Go developer tools](./go-tools.md): golangci-lint, Delve, govulncheck and GoReleaser
- [Rust dev environments](./rust-dev-environments.md)
- [Python dev environments](./python-dev-environments.md)
- [Node.js dev environments](./node-dev-environments.md)

[^toolchain]: [Go Toolchains](https://go.dev/doc/toolchain)
[^install]: [Download and install Go](https://go.dev/doc/install)
[^gopls]: [gopls documentation](https://go.dev/gopls/)
[^homebrew]: Homebrew: [go](https://formulae.brew.sh/formula/go) and [gopls](https://formulae.brew.sh/formula/gopls); `go.env` checked on the maintainer's Mac, 2026-10-21
[^winget-pkg]: [winget: GoLang.Go](https://github.com/microsoft/winget-pkgs/tree/master/manifests/g/GoLang/Go)
[^choco-pkg]: [Chocolatey: golang](https://community.chocolatey.org/packages/golang)
