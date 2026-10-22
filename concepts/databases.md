---
type: Category
title: Databases
description: Database servers and the clients, GUIs and extensions used with them.
---
# Databases

Database servers and the clients, GUIs and extensions used with them.

## PostgreSQL

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [PostgreSQL](../tools/postgresql.md) (includes psql) | PostgreSQL | `brew install postgresql@18` | `winget install PostgreSQL.PostgreSQL.18` | `sudo apt install postgresql`, or the PGDG repository |
| [Postgres.app](../tools/postgres-app.md) | PostgreSQL | `brew install --cask postgres-app` | | |
| [pgAdmin 4](../tools/pgadmin.md) | PostgreSQL | `brew install --cask pgadmin4` | `winget install PostgreSQL.pgAdmin` | `sudo apt install pgadmin4` (pgAdmin APT repository) |
| [pgcli](../tools/pgcli.md) | BSD-3-Clause | `brew install pgcli` | | `sudo apt-get install pgcli` or `pipx install pgcli` |
| [pgvector](../tools/pgvector.md) | PostgreSQL | `brew install pgvector` | build from source | `sudo apt install postgresql-18-pgvector` (PGDG repository) |

On a Mac, pick either Homebrew's `postgresql@18` or [Postgres.app](../tools/postgres-app.md) for the server, not both. Postgres.app already includes pgvector.

## Neo4j

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [Neo4j Community Edition](../tools/neo4j.md) | GPL-3.0 | `brew install neo4j` | zip from the Neo4j Deployment Center, or Docker | `sudo apt-get install neo4j` (Neo4j apt repository) |
| [Cypher Shell](../tools/cypher-shell.md) | GPL-3.0 | `brew install cypher-shell` | included in the Neo4j zip | included with the `neo4j` package |
| [Neo4j Browser](../tools/neo4j-browser.md) | | included with the server | included with the server | included with the server |
| [APOC Core](../tools/apoc.md) | Apache-2.0 | move the jar from `labs/` to `plugins/` | move the jar from `labs\` to `plugins\` | move the jar from `labs/` to `plugins/` |
| [Neo4j Desktop](../tools/neo4j-desktop.md) | | `brew install --cask neo4j-desktop` | `winget install Neo4j.Neo4jDesktop` | AppImage from the Neo4j Deployment Center |

Neo4j Desktop is free, but it runs Enterprise Edition under a single-developer licence, not Community Edition. For a Community-only setup, use the server with Neo4j Browser and Cypher Shell.

## Multi-database clients

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [DBeaver Community](../tools/dbeaver.md) | Apache-2.0 | `brew install --cask dbeaver-community` | `winget install DBeaver.DBeaver.Community` | `sudo snap install dbeaver-ce --classic` |

To run a database server in a container instead, see [Docker CLI](../tools/docker-cli.md); each server page gives its `docker run` command.
