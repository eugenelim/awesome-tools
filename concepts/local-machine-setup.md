---
type: Overview
title: Local machine setup
description: Essential tools first, then tools for each type of work, with platforms, licences and Homebrew and Windows install commands.
---
# Local machine setup

Every tool in this bundle: the essentials first, then the tools for each type of work. Install what matches your work. Details and sources are on each tool page, and a blank cell means the captured sources don't state it.

- [Essentials](#essentials)
- [AI-assisted coding](#ai-assisted-coding)
- [Notes, knowledge and email](#notes-knowledge-and-email)
- [Python](#python)
- [Go](#go)
- [Containers and Kubernetes](#containers-and-kubernetes)
- [Databases and vector search](#databases-and-vector-search)
- [Web, APIs and design](#web-apis-and-design)
- [Ontologies and data modelling](#ontologies-and-data-modelling)
- [Personal AI agents](#personal-ai-agents)
- [Install commands](#install-commands)

## Essentials

The maintainer's picks for any machine, whatever your work: the core setup, command-line utilities, then everyday utilities. Set up the [package manager](./package-managers.md) first.

### Core setup

A package manager, a password manager, a terminal, an editor and the GitHub CLI. On Windows, also WSL and Git for Windows; see [Windows platform tools](./windows-platform-tools.md).

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Homebrew](../tools/homebrew.md) | [Package manager](./package-managers.md) | ✓ | (WSL) | ✓ | BSD-2-Clause |
| [Bitwarden](../tools/bitwarden.md) | [Password manager](./password-managers.md) | ✓ | ✓ | ✓ | Open source |
| [Ghostty](../tools/ghostty.md) | [Terminal emulator](./terminal-emulators.md) | ✓ | | ✓ | |
| [Zed](../tools/zed.md) | [Code editor](./code-editors.md) | ✓ | ✓ | ✓ | GPL-3.0-or-later |
| [GitHub CLI (gh)](../tools/github-cli.md) | [Git and GitHub tool](./git-tools.md) | ✓ | ✓ | ✓ | MIT |
| [winget](../tools/winget.md) | [Package manager](./package-managers.md) | | ✓ | | MIT |
| [Chocolatey](../tools/chocolatey.md) | [Package manager](./package-managers.md) (fallback to winget) | | ✓ | | Apache-2.0 |
| [WSL](../tools/wsl.md) | [Windows platform tool](./windows-platform-tools.md) | | ✓ | | MIT |

### Command-line utilities

Small terminal tools for searching code, finding files, processing JSON and viewing directory trees.

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [ripgrep (rg)](../tools/ripgrep.md) | [Command-line utility](./command-line-utilities.md) | ✓ | ✓ | ✓ | Unlicense OR MIT |
| [fd](../tools/fd.md) | [Command-line utility](./command-line-utilities.md) | ✓ | ✓ | ✓ | Apache-2.0 OR MIT |
| [jq](../tools/jq.md) | [Command-line utility](./command-line-utilities.md) | ✓ | ✓ | ✓ | MIT |
| [tree](../tools/tree.md) | [Command-line utility](./command-line-utilities.md) | ✓ | | ✓ | GPL-2.0-or-later |

### Everyday utilities

Browsers, file managers and small utilities. Pick the ones for your platform.

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Firefox Developer Edition](../tools/firefox-developer-edition.md) | [Web browser](./web-browsers.md) | ✓ | ✓ | ✓ | |
| [SigmaOS](../tools/sigmaos.md) | [Web browser](./web-browsers.md) | ✓ | | | |
| [Rill](../tools/rill.md) | [Web browser](./web-browsers.md) | ✓ (Apple silicon) | | | |
| [Rascal](../tools/rascal.md) | [File manager](./file-managers.md) | ✓ | | | MIT |
| [Swift Salamander](../tools/swift-salamander.md) | [File manager](./file-managers.md) | ✓ | | | |
| [FreeCommander](../tools/freecommander.md) | [File manager](./file-managers.md) | | ✓ | | Freeware |
| [Multi Commander](../tools/multicommander.md) | [File manager](./file-managers.md) | | ✓ | | Freeware |
| [OneCommander](../tools/onecommander.md) | [File manager](./file-managers.md) | | ✓ | | Proprietary |
| [Forel](../tools/forel.md) | [macOS utility](./macos-utilities.md) | ✓ | | | GPL-3.0 |
| [Vorssaint](../tools/vorssaint.md) | [macOS utility](./macos-utilities.md) | ✓ (Apple silicon) | | | GPL-3.0-or-later |
| [Wick](../tools/wick.md) | [macOS utility](./macos-utilities.md) | ✓ | | | |
| [openGym](../tools/opengym.md) | [Health and fitness](./health-and-fitness.md) | ✓ (Docker) | ✓ (Docker) | ✓ (Docker) | AGPL-3.0 |

## AI-assisted coding

Coding agents, and agentic development environments (ADEs) for running several agents at once.

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Claude Code](../tools/claude-code.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | |
| [Codex](../tools/codex.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [GitHub Copilot CLI](../tools/github-copilot.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | |
| [Pi](../tools/pi.md) | [AI coding agent](./ai-coding-agents.md) | ✓ | ✓ | ✓ | MIT |
| [Antigravity](../tools/antigravity.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | |
| [Orca](../tools/orca.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |
| [herdr](../tools/herdr.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [VelaTerm](../tools/velaterm.md) | [ADE](./agentic-development-environments.md) | ✓ | ✓ | ✓ | MIT |

## Notes, knowledge and email

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Obsidian](../tools/obsidian.md) | [Knowledge management](./knowledge-management.md) | ✓ | | | |
| [OpenKnowledge](../tools/openknowledge.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Logseq](../tools/logseq.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | AGPL-3.0 |
| [Octarine](../tools/octarine.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | |
| [SilverBullet](../tools/silverbullet.md) | [Knowledge management](./knowledge-management.md) | ✓ | ✓ | ✓ | MIT |
| [Himalaya](../tools/himalaya.md) | [Email client](./email-clients.md) | ✓ | ✓ | ✓ | MIT OR Apache-2.0 |

## Python

Install Python and manage environments with uv; see [Python dev environments](./python-dev-environments.md).

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Ruff](../tools/ruff.md) | [Python developer tool](./python-tools.md) | ✓ | ✓ | ✓ | MIT |
| [mypy](../tools/mypy.md) | [Python developer tool](./python-tools.md) | ✓ | ✓ | ✓ | MIT |
| [ty](../tools/ty.md) (beta) | [Python developer tool](./python-tools.md) | ✓ | ✓ | ✓ | MIT |
| [pytest](../tools/pytest.md) | [Python developer tool](./python-tools.md) | ✓ | ✓ | ✓ | MIT |
| [pre-commit](../tools/pre-commit.md) | [Python developer tool](./python-tools.md) | ✓ | ✓ | ✓ | MIT |

For Node.js, see [Node.js dev environments](./node-dev-environments.md).

## Go

Install Go itself as described in [Go dev environments](./go-dev-environments.md).

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [golangci-lint](../tools/golangci-lint.md) | [Go developer tool](./go-tools.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Delve](../tools/delve.md) | [Go developer tool](./go-tools.md) | ✓ | ✓ | ✓ | MIT |
| [govulncheck](../tools/govulncheck.md) | [Go developer tool](./go-tools.md) | ✓ | ✓ | ✓ | BSD-3-Clause |
| [GoReleaser](../tools/goreleaser.md) | [Go developer tool](./go-tools.md) | ✓ | ✓ | ✓ | MIT |

## Containers and Kubernetes

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Docker CLI](../tools/docker-cli.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Colima](../tools/colima.md) | [Containers](./containers.md) | ✓ | | ✓ | MIT |
| [kubectl](../tools/kubectl.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Helm](../tools/helm.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [k9s](../tools/k9s.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [kind](../tools/kind.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [kubectx and kubens](../tools/kubectx.md) | [Containers](./containers.md) | ✓ | ✓ | ✓ | Apache-2.0 |

On a Mac, the Docker CLI with Colima replaces Docker Desktop; on Windows, run Docker Engine in WSL 2. See [Docker CLI](../tools/docker-cli.md).

## Databases and vector search

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [PostgreSQL](../tools/postgresql.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | PostgreSQL |
| [Postgres.app](../tools/postgres-app.md) | [Database](./databases.md) | ✓ | | | PostgreSQL |
| [pgAdmin 4](../tools/pgadmin.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | PostgreSQL |
| [pgcli](../tools/pgcli.md) | [Database](./databases.md) | ✓ | | ✓ | BSD-3-Clause |
| [Postgres MCP Pro](../tools/postgres-mcp-pro.md) | [Database](./databases.md) (MCP server) | ✓ | ✓ | ✓ | MIT |
| [pgvector](../tools/pgvector.md) | [Vector search](./databases.md#vector-search) | ✓ | ✓ | ✓ | PostgreSQL |
| [Qdrant](../tools/qdrant.md) | [Vector search](./databases.md#vector-search) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Neo4j Community Edition](../tools/neo4j.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Cypher Shell](../tools/cypher-shell.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Neo4j Browser](../tools/neo4j-browser.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | |
| [APOC Core](../tools/apoc.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Neo4j Desktop](../tools/neo4j-desktop.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | |
| [DBeaver Community](../tools/dbeaver.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | Apache-2.0 |

## Web, APIs and design

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Insomnia](../tools/insomnia.md) | [API client](./api-clients.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Paper](../tools/paper.md) | [Design tool](./design-tools.md) | ✓ (Apple silicon) | | | |

## Ontologies and data modelling

For a LinkML project, see [LinkML dev environment](./linkml-dev-environment.md).

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [LinkML](../tools/linkml.md) (core Python tools) | [Data modelling](./data-modelling.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [LinkML-Scala](../tools/linkml-scala.md) | [Data modelling](./data-modelling.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [LinkML-OWL](../tools/linkml-owl.md) | [Data modelling](./data-modelling.md) | ✓ | ✓ | ✓ | |
| [Schema Automator](../tools/schema-automator.md) | [Data modelling](./data-modelling.md) | ✓ | ✓ | ✓ | BSD-3-Clause |
| [Protégé](../tools/protege.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | BSD-2-Clause-Views |
| [WebProtégé (self-hosted)](../tools/webprotege.md) | [Ontology editor](./ontology-editors.md) | ✓ (Docker) | ✓ (Docker) | ✓ (Docker) | BSD-2-Clause (deployment) |
| [VocBench](../tools/vocbench.md) | [Ontology editor](./ontology-editors.md) | ✓ (Java) | ✓ (Java) | ✓ (Java) | Open source |

## Personal AI agents

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Hermes Agent](../tools/hermes.md) | [Personal AI agent](./personal-ai-agents.md) | ✓ | ✓ | ✓ | MIT |
| [Muse](../tools/muse.md) | [Personal AI agent](./personal-ai-agents.md) | ✓ | | | |

## Install commands

The commands follow the same groups. Copy the essentials, then the groups you need.

### Homebrew

Install Homebrew and add it to your shell first; see [Homebrew](../tools/homebrew.md#set-up). To update everything later, run `brew update && brew upgrade`.

```sh
# Essentials: core setup
brew install --cask bitwarden ghostty zed
brew install gh

# Essentials: command-line utilities
brew install ripgrep fd jq tree

# Essentials: everyday utilities
brew install --cask c0desurfer/tap/swift-salamander
brew install --cask chang-07/tap/rascal
brew install --cask lab421/tap/forel
brew install --cask firefox@developer-edition
brew install --cask sigmaos vorssaint

# AI-assisted coding
brew install --cask claude-code codex stablyai/orca/orca
brew install copilot-cli  # not `copilot` (AWS's ECS tool)
brew install --cask antigravity
brew install pi-coding-agent
brew install herdr

# Notes, knowledge and email
brew install node git
brew install --cask obsidian
npm install -g @inkeep/open-knowledge
brew install --cask octarine logseq
brew install himalaya

# Python: add mypy and pytest per project with uv
brew install uv
brew install ruff ty pre-commit

# Go
brew install golangci-lint delve govulncheck
brew install --cask goreleaser/tap/goreleaser

# Containers and Kubernetes
brew install docker docker-compose docker-buildx colima  # Docker CLI without Docker Desktop
brew install kubectl helm k9s kind kubectx              # kubectx installs kubens too

# Databases and vector search
brew install postgresql@18 pgcli pgvector  # or Postgres.app instead of postgresql@18
brew install neo4j                         # includes cypher-shell
brew install --cask pgadmin4 dbeaver-community neo4j-desktop
docker run -p 6333:6333 qdrant/qdrant      # Qdrant has no Homebrew package

# Web, APIs and design
brew install --cask insomnia paper-design

# Ontologies and data modelling
brew install openjdk@17                    # Java 17+ for VocBench
uv tool install linkml                     # or a LinkML project; see the LinkML guide
uv tool install schema-automator           # optional LinkML add-on
uv tool install linkml-owl                 # optional LinkML add-on
mise use -g ubi:NeverBlink-OSS/linkml-scala  # optional: LinkML-Scala native CLI

# Personal AI agents
brew install hermes-agent
brew install --cask hermes-desktop
```

VelaTerm, SilverBullet, Wick, VocBench, Rill, Qdrant, openGym (Docker) and WebProtégé (Docker) have no Homebrew package. The Protégé and Muse casks are disabled. Install these from their websites.

### Windows

Use winget first and Chocolatey only as a fallback; [Windows platform tools](./windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback) explains why. winget is built into Windows 10 1809+ and Windows 11; see [winget](../tools/winget.md#set-up) to check it works. To update everything later, run `winget upgrade --all`.

With winget (IDs checked 2026-10-19):

```powershell
# Essentials: core setup
wsl --install                                    # as administrator, then restart (Windows 10 2004+ or 11)
winget install Git.Git                           # Git for Windows, includes Git Bash
winget install --id GitHub.cli --source winget   # GitHub CLI (gh)
winget install Bitwarden.Bitwarden
winget install ZedIndustries.Zed

# Essentials: everyday utilities
winget install MilosParipovic.OneCommander       # Pro licence needed for commercial use
winget install MarekJasinski.FreeCommanderXE
winget install MathiasSvensson.MultiCommander

# AI-assisted coding
winget install Anthropic.ClaudeCode
winget install OpenAI.Codex
winget install GitHub.Copilot
winget install Google.Antigravity

# Notes and knowledge
winget install Obsidian.Obsidian
winget install Logseq.Logseq

# Python and Node.js
winget install astral-sh.uv
winget install astral-sh.ruff
winget install astral-sh.ty
winget install Schniz.fnm
winget install jdx.mise

# Go
winget install GolangCI.golangci-lint
winget install goreleaser.goreleaser

# Containers and Kubernetes
winget install Docker.DockerCLI                  # client only; run Docker Engine in WSL 2
winget install -e --id Kubernetes.kubectl
winget install Helm.Helm                         # Chocolatey's kubernetes-helm lags behind
winget install Derailed.k9s
winget install Kubernetes.kind
winget install --id ahmetb.kubectx
winget install --id ahmetb.kubens

# Databases
winget install PostgreSQL.PostgreSQL.18
winget install PostgreSQL.pgAdmin
winget install DBeaver.DBeaver.Community         # 26.2.0 vs 26.2.3 on Chocolatey, 2026-10-21
winget install Neo4j.Neo4jDesktop

# Web and APIs
winget install Insomnia.Insomnia

# Data modelling (after installing uv above)
uv tool install linkml
```

With Chocolatey, for tools winget lacks or only has as a preview. Install Chocolatey first (administrator PowerShell; see [Chocolatey](../tools/chocolatey.md)):

```powershell
choco install herdr                              # AI-assisted coding
choco install himalaya                           # email; or: scoop install himalaya
choco install hermes-desktop                     # personal AI agents
```

Delve, govulncheck, mypy, pytest and pre-commit have no winget package; install them with `go install` or uv as their pages show. Himalaya has no winget package either; use Chocolatey or Scoop. The Neo4j server has no Windows package; use its zip or Docker. Qdrant has no winget or Chocolatey package; use Docker or the release zip. Colima doesn't run on Windows.

Every winget tool above except Multi Commander, ty and Neo4j Desktop also has a Chocolatey package (Insomnia's is years out of date); IDs are on each tool page. Watch for the name traps: `zed` (use `zed-editor`), `orca` and `nvm`.

These have no Chocolatey package: Octarine, Firefox Developer Edition, Orca (the `orca` package is Microsoft's MSI editor), VelaTerm, SilverBullet, OpenKnowledge, Protégé, VocBench and Pi. Install them from their websites. See [Windows platform tools](./windows-platform-tools.md) for the recommended shell setup.
