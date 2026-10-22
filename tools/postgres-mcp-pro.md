---
type: Tool
title: Postgres MCP Pro
description: An open-source PostgreSQL MCP server that gives AI agents schema access, SQL execution, query plans, index tuning and health checks.
resource: https://github.com/crystaldba/postgres-mcp
tags:
  - postgresql
  - database
  - mcp
  - ai
  - python
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: pgmcp
    resource: https://github.com/crystaldba/postgres-mcp
    title: crystaldba/postgres-mcp README
  - id: releases
    resource: https://github.com/crystaldba/postgres-mcp/releases
    title: crystaldba/postgres-mcp releases and commits
  - id: pypi
    resource: https://pypi.org/project/postgres-mcp/
    title: "PyPI: postgres-mcp"
  - id: reference
    resource: https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres
    title: Reference PostgreSQL MCP server (archived)
  - id: claude-mcp
    resource: https://code.claude.com/docs/en/mcp
    title: Claude Code docs, Connect Claude Code to tools via MCP
---
# Postgres MCP Pro

A Model Context Protocol (MCP) server that connects AI agents such as [Claude Code](./claude-code.md) to a [PostgreSQL](./postgresql.md) database. Besides running queries, it has tools for query plans, index tuning and database health. Made by Crystal DBA and licensed under MIT.[^pgmcp]

- **Tools:** `list_schemas`, `list_objects`, `get_object_details`, `execute_sql`, `explain_query` (including with hypothetical indexes), `get_top_queries`, `analyze_workload_indexes`, `analyze_query_indexes` (up to 10 queries) and `analyze_db_health`.[^pgmcp]
- **Health checks:** buffer cache hit rates, connections, constraints, duplicate, unused and invalid indexes, sequence limits and vacuum health. Some checks come from PgHero.[^pgmcp]
- **Index tuning:** uses a version of Microsoft's Anytime algorithm for SQL Server's Database Tuning Advisor, rather than asking the model to guess.[^pgmcp]
- **Transports:** stdio, or SSE so several clients can share one server.[^pgmcp]
- **Versions:** tested on PostgreSQL 15, 16 and 17.[^pgmcp]
- **Releases:** the latest release is v0.3.0 (2025-05-16). On 2026-10-21 the last commit to `main` was on 2026-08-16.[^releases] [^pypi]

## Access modes

Pass one of these with `--access-mode`.[^pgmcp]

| Mode | What the agent can do | Intended for |
| --- | --- | --- |
| `unrestricted` | Read and write data and change the schema | Development |
| `restricted` | Read-only transactions, with an execution-time limit | Production |

Every example in the README uses `unrestricted`, so choose the mode deliberately. Use `restricted` for anything other than a local development database.[^pgmcp]

## Install

You need Docker or Python 3.12 or later. The README recommends Docker, because Python setups hit more environment-specific problems.[^pgmcp] [^pypi]

| Method | Command |
| --- | --- |
| Docker | `docker pull crystaldba/postgres-mcp` |
| uv (no install) | `uvx postgres-mcp` |
| pipx | `pipx install postgres-mcp` |

The Docker image remaps `localhost` in the connection URI to the host (`host.docker.internal` on macOS and Windows).[^pgmcp] For Docker without Docker Desktop, see [Docker CLI](./docker-cli.md); for uv, see [Python dev environments](../concepts/python-dev-environments.md).

### Index tuning extensions

Index tuning and workload analysis need two extensions in the database: `pg_stat_statements` for query statistics and `hypopg` for simulating indexes.[^pgmcp]

```sql
CREATE EXTENSION IF NOT EXISTS pg_stat_statements;
CREATE EXTENSION IF NOT EXISTS hypopg;
```

On AWS RDS, Azure and Google Cloud SQL both are usually available already. On a self-managed server, add `pg_stat_statements` to `shared_preload_libraries` first, and you may need to install `hypopg` from your package manager.[^pgmcp]

## Connect an agent

The server reads the connection from the `DATABASE_URI` environment variable.[^pgmcp] With Claude Code, Claude's options go before the server name and the server's command goes after `--`:[^claude-mcp]

```sh
claude mcp add --env DATABASE_URI=postgresql://user:password@localhost:5432/app_db \
  --transport stdio postgres -- uvx postgres-mcp --access-mode=restricted
```

For Claude Desktop, Cursor and other clients, add it to the client's `mcpServers` JSON:[^pgmcp]

```json
{
  "mcpServers": {
    "postgres": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "-e", "DATABASE_URI",
               "crystaldba/postgres-mcp", "--access-mode=restricted"],
      "env": {
        "DATABASE_URI": "postgresql://user:password@localhost:5432/app_db"
      }
    }
  }
}
```

To share one server, start it with `--transport=sse` (for example `docker run -p 8000:8000 ...`) and point clients at `http://localhost:8000/sse`.[^pgmcp]

## Other PostgreSQL MCP servers

- **Reference server:** the original PostgreSQL MCP server from the MCP project ran read-only queries and exposed table schemas as MCP resources. It's archived and no longer maintained.[^reference]
- **Hosted Postgres:** Supabase and Neon have their own MCP servers for their management APIs.[^pgmcp]

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)
- [pgcli](./pgcli.md)

[^pgmcp]: [crystaldba/postgres-mcp README](https://github.com/crystaldba/postgres-mcp)
[^releases]: [crystaldba/postgres-mcp releases](https://github.com/crystaldba/postgres-mcp/releases) and [commits](https://github.com/crystaldba/postgres-mcp/commits/main); checked 2026-10-21
[^pypi]: PyPI: [postgres-mcp](https://pypi.org/project/postgres-mcp/) (0.3.0, requires Python 3.12+); checked 2026-10-21
[^reference]: [Reference PostgreSQL MCP server](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres), in [modelcontextprotocol/servers-archived](https://github.com/modelcontextprotocol/servers-archived)
[^claude-mcp]: Claude Code docs: [Connect Claude Code to tools via MCP](https://code.claude.com/docs/en/mcp)
