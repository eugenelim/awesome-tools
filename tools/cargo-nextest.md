---
type: Tool
title: cargo-nextest
description: Test runner for Rust that runs each test in its own process, up to three times faster than cargo test, with retries and JUnit output for CI.
resource: https://nexte.st/
tags:
  - rust
  - testing
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0 OR MIT
pricing: Free
sources:
  - id: nextest
    resource: https://nexte.st/
    title: nextest website, install page and README
  - id: packages
    resource: https://formulae.brew.sh/formula/cargo-nextest
    title: "Homebrew: cargo-nextest; winget: nextest.cargo-nextest"
---
# cargo-nextest

A test runner for Rust projects, run as `cargo nextest run`. The project describes it as up to three times faster than `cargo test`, with per-test isolation and first-class CI support. It can retry flaky tests, split tests across CI workers, export JUnit XML and select tests with a filter expression language. It's dual-licensed under Apache-2.0 or MIT.[^nextest]

Doctests aren't supported, because of limitations in stable Rust. Run them separately with `cargo test --doc`.[^nextest]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install cargo-nextest` |
| Windows | `winget install nextest.cargo-nextest` |
| Linux (x86_64) | `curl -LsSf https://get.nexte.st/latest/linux \| tar zxf - -C ${CARGO_HOME:-~/.cargo}/bin` |

The install docs assume Rust is managed with [rustup](../concepts/rust-dev-environments.md).[^nextest] On 2026-10-23, Homebrew had 0.9.149 and winget 0.9.148; there's no Chocolatey package.[^packages]

## Use

```sh
cargo nextest run            # run the tests
cargo test --doc             # doctests, which nextest doesn't run
```

## See also

- [Rust developer tools](../concepts/rust-tools.md)
- [Rust dev environments](../concepts/rust-dev-environments.md)

[^nextest]: [nextest website](https://nexte.st/), [pre-built binaries](https://nexte.st/docs/installation/pre-built-binaries/) and [README](https://github.com/nextest-rs/nextest)
[^packages]: Homebrew: [cargo-nextest](https://formulae.brew.sh/formula/cargo-nextest); winget: [nextest.cargo-nextest](https://github.com/microsoft/winget-pkgs/tree/master/manifests/n/nextest/cargo-nextest); checked 2026-10-23
