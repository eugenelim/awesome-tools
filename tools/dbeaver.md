---
type: Tool
title: DBeaver Community
description: A cross-platform desktop database tool and SQL client with drivers for more than 100 databases, including PostgreSQL.
resource: https://dbeaver.io/
tags:
  - database
  - postgresql
  - gui
  - sql
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: dbeaver
    resource: https://github.com/dbeaver/dbeaver
    title: dbeaver/dbeaver README
  - id: download
    resource: https://dbeaver.io/download/
    title: DBeaver Community download
  - id: packages
    resource: https://formulae.brew.sh/cask/dbeaver-community
    title: "Homebrew: dbeaver-community; winget: DBeaver.DBeaver.Community; Chocolatey: dbeaver"
---
# DBeaver Community

A desktop database tool and SQL client for Windows, macOS and Linux, with a schema editor, SQL editor, data editor, ER diagrams, data import and export, execution plans and SSH tunnelling. Licensed under Apache-2.0.[^dbeaver]

- **Drivers:** more than 100 out of the box, including PostgreSQL; any database with a JDBC or ODBC driver can be added.[^dbeaver]
- **Java:** needs Java, and every distribution bundles an OpenJDK runtime.[^dbeaver]
- **Community vs PRO:** the paid PRO editions add NoSQL and more cloud databases (for example MongoDB, Cassandra and Redis), files as databases, federated queries, enterprise authentication (SAML, SSO, Kerberos) and more AI providers. Community's AI chat supports OpenAI-compatible endpoints and Copilot.[^dbeaver] [^download]
- **Releases:** usually a minor release every two weeks and a major release every quarter.[^download]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install --cask dbeaver-community` |
| Windows (recommended) | `winget install DBeaver.DBeaver.Community` |
| Windows (alternative) | `choco install dbeaver` |
| Linux | `sudo snap install dbeaver-ce --classic` or `flatpak install flathub io.dbeaver.DBeaverCommunity` |

The download page also has DEB, RPM and tar.gz builds, a Debian repository and a Launchpad PPA.[^download] On 2026-10-21, Homebrew and Chocolatey had 26.2.3 but winget had 26.2.0.[^packages]

## See also

- [Databases](../concepts/databases.md)
- [PostgreSQL](./postgresql.md)
- [pgAdmin 4](./pgadmin.md)

[^dbeaver]: [dbeaver/dbeaver README](https://github.com/dbeaver/dbeaver)
[^download]: [DBeaver Community download](https://dbeaver.io/download/), checked 2026-10-21
[^packages]: Homebrew: [dbeaver-community](https://formulae.brew.sh/cask/dbeaver-community); winget: [DBeaver.DBeaver.Community](https://github.com/microsoft/winget-pkgs/tree/master/manifests/d/DBeaver/DBeaver/Community); Chocolatey: [dbeaver](https://community.chocolatey.org/packages/dbeaver); versions checked 2026-10-21
