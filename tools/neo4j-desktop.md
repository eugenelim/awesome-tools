---
type: Tool
title: Neo4j Desktop
description: Neo4j's desktop app for creating and managing local Neo4j databases, bundled with an Enterprise Edition Developer licence.
resource: https://neo4j.com/download/
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
  - id: desktop
    resource: https://neo4j.com/docs/desktop/current/
    title: Neo4j Desktop manual
  - id: install
    resource: https://neo4j.com/docs/desktop/current/installation/
    title: Neo4j Desktop manual, Installation
  - id: packages
    resource: https://formulae.brew.sh/cask/neo4j-desktop
    title: "Homebrew: neo4j-desktop; winget: Neo4j.Neo4jDesktop"
---
# Neo4j Desktop

A desktop app for creating and managing local Neo4j databases, online or offline; it also connects to remote servers and Neo4j Aura.[^desktop] It's a free download, but it doesn't run [Community Edition](./neo4j.md). It includes a Developer licence for Enterprise Edition, with all Enterprise features, "for development use by an individual person on a single machine".[^desktop] [^install]

- **Instances:** run any number of local databases, from Neo4j 5.1.0 to the latest version, and back up, upgrade and add plugins such as [APOC Core](./apoc.md) from the app.[^desktop]
- **Tools:** Import (CSV import and modelling), Query ([Neo4j Browser](./neo4j-browser.md)), Bloom (visual exploration) and Dashboards.[^desktop]
- **Bundled runtime:** on Windows and Linux it ships with the latest Enterprise database and the JDK it needs; on macOS these download when first needed.[^install]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask neo4j-desktop` |
| Windows | `winget install Neo4j.Neo4jDesktop` |
| Linux | the AppImage from the Neo4j Deployment Center: `chmod +x` it and run it[^install] |

Neo4j lists macOS 10.10+, Ubuntu 22.04, Debian 11 and Windows 10 with PowerShell 5.1+.[^install] The Homebrew cask needs macOS 13 or later. On 2026-10-21 the cask had 2.3.0 but winget had 2.2.1. There's no Chocolatey package.[^packages]

## See also

- [Databases](../concepts/databases.md)
- [Neo4j Community Edition](./neo4j.md)

[^desktop]: [Neo4j Desktop manual](https://neo4j.com/docs/desktop/current/)
[^install]: [Neo4j Desktop manual, Installation](https://neo4j.com/docs/desktop/current/installation/)
[^packages]: Homebrew: [neo4j-desktop](https://formulae.brew.sh/cask/neo4j-desktop); winget: [Neo4j.Neo4jDesktop](https://github.com/microsoft/winget-pkgs/tree/master/manifests/n/Neo4j/Neo4jDesktop); versions checked 2026-10-21
