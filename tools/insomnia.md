---
type: Tool
title: Insomnia
description: Kong's open-source desktop API client for REST, GraphQL, gRPC, WebSockets and SSE, with an OpenAPI editor, tests, mocks and the inso CLI.
resource: https://insomnia.rest/
tags:
  - api
  - http
  - graphql
  - grpc
  - openapi
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free Essentials plan; Pro $12 and Enterprise $45 per user per month
sources:
  - id: insomnia
    resource: https://github.com/Kong/insomnia
    title: Kong/insomnia README
  - id: releases
    resource: https://github.com/Kong/insomnia/releases
    title: Kong/insomnia releases
  - id: pricing
    resource: https://insomnia.rest/pricing
    title: Insomnia pricing
  - id: packages
    resource: https://formulae.brew.sh/cask/insomnia
    title: "Homebrew: insomnia, inso; winget: Insomnia.Insomnia; Chocolatey: insomnia-rest-api-client"
---
# Insomnia

An open-source, cross-platform API client for REST, GraphQL, WebSockets, Server-Sent Events (SSE), gRPC and other HTTP-compatible protocols. Made by Kong and licensed under Apache-2.0.[^insomnia]

- **Debug:** send requests over the protocols above.[^insomnia]
- **Design:** a built-in OpenAPI editor with a visual preview.[^insomnia]
- **Test:** test suites and a collection runner.[^insomnia]
- **Mock:** cloud or self-hosted mock servers.[^insomnia]
- **CI/CD:** the `inso` CLI lints and tests in pipelines.[^insomnia]
- **Plugins:** third-party plugins.[^insomnia]

## Accounts and storage

Without an account you can only use the local **Scratch Pad**; most features need a free account. An account doesn't decide where your data goes. Each project uses one of three storage options:[^insomnia]

| Storage | Where data lives |
| --- | --- |
| Local Vault | Only on your machine |
| Git Sync | In a Git repository you choose, without going through Insomnia's cloud |
| Cloud Sync | In Insomnia's cloud, optionally end-to-end encrypted |

**Private Environments** keep environment settings, such as secrets, on your machine whatever storage the project uses.[^insomnia] For API data you can't share outside your organisation, use Local Vault or Git Sync, and keep secrets in private environments.

## Pricing

| Plan | Price per user per month | Notes |
| --- | --- | --- |
| Essentials | $0 | Unlimited cloud and local projects; Git Sync projects for up to 3 users; 1,000 mock requests a month |
| Pro | $12 | Unlimited users, Git Sync for everyone, unlimited organisations, 10,000 mock requests a month |
| Enterprise | $45 | Everything in Pro plus unlimited mock requests; self-serve up to 50 users |

Prices from Insomnia's pricing page on 2026-10-21.[^pricing] SAML and OIDC single sign-on also need a paid plan.[^insomnia]

## Install

| Platform | App | CLI (`inso`) |
| --- | --- | --- |
| macOS (12 or later) | `brew install --cask insomnia` | `brew install --cask inso` |
| Windows | `winget install Insomnia.Insomnia` | `inso-windows` zip from the releases page |
| Linux | `.deb`, `.rpm`, AppImage, snap or tarball from the releases page | `inso-linux-x64` tarball from the releases page |

On 2026-10-21 Homebrew and winget had 13.3.1, the latest release (2026-10-09).[^packages] [^releases] winget's `Insomnia.Inso` package stops at 9.2.0, and Chocolatey's `insomnia-rest-api-client` at 2023.11.2, so neither is listed.[^packages]

## See also

- [API clients](../concepts/api-clients.md)
- [Bruno](./bruno.md), which can import Insomnia collections

[^insomnia]: [Kong/insomnia README](https://github.com/Kong/insomnia)
[^releases]: [Kong/insomnia releases](https://github.com/Kong/insomnia/releases); `core@13.3.1`, checked 2026-10-21
[^pricing]: [Insomnia pricing](https://insomnia.rest/pricing); checked 2026-10-21
[^packages]: Homebrew: [insomnia](https://formulae.brew.sh/cask/insomnia), [inso](https://formulae.brew.sh/cask/inso); winget: [Insomnia.Insomnia](https://github.com/microsoft/winget-pkgs/tree/master/manifests/i/Insomnia/Insomnia), [Insomnia.Inso](https://github.com/microsoft/winget-pkgs/tree/master/manifests/i/Insomnia/Inso); Chocolatey: [insomnia-rest-api-client](https://community.chocolatey.org/packages/insomnia-rest-api-client); versions checked 2026-10-21
