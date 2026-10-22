---
type: Tool
title: APOC Core
description: A library of Cypher procedures and functions for Neo4j, covering data integration, conversion and graph utilities.
resource: https://neo4j.com/docs/apoc/current/
tags:
  - neo4j
  - graph-database
  - plugin
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: apoc
    resource: https://github.com/neo4j/apoc
    title: neo4j/apoc README and LICENSE
  - id: install
    resource: https://neo4j.com/docs/apoc/current/installation/
    title: APOC Core documentation, Installation
  - id: editions
    resource: https://neo4j.com/docs/operations-manual/current/introduction/
    title: Neo4j Operations Manual, Introduction
---
# APOC Core

"Awesome Procedures On Cypher": procedures and functions written in Java and called from Cypher, for tasks that are hard to express in Cypher alone, such as data integration, graph algorithms and data conversion. Since Neo4j 5.0 the officially supported APOC Core lives in `neo4j/apoc`; the rest was split out as the community-maintained APOC Extended. Licensed under Apache-2.0.[^apoc] It's available in [Community Edition](./neo4j.md).[^editions]

- **Bundled:** the jar ships with Neo4j in `$NEO4J_HOME/labs`. To enable it, move it to `$NEO4J_HOME/plugins` and restart.[^install]
- **Versions must match:** the year and month of the APOC version must match the Neo4j server's; patch numbers needn't.[^install]
- **Least privilege:** all procedures load by default. The docs recommend allowing only the ones you need with `dbms.security.procedures.allowlist`.[^install]

## Install

| Platform | Command |
| --- | --- |
| Server (any OS) | `mv $NEO4J_HOME/labs/apoc-*-core.jar $NEO4J_HOME/plugins/`, then restart Neo4j |
| Docker (development) | `docker run -p 7474:7474 -p 7687:7687 -e NEO4J_PLUGINS='["apoc"]' neo4j:2026.10` |
| Neo4j Desktop | install it from the instance's plugins |

`NEO4J_PLUGINS` is meant for development; for production, the docs say to download the matching jar and mount it at `/plugins`.[^install] On 2026-10-21 the latest release was 2026.10.0, matching Neo4j 2026.10.0.[^apoc]

## Use

Mount a downloaded jar into a container:[^install]

```sh
mkdir plugins && cd plugins
wget https://github.com/neo4j/apoc/releases/download/2026.10.0/apoc-2026.10.0-core.jar
cd ..
docker run --rm -e NEO4J_AUTH=none -p 7474:7474 -p 7687:7687 \
  -v $PWD/plugins:/plugins neo4j:2026.10
```

## See also

- [Databases](../concepts/databases.md)
- [Neo4j Community Edition](./neo4j.md)
- [Neo4j Desktop](./neo4j-desktop.md)

[^apoc]: [neo4j/apoc README](https://github.com/neo4j/apoc), [LICENSE](https://github.com/neo4j/apoc/blob/dev/LICENSE) and [releases](https://github.com/neo4j/apoc/releases); versions checked 2026-10-21
[^install]: [APOC Core documentation, Installation](https://neo4j.com/docs/apoc/current/installation/)
[^editions]: [Neo4j Operations Manual, Introduction](https://neo4j.com/docs/operations-manual/current/introduction/)
