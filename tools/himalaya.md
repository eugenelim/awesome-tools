---
type: Tool
title: Himalaya
description: A command-line email client written in Rust, for IMAP, SMTP, JMAP, Gmail and Microsoft Graph accounts.
resource: https://pimalaya.org/
tags:
  - email
  - cli
  - rust
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT OR Apache-2.0
pricing: Free
sources:
  - id: himalaya
    resource: https://github.com/pimalaya/himalaya/blob/v2.2.1/README.md
    title: pimalaya/himalaya README (v2.2.1)
  - id: releases
    resource: https://github.com/pimalaya/himalaya/releases/tag/v2.2.1
    title: pimalaya/himalaya v2.2.1 release
  - id: packages
    resource: https://formulae.brew.sh/formula/himalaya
    title: "Homebrew: himalaya; Chocolatey: himalaya; Scoop: himalaya"
---
# Himalaya

A command-line tool for managing email, written in Rust, from the Pimalaya project. It's dual-licensed under MIT or Apache-2.0, at your option.[^himalaya]

- **Protocols:** IMAP, SMTP, ManageSieve, JMAP, the Gmail REST API and Microsoft Graph (Outlook and Microsoft 365). Local mailboxes in Maildir, m2dir, mbox and pimdir format.[^himalaya]
- **Accounts:** several accounts in one TOML config file. Without a config file, `himalaya` starts a wizard that asks for your email address, discovers the servers for its domain, and prints the account as TOML.[^himalaya]
- **Scripting:** `--json` gives JSON output.[^himalaya]
- **Secrets:** every password or token field takes a literal or a shell command that prints the secret, such as `pass show gmail`. Version 2 removed built-in keyring support, so use a keyring CLI (`pass`, `secret-tool`, `gopass`) as the command.[^himalaya]
- **OAuth 2.0:** version 2 has no built-in OAuth flow. Get the access token from a broker such as ortie and supply it as a command.[^himalaya]
- **Funding:** grants from NLnet and the European Commission's NGI programmes, plus donations.[^himalaya]

## Gmail and Outlook

Gmail rejects your account password over IMAP and SMTP; generate an app password, which needs 2-step verification. Or use Gmail's REST API with an OAuth token.[^himalaya]

Microsoft has retired basic authentication for Outlook, so you need an OAuth 2.0 token from a broker, over IMAP and SMTP (`xoauth2` or `oauthbearer`) or the Microsoft Graph API. With Graph, sending also goes through Graph, so no SMTP is needed.[^himalaya]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install himalaya` |
| Windows | `scoop install himalaya`, or `choco install himalaya` |
| Linux (Arch) | `pacman -S himalaya` |
| Linux (Fedora/RHEL) | `dnf copr enable atim/himalaya`, then `dnf install himalaya` |
| macOS or Linux | `curl -sSL https://raw.githubusercontent.com/pimalaya/himalaya/master/install.sh \| PREFIX=~/.local sh` |
| Any (Rust 1.89+) | `cargo install --locked --git https://github.com/pimalaya/himalaya.git` |
| Any (Nix) | `nix profile install github:pimalaya/himalaya` |

The install script downloads a pre-built binary; drop `PREFIX=~/.local` and pipe to `sudo sh` to install for all users.[^himalaya] Release binaries cover macOS (Apple silicon and Intel), Windows x86-64 and Linux (x86-64, ARM and i686).[^releases]

On 2026-10-21, Homebrew, Chocolatey and Scoop all had 2.2.1, the latest release (2026-10-02). There's no winget package. The Chocolatey package's project URL points at pimalaya/himalaya.[^packages] [^releases]

## Use

```sh
himalaya                      # first run: account wizard
himalaya account check        # validate configured accounts
himalaya mailbox list
himalaya envelope list --page 2
himalaya envelope search from alice and after 2026-01-01 order by date desc
himalaya message read 42
himalaya attachment download 42
```

The config file is `$XDG_CONFIG_HOME/himalaya/config.toml`, then `~/.config/himalaya/config.toml`, then `~/.himalayarc`; `-c <PATH>` overrides it. To add an account, run the wizard again and merge its output into the file; there's no edit subcommand.[^himalaya]

## See also

- [Email clients](../concepts/email-clients.md)

[^himalaya]: [pimalaya/himalaya README (v2.2.1)](https://github.com/pimalaya/himalaya/blob/v2.2.1/README.md)
[^releases]: [pimalaya/himalaya v2.2.1 release](https://github.com/pimalaya/himalaya/releases/tag/v2.2.1)
[^packages]: Homebrew: [himalaya](https://formulae.brew.sh/formula/himalaya); Chocolatey: [himalaya](https://community.chocolatey.org/packages/himalaya); Scoop: [himalaya](https://github.com/ScoopInstaller/Main/blob/master/bucket/himalaya.json); versions checked 2026-10-21
