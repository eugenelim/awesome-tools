---
type: Tool
title: Neo4j Browser
description: The web interface that ships with Neo4j server for running Cypher and viewing results as graphs or tables.
resource: https://neo4j.com/docs/browser/
tags:
  - neo4j
  - graph-database
  - gui
platforms:
  - macOS
  - Windows
  - Linux
pricing: Free
sources:
  - id: docs
    resource: https://neo4j.com/docs/browser/
    title: Neo4j Browser manual
  - id: repo
    resource: https://github.com/neo4j/neo4j-browser
    title: neo4j/neo4j-browser README
  - id: macos
    resource: https://neo4j.com/docs/operations-manual/current/installation/osx/
    title: Neo4j Operations Manual, macOS installation
---
# Neo4j Browser

A developer tool for running Cypher queries and viewing the results as a graph or as an exportable table. It's the default developer interface for both Community and Enterprise Edition and comes with the Neo4j server; Neo4j Aura and [Neo4j Desktop](./neo4j-desktop.md) offer the same tool as **Query**.[^docs]

- **Capabilities:** read and write queries, some admin commands, and graph and table views of results.[^docs]
- **Licence:** the current Browser is built from closed-source artefacts shared with Neo4j Console and Neo4j Desktop. The GPL-3.0 `neo4j/neo4j-browser` repository holds the classic Browser, which is no longer bundled with the server.[^repo]
- **Hosted:** a hosted copy is at `https://browser.neo4j.io`.[^repo]

## Install

Nothing to install. Start a [Neo4j server](./neo4j.md) and open `http://localhost:7474`.[^macos]

## Use

Open `http://localhost:7474` and log in as `neo4j`. With the default password, `neo4j`, you're asked to change it at first login.[^macos]

## See also

- [Databases](../concepts/databases.md)
- [Neo4j Community Edition](./neo4j.md)

[^docs]: [Neo4j Browser manual](https://neo4j.com/docs/browser/)
[^repo]: [neo4j/neo4j-browser README](https://github.com/neo4j/neo4j-browser)
[^macos]: [Neo4j Operations Manual, macOS installation](https://neo4j.com/docs/operations-manual/current/installation/osx/)
