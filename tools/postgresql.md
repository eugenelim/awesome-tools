---
type: Tool
title: PostgreSQL
description: An open-source object-relational database server, shipped with the psql terminal client.
resource: https://www.postgresql.org/
tags:
  - postgresql
  - database
  - server
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: PostgreSQL
pricing: Free
sources:
  - id: licence
    resource: https://www.postgresql.org/about/licence/
    title: PostgreSQL Licence
  - id: versioning
    resource: https://www.postgresql.org/support/versioning/
    title: PostgreSQL Versioning Policy
  - id: psql
    resource: https://www.postgresql.org/docs/current/app-psql.html
    title: psql documentation
  - id: macos
    resource: https://www.postgresql.org/download/macosx/
    title: PostgreSQL macOS packages
  - id: windows
    resource: https://www.postgresql.org/download/windows/
    title: PostgreSQL Windows installers
  - id: ubuntu
    resource: https://www.postgresql.org/download/linux/ubuntu/
    title: PostgreSQL Ubuntu packages and Apt repository
  - id: docker
    resource: https://github.com/docker-library/docs/blob/master/postgres/content.md
    title: Docker Official Image postgres documentation
  - id: packages
    resource: https://formulae.brew.sh/formula/postgresql@18
    title: "Homebrew: postgresql@18, libpq; winget: PostgreSQL.PostgreSQL.18; Chocolatey: postgresql, postgresql18"
---
# PostgreSQL

An open-source object-relational database server, released under the PostgreSQL Licence, which postgresql.org describes as similar to the BSD or MIT licences.[^licence] Every install includes `psql`, a terminal client that runs queries interactively, from a file or from command-line arguments.[^psql]

- **Versioning:** a new major version comes out about once a year and is supported for 5 years, with minor (bug and security fix) releases at least every three months.[^versioning]
- **Current version:** on 2026-10-21 the current major was 18 (18.6, supported until 14 November 2030). Versions 14 to 17 were also supported; 14 reaches end of life on 12 November 2026.[^versioning]
- **Upgrading:** a major upgrade needs a dump and reload, or `pg_upgrade`. A minor upgrade only needs new binaries and a restart.[^versioning]
- **EDB installer:** the Windows and macOS installer is hosted by EDB, not the PostgreSQL community, and bundles pgAdmin and StackBuilder.[^windows] [^macos]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install postgresql@18` then `brew services start postgresql@18`, or [Postgres.app](./postgres-app.md) |
| macOS (client only) | `brew install libpq` |
| Windows (recommended) | `winget install PostgreSQL.PostgreSQL.18` |
| Windows (alternative) | `choco install postgresql18` |
| Linux (Debian/Ubuntu) | `sudo apt install postgresql` (the distribution's version) |
| Linux (PGDG repository) | see below |
| Docker | `docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres` |

Homebrew has one formula per major version, `postgresql@NN`.[^macos] Both `postgresql@18` and `libpq` are keg-only, so their `bin` directories aren't linked onto your `PATH`; `libpq` is keg-only because it conflicts with PostgreSQL.[^packages] The winget package runs EDB's installer.[^packages]

The PGDG Apt repository has every supported version and keeps them updated:[^ubuntu]

```sh
sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
sudo apt install postgresql-18
```

In the Docker image, `POSTGRES_PASSWORD` is required. From PostgreSQL 18 the volume to mount is `/var/lib/postgresql`; for 17 and earlier it's `/var/lib/postgresql/data`.[^docker] See [Docker CLI](./docker-cli.md) for running containers without Docker Desktop.

On 2026-10-21, Homebrew (`postgresql@18`, `libpq`), winget and Chocolatey (`postgresql`, `postgresql18`) all had 18.6.[^packages]

## Use

```sh
psql -h localhost -U postgres
docker run -it --rm --network some-network postgres psql -h some-postgres -U postgres
```

The second command, from the Docker image docs, runs psql from a container against a server container.[^docker]

## See also

- [Databases](../concepts/databases.md)
- [Postgres.app](./postgres-app.md)
- [pgAdmin 4](./pgadmin.md)
- [pgcli](./pgcli.md)
- [pgvector](./pgvector.md)

[^licence]: [PostgreSQL Licence](https://www.postgresql.org/about/licence/)
[^versioning]: [PostgreSQL Versioning Policy](https://www.postgresql.org/support/versioning/), checked 2026-10-21
[^psql]: [psql documentation](https://www.postgresql.org/docs/current/app-psql.html)
[^macos]: [PostgreSQL macOS packages](https://www.postgresql.org/download/macosx/)
[^windows]: [PostgreSQL Windows installers](https://www.postgresql.org/download/windows/)
[^ubuntu]: [PostgreSQL Ubuntu packages and Apt repository](https://www.postgresql.org/download/linux/ubuntu/)
[^docker]: [Docker Official Image postgres documentation](https://github.com/docker-library/docs/blob/master/postgres/content.md)
[^packages]: Homebrew: [postgresql@18](https://formulae.brew.sh/formula/postgresql@18), [libpq](https://formulae.brew.sh/formula/libpq); winget: [PostgreSQL.PostgreSQL.18](https://github.com/microsoft/winget-pkgs/tree/master/manifests/p/PostgreSQL/PostgreSQL/18); Chocolatey: [postgresql](https://community.chocolatey.org/packages/postgresql), [postgresql18](https://community.chocolatey.org/packages/postgresql18); versions checked 2026-10-21
