---
type: Category
title: Rust developer tools
description: Formatting, linting, editor support, testing and dependency checks for Rust projects.
---
# Rust developer tools

Formatting, linting, editor support, testing and dependency checks for Rust projects. For installing Rust with rustup, see [Rust dev environments](./rust-dev-environments.md).

## rustup components

rustfmt and Clippy come with the default rustup profile; add rust-analyzer yourself. See [standard components](./rust-dev-environments.md#standard-components).

| Component | Purpose | Install |
| --- | --- | --- |
| rustfmt | Formatter (`cargo fmt`) | default profile |
| Clippy | Linter (`cargo clippy`) | default profile |
| rust-analyzer | Language server | `rustup component add rust-analyzer` |

## Cargo plugins

| Tool | Purpose | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- | --- |
| [cargo-nextest](../tools/cargo-nextest.md) | Faster test runner, with retries and JUnit output | Apache-2.0 OR MIT | `brew install cargo-nextest` | `winget install nextest.cargo-nextest` | pre-built binary |
| [cargo-deny](../tools/cargo-deny.md) | Advisories, licences, banned crates and sources | Apache-2.0 OR MIT | `brew install cargo-deny` | `cargo install --locked cargo-deny` | `cargo install --locked cargo-deny` |
| [cargo-audit](../tools/cargo-audit.md) | RustSec advisories only | Apache-2.0 OR MIT | `brew install cargo-audit` | `cargo install cargo-audit` | `cargo install cargo-audit` |

Both cargo-deny and cargo-audit check crates against an advisory database; cargo-deny also checks licences, banned crates and sources. Programs installed with `cargo install` go to `~/.cargo/bin` (`%USERPROFILE%\.cargo\bin` on Windows); see [Rust dev environments](./rust-dev-environments.md#macos-with-homebrew) for `PATH`.
