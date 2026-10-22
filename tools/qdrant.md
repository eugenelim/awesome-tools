---
type: Tool
title: Qdrant
description: An open-source vector database and similarity search engine written in Rust, with an official MCP server.
resource: https://qdrant.tech/
tags:
  - database
  - vector-search
  - ai
  - mcp
  - rust
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free; managed Qdrant Cloud has a free tier
sources:
  - id: qdrant
    resource: https://github.com/qdrant/qdrant
    title: qdrant/qdrant README
  - id: releases
    resource: https://github.com/qdrant/qdrant/releases
    title: qdrant/qdrant releases
  - id: webui
    resource: https://qdrant.tech/documentation/web-ui/
    title: Qdrant Web UI documentation
  - id: mcp
    resource: https://github.com/qdrant/mcp-server-qdrant
    title: qdrant/mcp-server-qdrant README
  - id: claude-mcp
    resource: https://code.claude.com/docs/en/mcp
    title: Claude Code docs, Connect Claude Code to tools via MCP
---
# Qdrant

A vector similarity search engine and vector database. It stores points (vectors with a JSON payload) and serves them over a REST API (with an OpenAPI 3.0 spec) and gRPC. Written in Rust and licensed under Apache-2.0. A managed Qdrant Cloud has a free tier.[^qdrant]

- **Search:** dense vectors for semantic similarity, sparse vectors for full-text search, and multivectors such as ColBERT. Hybrid search merges results with Reciprocal Rank Fusion or Distribution-Based Score Fusion.[^qdrant]
- **Filtering:** filter on the payload by keyword, full-text, numeric range or geo-location, combined with `must`, `should` and `must_not`.[^qdrant]
- **Memory:** built-in quantization cuts RAM use by up to 97%, and vectors can be stored on disk.[^qdrant]
- **Scale:** sharding and replication, and multitenancy for multi-user data.[^qdrant]
- **Web UI:** a dashboard at `http://localhost:6333/dashboard` for browsing collections and calling the REST API.[^qdrant] [^webui]
- **Clients:** official Python, JavaScript/TypeScript, Go, Rust, .NET and Java clients.[^qdrant]
- **Qdrant Edge:** an in-process version for Python and Rust that stores data locally and can sync with a server.[^qdrant]

For vectors next to relational data in an existing PostgreSQL database, see [pgvector](./pgvector.md) instead.

## Install

```sh
docker run -p 6333:6333 qdrant/qdrant
```

This starts Qdrant with no authentication, listening on all network interfaces; read Qdrant's security guide before exposing it.[^qdrant] For Docker without Docker Desktop, see [Docker CLI](./docker-cli.md) and [Colima](./colima.md).

Each release also ships binaries for macOS (Apple silicon and Intel), Windows x86-64 and Linux, plus a Debian package and an AppImage. On 2026-10-21 the latest was v1.19.2 (2026-10-05). There's no Homebrew, winget or Chocolatey package.[^releases]

```python
from qdrant_client import QdrantClient
client = QdrantClient(url="http://localhost:6333")
```

## MCP server

Qdrant's official MCP server, `mcp-server-qdrant` (Apache-2.0), uses Qdrant as a semantic memory for agents. It has two tools: `qdrant-store` saves text with optional metadata, and `qdrant-find` searches it. It embeds text with FastEmbed, using `sentence-transformers/all-MiniLM-L6-v2` by default.[^mcp]

Configure it with environment variables: `QDRANT_URL` (or `QDRANT_LOCAL_PATH` for a local database, not both), `QDRANT_API_KEY`, `COLLECTION_NAME` and `EMBEDDING_MODEL`. `QDRANT_READ_ONLY=true` removes the store tool. Transports are stdio (the default), SSE and streamable HTTP. It needs Python 3.10 or later and runs with `uvx`.[^mcp]

To add it to [Claude Code](./claude-code.md):[^mcp] [^claude-mcp]

```sh
claude mcp add --env QDRANT_URL=http://localhost:6333 --env COLLECTION_NAME=agent-memory \
  --transport stdio qdrant -- uvx mcp-server-qdrant
```

## See also

- [Databases](../concepts/databases.md#vector-search)
- [pgvector](./pgvector.md)

[^qdrant]: [qdrant/qdrant README](https://github.com/qdrant/qdrant)
[^releases]: [qdrant/qdrant releases](https://github.com/qdrant/qdrant/releases); checked 2026-10-21. Homebrew: no `qdrant` formula or cask; Chocolatey: no `qdrant` package
[^webui]: [Qdrant Web UI documentation](https://qdrant.tech/documentation/web-ui/)
[^mcp]: [qdrant/mcp-server-qdrant README](https://github.com/qdrant/mcp-server-qdrant); PyPI [mcp-server-qdrant](https://pypi.org/project/mcp-server-qdrant/) 0.8.1, checked 2026-10-21
[^claude-mcp]: Claude Code docs: [Connect Claude Code to tools via MCP](https://code.claude.com/docs/en/mcp)
