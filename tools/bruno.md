---
type: Tool
title: Bruno
description: Open-source, offline-only API client that stores collections as plain-text files in a folder you can keep in Git; imports Postman and Insomnia collections.
resource: https://www.usebruno.com/
tags:
  - api
  - testing
  - git
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free; paid Pro and Ultimate editions
sources:
  - id: bruno
    resource: https://github.com/usebruno/bruno
    title: usebruno/bruno README
  - id: import
    resource: https://docs.usebruno.com/get-started/import-export-data/import-collections
    title: "Bruno docs: Import collections"
  - id: postman
    resource: https://docs.usebruno.com/get-started/import-export-data/postman-migration
    title: "Bruno docs: Migrating from Postman"
  - id: pricing
    resource: https://www.usebruno.com/pricing
    title: Bruno pricing
  - id: packages
    resource: https://formulae.brew.sh/cask/bruno
    title: "Homebrew: bruno; winget: Bruno.Bruno; Chocolatey: bruno"
---
# Bruno

An open-source API client, licensed under MIT. Bruno stores each collection directly in a folder on your filesystem, in a plain-text format, so you can review and share collections with Git like code. It's offline-only: the project says it has no plans to add cloud sync, ever.[^bruno]

- **Protocols:** HTTP/REST, GraphQL and gRPC, with testing, documentation, scripting, code generation and history in the free edition.[^pricing]
- **CLI:** `bru run` runs a collection, folder or single request from the terminal or CI. Install it with `npm install -g @usebruno/cli`, or use the `usebruno/cli` Docker image.[^bruno]

## Import from Postman and Insomnia

Bruno imports collections from both:[^import] [^postman]

- **Postman:** export the collection as Collection v2 or v2.1 JSON, then in Bruno choose **+** → **Import Collection**. Import Postman environments separately from Bruno's environment settings. Bruno translates common Postman script calls, such as `pm.test`, `pm.environment` and `pm.response`, to its own. Scripts that use Postman-only packages, such as `newman` or `postman-collection`, need rewriting.
- **Postman, everything at once:** importing a full Postman data export (all collections, environments and globals) needs the paid Ultimate edition.
- **Insomnia:** export from Application → Preferences → Data → Export Data. Bruno reads Insomnia v4 `.json` and v5+ `.yaml` exports.

Importing converts a copy; it doesn't keep the original tool in sync. Bruno stores all variable values as strings, so imported numbers and booleans become text.[^postman]

**Developer Mode:** some imported scripts need libraries that only run in Developer Mode, where scripts can access files and run system commands. Only turn it on for collections you trust.[^postman]

## Pricing

| Edition | Price (per user/month, billed annually) | Adds |
| --- | --- | --- |
| Open Source | $0 | Core client; 2 workspaces; public Git providers only |
| Pro | $6 | Private Git providers, unlimited workspaces, support SLA |
| Ultimate | $11 | SSO, SCIM, audit logs, bulk Postman import; 14-day trial |

Prices as of 2026-10-24.[^pricing]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask bruno` |
| Windows (recommended) | `winget install Bruno.Bruno` |
| Windows (alternative) | `choco install bruno` |
| Linux | `snap install bruno`, Flatpak `com.usebruno.Bruno`, or Bruno's apt repository |

From the README.[^bruno] On 2026-10-24, Homebrew, winget and Chocolatey all had 4.3.0, the latest release.[^packages]

## See also

- [API clients](../concepts/api-clients.md)
- [Insomnia](./insomnia.md)

[^bruno]: [usebruno/bruno README](https://github.com/usebruno/bruno)
[^import]: [Bruno docs: Import collections](https://docs.usebruno.com/get-started/import-export-data/import-collections)
[^postman]: [Bruno docs: Migrating from Postman](https://docs.usebruno.com/get-started/import-export-data/postman-migration)
[^pricing]: [Bruno pricing](https://www.usebruno.com/pricing), checked 2026-10-24
[^packages]: Homebrew: [bruno](https://formulae.brew.sh/cask/bruno); winget: [Bruno.Bruno](https://github.com/microsoft/winget-pkgs/tree/master/manifests/b/Bruno/Bruno); Chocolatey: [bruno](https://community.chocolatey.org/packages/bruno); [releases](https://github.com/usebruno/bruno/releases); checked 2026-10-24
