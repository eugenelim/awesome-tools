---
type: Tool
title: Cypher Shell
description: Neo4j's command-line client for running Cypher queries and admin commands over the Bolt protocol.
resource: https://neo4j.com/docs/operations-manual/current/cypher-shell/
tags:
  - neo4j
  - graph-database
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: GPL-3.0
pricing: Free
sources:
  - id: docs
    resource: https://neo4j.com/docs/operations-manual/current/cypher-shell/
    title: Neo4j Operations Manual, Cypher Shell
  - id: source
    resource: https://github.com/neo4j/neo4j/tree/2026.10/community/cypher-shell
    title: neo4j/neo4j community/cypher-shell
  - id: packages
    resource: https://formulae.brew.sh/formula/cypher-shell
    title: "Homebrew: cypher-shell"
---
# Cypher Shell

A command-line client for running Cypher queries and admin tasks against a Neo4j database over Bolt. It's interactive by default; for scripts, pass Cypher as an argument or pipe in a file (on Windows, piping needs PowerShell).[^docs] The source is in the main Neo4j repository under `community/cypher-shell` (GPL-3.0); the old `neo4j/cypher-shell` repository is archived.[^source]

- **Bundled** in the `bin` directory of every server install, and also downloadable on its own from the Neo4j Deployment Center.[^docs]
- **Options:** `--format auto|verbose|plain` for output, `-P '{a: 1}'` for parameters and `-f FILE` to run a file.[^docs]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install cypher-shell` (also installed by `brew install neo4j`) |
| Windows | `bin\cypher-shell` in the Neo4j zip, or the standalone download from the Neo4j Deployment Center |
| Linux | installed with the `neo4j` apt or yum package; `bin/cypher-shell` in tar installs |

On 2026-10-21 Homebrew had 2026.10.0, which depends on `openjdk@21`.[^packages]

## Use

```sh
cypher-shell -a neo4j://localhost:7687 -u neo4j
cat some-cypher.txt | cypher-shell
cypher-shell -f import.cypher --format plain
```

## See also

- [Databases](../concepts/databases.md)
- [Neo4j Community Edition](./neo4j.md)

[^docs]: [Neo4j Operations Manual, Cypher Shell](https://neo4j.com/docs/operations-manual/current/cypher-shell/)
[^source]: [neo4j/neo4j community/cypher-shell](https://github.com/neo4j/neo4j/tree/2026.10/community/cypher-shell); [neo4j/cypher-shell](https://github.com/neo4j/cypher-shell) (archived)
[^packages]: Homebrew: [cypher-shell](https://formulae.brew.sh/formula/cypher-shell); version checked 2026-10-21
