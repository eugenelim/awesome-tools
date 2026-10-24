---
type: Tool
title: cargo-deny
description: Cargo plugin that checks a Rust project's dependencies for security advisories, unacceptable licences, banned or duplicate crates and untrusted sources.
resource: https://github.com/EmbarkStudios/cargo-deny
tags:
  - rust
  - security
  - licensing
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0 OR MIT
pricing: Free
sources:
  - id: deny
    resource: https://github.com/EmbarkStudios/cargo-deny
    title: EmbarkStudios/cargo-deny README
  - id: homebrew
    resource: https://formulae.brew.sh/formula/cargo-deny
    title: "Homebrew: cargo-deny"
---
# cargo-deny

A Cargo plugin from Embark Studios for linting your dependencies. It's dual-licensed under Apache-2.0 or MIT.[^deny] It runs four checks:[^deny]

- **Advisories:** crates with issues in an advisory database.
- **Licences:** every crate's licence terms are ones you've accepted.
- **Bans:** denies or allows specific crates, and finds several versions of the same crate.
- **Sources:** crates only come from sources you trust.

The project says its output isn't legal advice.[^deny] There's also a GitHub Action, `cargo-deny-action`, and a pre-commit hook.[^deny]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install cargo-deny` |
| Windows | `cargo install --locked cargo-deny` |
| Linux | `cargo install --locked cargo-deny` |

`cargo install --locked` is the documented install.[^deny] Homebrew had 0.20.2 on 2026-10-23.[^homebrew] There's no winget or Chocolatey package.

## Use

From the README:[^deny]

```sh
cargo deny init              # create deny.toml
cargo deny check             # run all checks
cargo deny check licenses    # or one check: licenses, bans, advisories, sources
```

## See also

- [Rust developer tools](../concepts/rust-tools.md)
- [cargo-audit](./cargo-audit.md)

[^deny]: [EmbarkStudios/cargo-deny README](https://github.com/EmbarkStudios/cargo-deny)
[^homebrew]: [Homebrew: cargo-deny](https://formulae.brew.sh/formula/cargo-deny); no winget or Chocolatey package found, 2026-10-23
