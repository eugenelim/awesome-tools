---
type: Tool
title: govulncheck
description: The Go project's tool that reports known vulnerabilities affecting Go source code or binaries, using the Go vulnerability database.
resource: https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck
tags:
  - go
  - security
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: BSD-3-Clause
pricing: Free
sources:
  - id: vuln
    resource: https://github.com/golang/vuln
    title: golang/vuln README
  - id: doc
    resource: https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck
    title: govulncheck command documentation
  - id: packages
    resource: https://formulae.brew.sh/formula/govulncheck
    title: "Homebrew: govulncheck; Go module proxy: golang.org/x/vuln"
---
# govulncheck

Reports known vulnerabilities that affect Go code. It analyses source code, or a binary's symbol table, to narrow reports to vulnerabilities your code could actually reach.[^doc] It's backed by the Go vulnerability database, curated by the Go security team. The code is BSD-3-Clause; database entries at vuln.go.dev are CC-BY 4.0.[^vuln]

- **Source mode:** `govulncheck ./...` in a module. Findings include a call stack showing how your code reaches the vulnerable function.[^doc]
- **Binary mode:** `-mode binary` checks a compiled binary, without call stacks.[^doc]
- **Network:** by default it queries vuln.go.dev, sending only module paths already in the database, not your code. `-db` picks another database.[^doc]
- **Output:** JSON, SARIF and OpenVEX. It exits non-zero when it finds vulnerabilities, except in those formats.[^doc]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install govulncheck` |
| Windows | `go install golang.org/x/vuln/cmd/govulncheck@latest` |
| Linux | `go install golang.org/x/vuln/cmd/govulncheck@latest` |

The `go install` command is the documented install.[^vuln] On 2026-10-21 the Go module proxy and Homebrew both had v1.9.0. The GitHub releases page is out of date, so check the module proxy for the current version. There's no winget or Chocolatey package.[^packages]

## Use

```sh
govulncheck ./...
govulncheck -show traces ./...
govulncheck -mode binary $HOME/go/bin/my-go-program
```

## See also

- [Go developer tools](../concepts/go-tools.md)
- [Go dev environments](../concepts/go-dev-environments.md)

[^vuln]: [golang/vuln README](https://github.com/golang/vuln)
[^doc]: [govulncheck command documentation](https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck)
[^packages]: Homebrew: [govulncheck](https://formulae.brew.sh/formula/govulncheck); Go module proxy: [golang.org/x/vuln @latest](https://proxy.golang.org/golang.org/x/vuln/@latest); versions checked 2026-10-21
