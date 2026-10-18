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

## See also

- [Password managers](../concepts/password-managers.md)

[^bitwarden]: [Bitwarden homepage](https://bitwarden.com/)
[^homebrew]: [Homebrew: bitwarden](https://formulae.brew.sh/cask/bitwarden)
