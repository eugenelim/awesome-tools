---
type: Tool
title: Bitwarden
description: Open-source, end-to-end encrypted password manager for individuals, families and businesses.
resource: https://bitwarden.com/
tags:
  - password-manager
  - security
  - open-source
license: Open source
sources:
  - id: bitwarden
    resource: https://bitwarden.com/
    title: Bitwarden homepage
  - id: homebrew
    resource: https://formulae.brew.sh/cask/bitwarden
    title: "Homebrew: bitwarden"
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/b/Bitwarden/Bitwarden
    title: "winget: Bitwarden.Bitwarden"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/bitwarden
    title: "Chocolatey: bitwarden"
  - id: cli
    resource: https://bitwarden.com/help/cli/
    title: Bitwarden CLI documentation
  - id: homebrew-cli
    resource: https://formulae.brew.sh/formula/bitwarden-cli
    title: "Homebrew: bitwarden-cli"
  - id: winget-cli
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/b/Bitwarden/CLI
    title: "winget: Bitwarden.CLI"
  - id: choco-cli
    resource: https://community.chocolatey.org/packages/bitwarden-cli
    title: "Chocolatey: bitwarden-cli"
---
# Bitwarden

An open-source, end-to-end encrypted password manager that stores and shares passwords, passkeys and secrets for people, AI agents and machines.[^bitwarden]

## Features

From the vendor homepage:[^bitwarden]

- Autofill on any device.
- Password, username and email-alias generator.
- Sharing with permissions for families, teams and enterprises.
- Public codebase and independently verified security claims.
- Credential lifecycle management: creation, rotation, retirement and succession.
- Premium adds an integrated authenticator, file attachments, emergency access and security reports.

## Pricing

| Plan | Price (USD, billed annually) |
| --- | --- |
| Free | $0 |
| Premium | $1.65/mo ($19.80/yr) |
| Families (up to 6 users) | $3.99/mo ($47.88/yr) |
| Teams | $4/user/mo |
| Enterprise | $6/user/mo |

Prices as of 2026-10-18.[^bitwarden]

## Install

```sh
brew install --cask bitwarden
```

Requires macOS 12 or later.[^homebrew]

On Windows with [winget](./winget.md) (recommended):[^winget-pkg]

```powershell
winget install Bitwarden.Bitwarden
```

Or with [Chocolatey](./chocolatey.md):[^choco-pkg]

```powershell
choco install bitwarden
```

## CLI

The `bw` command-line client is a separate install.[^cli]

```sh
brew install bitwarden-cli          # macOS
```

```powershell
winget install Bitwarden.CLI        # Windows; or: choco install bitwarden-cli
```

There is also an npm package, `@bitwarden/cli`, and a native executable for each platform.[^homebrew-cli][^winget-cli][^choco-cli][^cli]

### Common commands

From the CLI docs:[^cli]

```sh
bw login                              # prompts for email, master password and any two-step code
export BW_SESSION="$(bw unlock --raw)" # prompts for the master password, so it stays out of shell history
bw get username <search term or id>
bw get password <search term or id>
bw get totp <search term or id>
bw list items --search github
bw sync                               # pull the latest vault from the server
bw lock                               # invalidate the session key when you're done
```

- **Logging in vs unlocking:** `bw login` signs you in to the account. Vault commands such as `get` and `list` also need a session key, which `bw unlock` returns. `--raw` prints only the key, without the explanatory message, so it can go straight into `BW_SESSION`.[^cli]
- **Session key:** the key sits in the `BW_SESSION` environment variable until you run `bw lock` or `bw logout`. It doesn't carry over to a new terminal window. Instead of setting the variable, you can pass `--session <key>` to each command.[^cli]
- **Search terms:** `bw get` errors if a search term matches more than one item. Use the item's id instead.[^cli]
- **Self-hosted or EU server:** run `bw config server <url>` before `bw login`, for example `bw config server https://vault.bitwarden.eu`.[^cli]

## See also

- [Password managers](../concepts/password-managers.md)

[^bitwarden]: [Bitwarden homepage](https://bitwarden.com/)
[^homebrew]: [Homebrew: bitwarden](https://formulae.brew.sh/cask/bitwarden)

[^choco-pkg]: [Chocolatey: bitwarden](https://community.chocolatey.org/packages/bitwarden)

[^winget-pkg]: [winget: Bitwarden.Bitwarden](https://github.com/microsoft/winget-pkgs/tree/master/manifests/b/Bitwarden/Bitwarden)

[^cli]: [Bitwarden CLI documentation](https://bitwarden.com/help/cli/)

[^homebrew-cli]: [Homebrew: bitwarden-cli](https://formulae.brew.sh/formula/bitwarden-cli)

[^winget-cli]: [winget: Bitwarden.CLI](https://github.com/microsoft/winget-pkgs/tree/master/manifests/b/Bitwarden/CLI)

[^choco-cli]: [Chocolatey: bitwarden-cli](https://community.chocolatey.org/packages/bitwarden-cli)
