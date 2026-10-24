---
type: Guide
title: Rust dev environments
description: Installing Rust with rustup, pinning a project's toolchain, and the standard components (Clippy, rustfmt, rust-analyzer).
tags:
  - rust
  - version-manager
  - guide
sources:
  - id: rustup
    resource: https://rust-lang.github.io/rustup/
    title: rustup book (installation, other installation methods, MSVC prerequisites, basics, overrides, components, profiles)
  - id: cargo
    resource: https://doc.rust-lang.org/cargo/getting-started/first-steps.html
    title: "The Cargo Book: First steps with Cargo"
  - id: clippy
    resource: https://github.com/rust-lang/rust-clippy
    title: rust-lang/rust-clippy README
  - id: rustfmt
    resource: https://github.com/rust-lang/rustfmt
    title: rust-lang/rustfmt README
  - id: rust-analyzer
    resource: https://rust-analyzer.github.io/book/rust_analyzer_binary.html
    title: rust-analyzer binary docs
  - id: homebrew
    resource: https://formulae.brew.sh/formula/rustup
    title: "Homebrew: rustup, rust"
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/r/Rustlang/Rustup
    title: "winget: Rustlang.Rustup"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/rustup.install
    title: "Chocolatey: rustup.install"
---
# Rust dev environments

## Recommendation: rustup

Install Rust with **rustup**, the official installer, and let it manage everything else. Like Go and unlike Python and Node.js, you don't need a separate version manager: rustup is the version manager.

- **Toolchains:** rustup installs `rustc`, `cargo` and the other standard tools, and switches between stable, beta, nightly and specific versions. It uses stable by default; stable gets a new release every six weeks, and `rustup update` installs it.[^rustup]
- **Per-project versions:** a `rust-toolchain.toml` file in the repository pins the project's toolchain, components and targets. rustup picks it up when you run `cargo` or `rustc` in that folder or below.[^rustup]
- **Components:** the default profile includes `rustfmt` and `clippy`. Add `rust-analyzer` and other components with `rustup component add`.[^rustup]
- **Avoid Homebrew's `rust` formula** for development. It's a Homebrew-managed toolchain, separate from rustup, so you can't switch versions or add components with it. If you also use rustup, Homebrew warns about `PATH` conflicts.[^rustup] [^homebrew]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install rustup`, then the `PATH` setup below[^homebrew] |
| Windows (recommended) | `winget install Rustlang.Rustup`, plus the MSVC build tools below[^winget-pkg] |
| Windows (alternative) | `choco install rustup.install` (1.27.1 on 2026-10-23, behind winget's 1.29.1)[^choco-pkg] |
| Any | Official script from rust-lang.org: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs \| sh`[^rustup] |

The rustup project doesn't maintain the Homebrew, winget or Chocolatey packages.[^rustup]

### macOS with Homebrew

Homebrew's `rustup` is keg-only: `rustc` and `cargo` aren't on `PATH` until you add them. Programs installed with `cargo install` go to `~/.cargo/bin`, so add that too:[^homebrew] [^rustup]

```sh
brew install rustup
# add to ~/.zshrc, then open a new terminal
export PATH="$(brew --prefix rustup)/bin:$HOME/.cargo/bin:$PATH"
rustup default stable        # install the stable toolchain and make it the default
rustc --version
```

`rustup default stable` is the setup step the rustup docs give for Homebrew.[^rustup] The official script installs everything into `~/.cargo/bin` and adds it to `PATH` for you instead.[^rustup]

### Windows: MSVC build tools

Rust on Windows needs a linker and the Windows SDK from Visual Studio. If Visual Studio isn't installed, `rustup-init` offers to install Visual Studio Community, which is free for individuals, education and open source, but not for other uses such as proprietary enterprise software. Ask your organisation which edition to use.[^rustup] Or install it with winget:[^rustup]

```powershell
winget install --id Microsoft.VisualStudio.Community --source winget --force --override "--add Microsoft.VisualStudio.Component.VC.Tools.x86.x64 --add Microsoft.VisualStudio.Component.VC.Tools.ARM64 --add Microsoft.VisualStudio.Component.Windows11SDK.22621 --addProductLang En-us"
```

If you already have a Visual Studio licence, replace `Community` with `BuildTools`.[^rustup]

## Keep it up to date

```sh
rustup update                # update installed toolchains
rustup self update           # update rustup itself
rustup show                  # which toolchain is active here
```

From the rustup docs. Packaged builds of rustup can have self-update turned off; then update rustup with the package manager instead.[^rustup]

## Pin a project's toolchain

Add `rust-toolchain.toml` at the project root:[^rustup]

```toml
[toolchain]
channel = "1.99"                     # or stable, beta, nightly, 1.99.1, nightly-2026-10-01
components = ["rustfmt", "clippy"]
```

rustup chooses the toolchain in this order: `cargo +beta`-style shorthand on the command line, the `RUSTUP_TOOLCHAIN` environment variable, a directory override (`rustup override set`), `rust-toolchain.toml`, then your default.[^rustup] To try a different toolchain once, run `cargo +beta test`.[^rustup]

## Start a project

```sh
cargo new hello_world        # binary package; --lib for a library
cd hello_world
cargo build
cargo run
```

`cargo new` creates `Cargo.toml` and `src/main.rs`.[^cargo]

## Standard components

| Component | What it does | Install | Run |
| --- | --- | --- | --- |
| rustfmt | Formats code to the Rust style guidelines[^rustfmt] | In the default profile, or `rustup component add rustfmt`[^rustup] [^rustfmt] | `cargo fmt`; `cargo fmt --check` in CI[^rustfmt] |
| Clippy | More than 800 lints for common mistakes and unidiomatic code[^clippy] | In the default profile, or `rustup component add clippy`[^rustup] [^clippy] | `cargo clippy`; `cargo clippy --fix` applies suggestions[^clippy] |
| rust-analyzer | Language server for editors | `rustup component add rust-analyzer`[^rust-analyzer] | Your editor starts it |

- **Clippy lint levels:** the `correctness` lints deny by default, and `suspicious`, `style`, `complexity` and `perf` warn. `pedantic`, `nursery`, `cargo` and `restriction` are off. Turn on `restriction` lints one at a time, never the whole group.[^clippy]
- **rustfmt config:** put settings in `rustfmt.toml` or `.rustfmt.toml` in the project. `cargo fmt` reads the edition from `Cargo.toml`.[^rustfmt]
- **rust-analyzer:** editors need the `rust-analyzer` binary on `PATH`. If your editor can't find it, it may not see the same `PATH` as your shell.[^rust-analyzer] Homebrew also has a `rust-analyzer` formula.[^homebrew]

## See also

- [Rust developer tools](./rust-tools.md): cargo-nextest, cargo-deny and cargo-audit
- [Go dev environments](./go-dev-environments.md)
- [Python dev environments](./python-dev-environments.md)
- [Node.js dev environments](./node-dev-environments.md)
- [Local machine setup](./local-machine-setup.md#rust)

[^rustup]: rustup book: [Installation](https://rust-lang.github.io/rustup/installation/index.html), [Other installation methods](https://rust-lang.github.io/rustup/installation/other.html), [MSVC prerequisites](https://rust-lang.github.io/rustup/installation/windows-msvc.html), [Basic usage](https://rust-lang.github.io/rustup/basics.html), [Overrides](https://rust-lang.github.io/rustup/overrides.html), [Components](https://rust-lang.github.io/rustup/concepts/components.html) and [Profiles](https://rust-lang.github.io/rustup/concepts/profiles.html)
[^cargo]: [The Cargo Book: First steps with Cargo](https://doc.rust-lang.org/cargo/getting-started/first-steps.html)
[^clippy]: [rust-lang/rust-clippy README](https://github.com/rust-lang/rust-clippy)
[^rustfmt]: [rust-lang/rustfmt README](https://github.com/rust-lang/rustfmt)
[^rust-analyzer]: [rust-analyzer binary docs](https://rust-analyzer.github.io/book/rust_analyzer_binary.html)
[^homebrew]: Homebrew: [rustup](https://formulae.brew.sh/formula/rustup) (keg-only; 1.29.2), [rust](https://formulae.brew.sh/formula/rust) and [rust-analyzer](https://formulae.brew.sh/formula/rust-analyzer); checked 2026-10-23
[^winget-pkg]: [winget: Rustlang.Rustup](https://github.com/microsoft/winget-pkgs/tree/master/manifests/r/Rustlang/Rustup)
[^choco-pkg]: [Chocolatey: rustup.install](https://community.chocolatey.org/packages/rustup.install)
