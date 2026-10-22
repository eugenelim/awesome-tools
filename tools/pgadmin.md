---
type: Tool
title: pgAdmin 4
description: An administration, development and monitoring tool for PostgreSQL that runs as a desktop app or a web server.
resource: https://www.pgadmin.org/
tags:
  - postgresql
  - database
  - gui
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: PostgreSQL
pricing: Free
sources:
  - id: pgadmin
    resource: https://www.pgadmin.org/
    title: pgAdmin home page
  - id: licence
    resource: https://www.pgadmin.org/licence/
    title: pgAdmin licence
  - id: apt
    resource: https://www.pgadmin.org/download/pgadmin-4-apt/
    title: pgAdmin 4 APT instructions
  - id: packages
    resource: https://formulae.brew.sh/cask/pgadmin4
    title: "Homebrew: pgadmin4; winget: PostgreSQL.pgAdmin; Chocolatey: pgadmin4"
---
# pgAdmin 4

An administration, development and monitoring tool for PostgreSQL. It runs in desktop or server (web) mode on Windows, macOS and Linux, and in containers.[^pgadmin] Licensed under the PostgreSQL Licence.[^licence]

- **Windows:** one signed 64-bit installer covers desktop and server mode.[^pgadmin]
- **macOS:** a signed, notarised universal disk image for Apple silicon and Intel.[^pgadmin]
- **Linux:** packages are `pgadmin4` (desktop and web), `pgadmin4-desktop` and `pgadmin4-web`. Configure the web package with `/usr/pgadmin4/bin/setup-web.sh`.[^apt]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask pgadmin4` |
| Windows (recommended) | `winget install PostgreSQL.pgAdmin` |
| Windows (alternative) | `choco install pgadmin4` |
| Linux (Debian/Ubuntu) | add the pgAdmin APT repository, then `sudo apt install pgadmin4`[^apt] |
| Container | `docker pull dpage/pgadmin4` |

On 2026-10-21, Homebrew, winget and Chocolatey all had 9.18.[^packages] The Windows and macOS PostgreSQL installers from EDB also bundle pgAdmin; see [PostgreSQL](./postgresql.md).

## Use

Run the web version in a container ([Docker CLI](./docker-cli.md)):

```sh
docker run -p 80:80 \
  -e 'PGADMIN_DEFAULT_EMAIL=user@domain.com' \
  -e 'PGADMIN_DEFAULT_PASSWORD=SuperSecret' \
  -d dpage/pgadmin4
```

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)
- [DBeaver Community](./dbeaver.md)

[^pgadmin]: [pgAdmin home page](https://www.pgadmin.org/)
[^licence]: [pgAdmin licence](https://www.pgadmin.org/licence/)
[^apt]: [pgAdmin 4 APT instructions](https://www.pgadmin.org/download/pgadmin-4-apt/)
[^packages]: Homebrew: [pgadmin4](https://formulae.brew.sh/cask/pgadmin4); winget: [PostgreSQL.pgAdmin](https://github.com/microsoft/winget-pkgs/tree/master/manifests/p/PostgreSQL/pgAdmin); Chocolatey: [pgadmin4](https://community.chocolatey.org/packages/pgadmin4); versions checked 2026-10-21
