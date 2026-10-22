---
type: Tool
title: pgcli
description: A terminal client for PostgreSQL with auto-completion and syntax highlighting.
resource: https://www.pgcli.com/
tags:
  - postgresql
  - database
  - cli
  - python
  - open-source
platforms:
  - macOS
  - Linux
license: BSD-3-Clause
pricing: Free
sources:
  - id: pgcli
    resource: https://github.com/dbcli/pgcli
    title: dbcli/pgcli README
  - id: packages
    resource: https://formulae.brew.sh/formula/pgcli
    title: "Homebrew: pgcli; PyPI: pgcli"
---
# pgcli

A terminal client for PostgreSQL with auto-completion and syntax highlighting; an alternative to psql for interactive work. Licensed under BSD-3-Clause.[^pgcli] [^packages]

- **Connections:** takes a database name or a `postgresql://` connection URL.[^pgcli]
- **Python:** the PyPI package needs Python 3.10 or later. The README notes that a pip install needs PostgreSQL on the system.[^packages] [^pgcli]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install pgcli` |
| Linux (Debian/Ubuntu) | `sudo apt-get install pgcli` |
| Any (Python) | `pipx install pgcli`, or run it without installing: `uvx pgcli` |

Many Linux distributions package it; pipx or uvx get the latest PyPI release in an isolated environment.[^pgcli] For uv, see [Python dev environments](../concepts/python-dev-environments.md). On 2026-10-21, Homebrew and PyPI both had 4.7.1.[^packages]

## Use

```sh
pgcli local_database
pgcli postgresql://user@example.com:5432/app_db
```

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)

[^pgcli]: [dbcli/pgcli README](https://github.com/dbcli/pgcli)
[^packages]: Homebrew: [pgcli](https://formulae.brew.sh/formula/pgcli); PyPI: [pgcli](https://pypi.org/project/pgcli/); versions checked 2026-10-21
