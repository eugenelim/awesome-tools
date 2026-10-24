---
type: Tool
title: cargo-audit
description: RustSec's Cargo subcommand that checks Cargo.lock for crates with vulnerabilities reported to the RustSec Advisory Database.
resource: https://github.com/rustsec/rustsec/tree/main/cargo-audit
tags:
  - rust
  - security
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0 OR MIT
pricing: Free
sources:
  - id: audit
    resource: https://github.com/rustsec/rustsec/tree/main/cargo-audit
    title: rustsec/rustsec cargo-audit README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/cargo-audit
    title: "Homebrew: cargo-audit"
---
# cargo-audit

Audits your dependencies for crates with security vulnerabilities reported to the RustSec Advisory Database. It needs Rust 1.74 or later and is licensed under Apache-2.0 or MIT.[^audit] [cargo-deny](./cargo-deny.md)'s advisories check covers the same ground, alongside licence and source checks.

**Only run it on projects you trust.** If `Cargo.lock` is missing, it runs `cargo update --workspace` to create one, and Cargo can run code from the project. To audit a project you don't trust, pass its lockfile with `--file` and run it from outside the project.[^audit]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install cargo-audit` |
| Windows | `cargo install cargo-audit` |
| Linux | `cargo install cargo-audit`, or your distribution's package (Alpine, Arch) |

From the README.[^audit] Homebrew had 0.22.2 on 2026-10-23.[^homebrew] There's no winget or Chocolatey package.

## Use

From the README:[^audit]

```sh
cargo audit                              # in the project's top folder
cargo audit --file path/to/Cargo.lock    # a project you don't trust
cargo audit bin path/to/binary           # a compiled binary
cargo audit --ignore RUSTSEC-2017-0001   # skip an advisory that doesn't apply
```

`cargo audit fix`, which updates vulnerable requirements in `Cargo.toml`, is experimental and needs `cargo install cargo-audit --features=fix`.[^audit]

## See also

- [Rust developer tools](../concepts/rust-tools.md)
- [cargo-deny](./cargo-deny.md)

[^audit]: [rustsec/rustsec cargo-audit README](https://github.com/rustsec/rustsec/tree/main/cargo-audit)
[^homebrew]: [Homebrew: cargo-audit](https://formulae.brew.sh/formula/cargo-audit); no winget or Chocolatey package found, 2026-10-23
