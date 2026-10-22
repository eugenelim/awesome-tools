---
type: Tool
title: Postgres.app
description: PostgreSQL packaged as a native macOS app, with a menu bar item and the command-line tools.
resource: https://postgresapp.com/
tags:
  - postgresql
  - database
  - macos
  - open-source
platforms:
  - macOS
license: PostgreSQL
pricing: Free
sources:
  - id: site
    resource: https://postgresapp.com/
    title: Postgres.app home page
  - id: downloads
    resource: https://postgresapp.com/downloads.html
    title: Postgres.app downloads
  - id: cli
    resource: https://postgresapp.com/documentation/cli-tools.html
    title: Postgres.app CLI tools
  - id: repo
    resource: https://github.com/PostgresApp/PostgresApp
    title: PostgresApp/PostgresApp README and LICENSE
  - id: packages
    resource: https://formulae.brew.sh/cask/postgres-app
    title: "Homebrew: postgres-app"
---
# Postgres.app

PostgreSQL packaged as an ordinary Mac app, with a menu bar item, the command-line tools and headers.[^site] It can run several PostgreSQL versions side by side. The repository's LICENSE file is the PostgreSQL Licence.[^repo]

- **Bundled extensions:** PostGIS, wal2json and pldebugger; [pgvector](./pgvector.md) and pgrouting for PostgreSQL 15 and later; pljs for 14 and later.[^repo]
- **Defaults:** host `localhost`, port 5432, your macOS user name and no password.[^site]
- **Updates:** minor updates can install automatically.[^site]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask postgres-app` |

Or download it, move it to Applications, open it and click "Initialize".[^site] On 2026-10-21 the latest release was 2.9.6, with PostgreSQL 18.6, needing macOS 10.15 or later; a larger download bundles every supported version.[^downloads] Homebrew had 2.9.6, which bundles PostgreSQL 14 to 18.[^packages]

## Use

Add the bundled tools to `PATH`, then open a new terminal:[^cli]

```sh
sudo mkdir -p /etc/paths.d && echo /Applications/Postgres.app/Contents/Versions/latest/bin | sudo tee /etc/paths.d/postgresapp
psql
```

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)

[^site]: [Postgres.app home page](https://postgresapp.com/)
[^downloads]: [Postgres.app downloads](https://postgresapp.com/downloads.html), checked 2026-10-21
[^cli]: [Postgres.app CLI tools](https://postgresapp.com/documentation/cli-tools.html)
[^repo]: [PostgresApp/PostgresApp README and LICENSE](https://github.com/PostgresApp/PostgresApp)
[^packages]: Homebrew: [postgres-app](https://formulae.brew.sh/cask/postgres-app); version checked 2026-10-21
