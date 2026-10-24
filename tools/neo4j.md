---
type: Tool
title: Neo4j Community Edition
description: The open-source, single-instance edition of the Neo4j graph database, queried with Cypher.
resource: https://neo4j.com/
tags:
  - neo4j
  - database
  - graph-database
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: GPL-3.0
pricing: Free
sources:
  - id: neo4j
    resource: https://github.com/neo4j/neo4j
    title: neo4j/neo4j README and LICENSE.txt
  - id: editions
    resource: https://neo4j.com/docs/operations-manual/current/introduction/
    title: Neo4j Operations Manual, Introduction
  - id: macos
    resource: https://neo4j.com/docs/operations-manual/current/installation/osx/
    title: Neo4j Operations Manual, macOS installation
  - id: debian
    resource: https://neo4j.com/docs/operations-manual/current/installation/linux/debian/
    title: Neo4j Operations Manual, Debian-based distributions
  - id: rpm
    resource: https://neo4j.com/docs/operations-manual/current/installation/linux/rpm/
    title: Neo4j Operations Manual, Red Hat, CentOS, Fedora and Amazon Linux
  - id: windows
    resource: https://neo4j.com/docs/operations-manual/current/installation/windows/
    title: Neo4j Operations Manual, Windows installation
  - id: docker
    resource: https://neo4j.com/docs/operations-manual/current/docker/introduction/
    title: Neo4j Operations Manual, Getting started with Neo4j in Docker
  - id: cli
    resource: https://neo4j.com/docs/operations-manual/current/neo4j-admin-neo4j-cli/
    title: Neo4j Operations Manual, neo4j and neo4j-admin commands
  - id: services
    resource: https://docs.brew.sh/Manpage#services-subcommand
    title: "Homebrew manpage: brew services"
  - id: packages
    resource: https://formulae.brew.sh/formula/neo4j
    title: "Homebrew: neo4j; Docker Hub: neo4j"
---
# Neo4j Community Edition

A graph database that stores data as nodes and relationships (a property graph), queried with the Cypher language.[^editions] Community Edition is licensed under GPL-3.0; Enterprise Edition adds closed-source components that aren't in the public repository and need a commercial licence.[^neo4j] Neo4j describes Community Edition as "suitable for single-instance deployments".[^editions]

- **Included:** ACID transactions, Cypher, [Cypher Shell](./cypher-shell.md), [Neo4j Browser](./neo4j-browser.md), the Bolt protocol, full-text and vector indexes, property uniqueness constraints, offline import and offline backup (dump).[^editions]
- **Enterprise only:** clustering, online backup and restore, more than one user database, composite databases, role-based and sub-graph access control, LDAP/Active Directory and Kerberos, property existence, type and key constraints, parallel Cypher runtimes, change data capture, incremental import, Bloom and Prometheus metrics.[^editions]
- **Versioning:** since 2025.01.0 the server uses calendar versions (`YYYY.MM.Patch`), and some releases are long-term support. From 2025.06 the Cypher language is versioned separately (Cypher 5 and Cypher 25).[^editions]
- **Java:** needs a Java 21 runtime; Java 25 is supported from 2025.10.[^debian]
- **Usage data:** Community Edition reports a small amount of usage data by default.[^editions]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install neo4j`, then [start it](#run-on-macos-with-homebrew)[^macos] |
| Windows | the Windows zip from the Neo4j Deployment Center (run `bin\neo4j console`), or Docker[^windows] |
| Linux (Debian/Ubuntu) | add the `https://debian.neo4j.com` apt repository, then `sudo apt-get install neo4j`[^debian] |
| Linux (RHEL, Fedora, Amazon Linux) | add the `https://yum.neo4j.com/stable/latest` repository, then `yum install neo4j-<version>`[^rpm] |
| Docker | `docker run --publish=7474:7474 --publish=7687:7687 --volume=$HOME/neo4j/data:/data neo4j`[^docker] |

The Homebrew formula installs Community Edition as a service.[^macos] On Windows you need Oracle JDK 21 or Zulu JDK 21.[^windows] On Linux, apt pulls in OpenJDK 21 if no JDK is installed; on Ubuntu Server, enable the `universe` repository first.[^debian] The official Docker image's Community tags have no suffix (for example `neo4j:2026.10.0`); Enterprise tags end in `-enterprise`.[^docker] For Docker without Docker Desktop, see [Docker CLI](./docker-cli.md).

On 2026-10-21 Homebrew had 2026.10.0, the latest release, and installs [Cypher Shell](./cypher-shell.md) and `openjdk@21` with it. There's no winget package, and Chocolatey's `neo4j-community` is stuck at 3.5.1, so neither is listed.[^packages]

## Run on macOS with Homebrew

### Start now and at every login

```sh
brew services start neo4j        # start now, and again at every login
brew services list               # check it's running
brew services restart neo4j      # after changing the configuration file
brew services stop neo4j         # stop, and don't start at login
```

Configuration changes only take effect after a restart.[^macos] Without `sudo`, `brew services` starts the service at login.[^services] The service runs `neo4j console` from `$(brew --prefix)/var/neo4j` and logs to `$(brew --prefix)/var/log/neo4j.log`.[^packages]

### Run without a background service

The Homebrew formula puts the `neo4j` command on `PATH`, so you can run the server yourself. It won't start again at login:[^cli] [^macos]

```sh
neo4j console      # in this terminal, with logs printed here
neo4j start        # or as a background process (daemon)
neo4j status
neo4j stop
```

## Use

```sh
$NEO4J_HOME/bin/neo4j console             # foreground, zip or tar install
docker run --restart always \
  --publish=7474:7474 --publish=7687:7687 \
  --env NEO4J_AUTH=neo4j/your_password \
  --volume=/path/to/your/data:/data \
  neo4j:2026.10.0
```

[Neo4j Browser](./neo4j-browser.md) is at `http://localhost:7474` and drivers connect to `bolt://localhost:7687`. The default login is `neo4j`/`neo4j`, and you're asked to change the password at first login.[^macos] Without a mounted `/data` volume, the container loses its data on restart, and mounted folders must exist before it starts.[^docker]

## See also

- [Databases](../concepts/databases.md)
- [Cypher Shell](./cypher-shell.md)
- [APOC Core](./apoc.md)
- [Neo4j Desktop](./neo4j-desktop.md)

[^neo4j]: [neo4j/neo4j README](https://github.com/neo4j/neo4j) and [LICENSE.txt](https://github.com/neo4j/neo4j/blob/2026.10/LICENSE.txt)
[^editions]: [Neo4j Operations Manual, Introduction](https://neo4j.com/docs/operations-manual/current/introduction/)
[^macos]: [Neo4j Operations Manual, macOS installation](https://neo4j.com/docs/operations-manual/current/installation/osx/)
[^debian]: [Neo4j Operations Manual, Debian-based distributions](https://neo4j.com/docs/operations-manual/current/installation/linux/debian/)
[^rpm]: [Neo4j Operations Manual, RPM installation](https://neo4j.com/docs/operations-manual/current/installation/linux/rpm/)
[^windows]: [Neo4j Operations Manual, Windows installation](https://neo4j.com/docs/operations-manual/current/installation/windows/)
[^docker]: [Neo4j Operations Manual, Getting started with Neo4j in Docker](https://neo4j.com/docs/operations-manual/current/docker/introduction/)
[^cli]: [Neo4j Operations Manual, neo4j and neo4j-admin commands](https://neo4j.com/docs/operations-manual/current/neo4j-admin-neo4j-cli/)
[^services]: [Homebrew manpage: brew services](https://docs.brew.sh/Manpage#services-subcommand)
[^packages]: Homebrew: [neo4j](https://formulae.brew.sh/formula/neo4j); Docker Hub: [neo4j](https://hub.docker.com/_/neo4j); Chocolatey: [neo4j-community](https://community.chocolatey.org/packages/neo4j-community); versions checked 2026-10-21; service definition checked 2026-10-24
