---
type: Category
title: Go developer tools
description: Linting, debugging, vulnerability scanning and release tools for Go projects.
---
# Go developer tools

Linting, debugging, vulnerability scanning and release tools for Go projects. For installing Go and the gopls language server, see [Go dev environments](./go-dev-environments.md).

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [golangci-lint](../tools/golangci-lint.md) | GPL-3.0 | `brew install golangci-lint` | `winget install GolangCI.golangci-lint` | install script from golangci-lint.run |
| [Delve](../tools/delve.md) | MIT | `brew install delve` | `go install github.com/go-delve/delve/cmd/dlv@latest` | `go install github.com/go-delve/delve/cmd/dlv@latest` |
| [govulncheck](../tools/govulncheck.md) | BSD-3-Clause | `brew install govulncheck` | `go install golang.org/x/vuln/cmd/govulncheck@latest` | `go install golang.org/x/vuln/cmd/govulncheck@latest` |
| [GoReleaser](../tools/goreleaser.md) | MIT (Pro is paid) | `brew install --cask goreleaser/tap/goreleaser` | `winget install goreleaser.goreleaser` | apt/yum repositories or snap |

Tools installed with `go install` land in `$(go env GOPATH)/bin`; add it to `PATH` as described in [Go dev environments](./go-dev-environments.md#set-up-path-for-installed-tools).
