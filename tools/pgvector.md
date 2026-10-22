---
type: Tool
title: pgvector
description: A PostgreSQL extension for storing vectors and running exact or approximate nearest-neighbour search.
resource: https://github.com/pgvector/pgvector
tags:
  - postgresql
  - database
  - extension
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: PostgreSQL
pricing: Free
sources:
  - id: pgvector
    resource: https://github.com/pgvector/pgvector
    title: pgvector/pgvector README and LICENSE
  - id: packages
    resource: https://formulae.brew.sh/formula/pgvector
    title: "Homebrew: pgvector"
---
# pgvector

A PostgreSQL extension that stores vectors alongside the rest of your data. Its LICENSE file is the PostgreSQL Licence.[^pgvector] [^packages]

- **Vector types:** single-precision, half-precision, binary and sparse.[^pgvector]
- **Distances:** L2, inner product, cosine, L1, Hamming and Jaccard.[^pgvector]
- **Search:** exact nearest-neighbour search by default; HNSW and IVFFlat indexes give faster approximate search at some cost in recall.[^pgvector]
- **Versions:** supports PostgreSQL 13 and later.[^pgvector]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install pgvector` (for the `postgresql@18` and `postgresql@17` formulae), or use [Postgres.app](./postgres-app.md), which includes it |
| Windows | build with `nmake /F Makefile.win` from a Visual Studio x64 Native Tools prompt |
| Linux (Debian/Ubuntu, PGDG repository) | `sudo apt install postgresql-18-pgvector` (use your server's major version) |
| Docker | `docker pull pgvector/pgvector:pg18-trixie` |

The commands are from the README.[^pgvector] On 2026-10-21 Homebrew had 0.8.7.[^packages]

## Use

```sql
CREATE EXTENSION vector;
CREATE TABLE items (id bigserial PRIMARY KEY, embedding vector(3));
INSERT INTO items (embedding) VALUES ('[1,2,3]'), ('[4,5,6]');
SELECT * FROM items ORDER BY embedding <-> '[3,1,2]' LIMIT 5;
```

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)

[^pgvector]: [pgvector/pgvector README and LICENSE](https://github.com/pgvector/pgvector)
[^packages]: Homebrew: [pgvector](https://formulae.brew.sh/formula/pgvector); version checked 2026-10-21
