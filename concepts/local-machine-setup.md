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
- [Rust](#rust)
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

## Rust

Install Rust with rustup as described in [Rust dev environments](./rust-dev-environments.md); rustfmt and Clippy come with it.

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [cargo-nextest](../tools/cargo-nextest.md) | [Rust developer tool](./rust-tools.md) | ✓ | ✓ | ✓ | Apache-2.0 OR MIT |
| [cargo-deny](../tools/cargo-deny.md) | [Rust developer tool](./rust-tools.md) | ✓ | ✓ | ✓ | Apache-2.0 OR MIT |
| [cargo-audit](../tools/cargo-audit.md) | [Rust developer tool](./rust-tools.md) | ✓ | ✓ | ✓ | Apache-2.0 OR MIT |

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

### PostgreSQL

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [PostgreSQL](../tools/postgresql.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | PostgreSQL |
| [Postgres.app](../tools/postgres-app.md) | [Database](./databases.md) | ✓ | | | PostgreSQL |
| [pgAdmin 4](../tools/pgadmin.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | PostgreSQL |
| [pgcli](../tools/pgcli.md) | [Database](./databases.md) | ✓ | | ✓ | BSD-3-Clause |
| [Postgres MCP Pro](../tools/postgres-mcp-pro.md) | [Database](./databases.md) (MCP server) | ✓ | ✓ | ✓ | MIT |
| [pgvector](../tools/pgvector.md) | [Vector search](./databases.md#vector-search) | ✓ | ✓ | ✓ | PostgreSQL |

### Neo4j

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Neo4j Community Edition](../tools/neo4j.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Cypher Shell](../tools/cypher-shell.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | GPL-3.0 |
| [Neo4j Browser](../tools/neo4j-browser.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | |
| [APOC Core](../tools/apoc.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Neo4j Desktop](../tools/neo4j-desktop.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | |

### Other databases and clients

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Qdrant](../tools/qdrant.md) | [Vector search](./databases.md#vector-search) | ✓ | ✓ | ✓ | Apache-2.0 |
| [DBeaver Community](../tools/dbeaver.md) | [Database](./databases.md) | ✓ | ✓ | ✓ | Apache-2.0 |

## Web, APIs and design

| Tool | Type | macOS | Windows | Linux | Licence |
| --- | --- | --- | --- | --- | --- |
| [Bruno](../tools/bruno.md) | [API client](./api-clients.md) | ✓ | ✓ | ✓ | MIT |
| [Insomnia](../tools/insomnia.md) | [API client](./api-clients.md) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Spectral](../tools/spectral.md) | [API description linter](./api-clients.md#api-description-linters) | ✓ | ✓ | ✓ | Apache-2.0 |
| [Paper](../tools/paper.md) | [Design tool](./design-tools.md) | ✓ (Apple silicon) | | | |
| [Penpot](../tools/penpot.md) | [Design tool](./design-tools.md) | ✓ (web, Docker) | ✓ (web, Docker) | ✓ (web, Docker) | MPL-2.0 |
| [ImageOptim](../tools/imageoptim.md) | [Design tool](./design-tools.md#image-optimisation) | ✓ | | | GPL-2.0-or-later |

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

Install Homebrew and add it to your shell first; see [Homebrew](../tools/homebrew.md#set-up). To update everything later, run `brew update && brew upgrade`, then `uv python upgrade` for uv's Pythons and `uv tool upgrade --all` for uv tools.

```sh
# Essentials: core setup
brew install --cask bitwarden ghostty zed
brew install gh
brew install git

# Essentials: command-line utilities
brew install ripgrep fd jq tree

# Essentials: everyday utilities
brew install --cask c0desurfer/tap/swift-salamander  # dual-pane file manager
brew install --cask firefox@developer-edition        # Firefox with beta DevTools
brew install --cask chang-07/tap/rascal              # keyboard-first Finder replacement
brew install --cask lab421/tap/forel                 # folder automation (Hazel alternative)
brew install --cask sigmaos                          # browser with workspaces and an AI assistant
brew install --cask vorssaint                        # menu bar toolkit

# AI-assisted coding
brew install --cask claude-code codex stablyai/orca/orca
brew install copilot-cli  # not `copilot` (AWS's ECS tool)
brew install --cask antigravity
brew install pi-coding-agent
brew install herdr

# Node.js: fnm installs Node.js, which comes with npm; see the Node.js guide
brew install fnm                           # Node.js version manager
eval "$(fnm env --use-on-cd --shell zsh)"  # also add this line to ~/.zshrc
fnm install --lts                          # the first version installed becomes the default

# Notes, knowledge and email
brew install --cask obsidian
npm install -g @inkeep/open-knowledge      # needs Node.js 24+ and git, installed above
brew install --cask octarine logseq
brew install himalaya

# Python: add mypy and pytest per project with uv
brew install uv               # Python versions, environments, packages and tools
uv python install 3.14        # a uv-managed Python, so uv doesn't fall back to a system one
uv python update-shell        # put ~/.local/bin (python3.14, uv tools) on PATH; open a new terminal
uv python pin --global 3.14   # default when a project doesn't pin a version
brew install ruff             # linter and formatter
brew install ty               # type checker and language server (beta)
brew install pre-commit       # Git pre-commit hooks

# Go
brew install go                               # Go itself; switches toolchains per project
brew install golangci-lint                    # runs linters in parallel, and formats code
brew install delve                            # debugger (dlv)
brew install govulncheck                      # finds known vulnerabilities your code reaches
brew install --cask goreleaser/tap/goreleaser # release automation

# Rust: see the Rust guide
brew install rustup                           # Rust toolchains and components
export PATH="$(brew --prefix rustup)/bin:$HOME/.cargo/bin:$PATH"  # keg-only; also add this line to ~/.zshrc
rustup default stable                         # stable Rust, with rustfmt and Clippy
rustup component add rust-analyzer            # language server for editors
brew install cargo-nextest                    # faster test runner
brew install cargo-deny                       # dependency advisories, licences and sources
brew install cargo-audit                      # RustSec advisories

# Containers and Kubernetes
brew install docker docker-compose docker-buildx colima  # Docker CLI without Docker Desktop
brew install kubectl helm k9s kind kubectx              # kubectx installs kubens too

# Databases and vector search
brew install postgresql@18 pgcli pgvector  # PostgreSQL; or Postgres.app instead of postgresql@18
brew install --cask pgadmin4
brew install neo4j                         # Neo4j; includes cypher-shell
brew install --cask neo4j-desktop
brew install --cask dbeaver-community      # multi-database SQL client
docker run -p 6333:6333 qdrant/qdrant      # Qdrant has no Homebrew package

# Web, APIs and design
brew install --cask bruno         # offline API client; collections are files in Git
brew install --cask insomnia      # API client for REST, GraphQL, gRPC, WebSockets and SSE
brew install spectral-cli         # lints OpenAPI, AsyncAPI and Arazzo files against rulesets
brew install --cask paper-design  # design tool with an HTML/CSS canvas that agents can edit
brew install --cask imageoptim    # shrinks JPEG, PNG, SVG and GIF files and strips metadata
# Penpot has no Homebrew package: use penpot.app, or self-host with Docker (see the Penpot page)

# Ontologies and data modelling
brew install openjdk@21                    # Java 17+ for VocBench; skip if you installed neo4j, which installs it
uv tool install --with jinja2-time copier  # creates LinkML projects from the template; see the LinkML guide
uv tool install rust-just                  # task runner the template uses
uv tool install linkml                     # optional: LinkML commands outside a project
uv tool install schema-automator           # optional LinkML add-on
uv tool install linkml-owl                 # optional LinkML add-on
mise use -g ubi:NeverBlink-OSS/linkml-scala  # optional: LinkML-Scala native CLI

# Personal AI agents
brew install hermes-agent
brew install --cask hermes-desktop
```

VelaTerm, SilverBullet, Wick, VocBench, Rill, Qdrant, openGym (Docker), WebProtégé (Docker) and Penpot (web or Docker) have no Homebrew package. The Protégé and Muse casks are disabled. Install these from their websites.

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
winget install MilosParipovic.OneCommander       # Explorer alternative with Miller columns; Pro licence needed for commercial use
winget install MarekJasinski.FreeCommanderXE     # dual-panel file manager
winget install MathiasSvensson.MultiCommander    # scriptable dual-pane file manager

# AI-assisted coding
winget install Anthropic.ClaudeCode
winget install OpenAI.Codex
winget install GitHub.Copilot
winget install Google.Antigravity

# Notes and knowledge
winget install Obsidian.Obsidian
winget install Logseq.Logseq

# Python and Node.js
winget install astral-sh.uv                      # Python versions, environments, packages and tools
winget install astral-sh.ruff                    # Python linter and formatter
winget install astral-sh.ty                      # Python type checker and language server (beta)
winget install Schniz.fnm                        # Node.js version manager
winget install jdx.mise                          # version manager for Node.js and other languages

# Go
winget install GoLang.Go                         # Go itself; switches toolchains per project
winget install GolangCI.golangci-lint            # runs Go linters in parallel, and formats code
winget install goreleaser.goreleaser             # release automation

# Rust: needs the MSVC build tools; see the Rust guide
winget install Rustlang.Rustup                   # Rust toolchains and components
winget install nextest.cargo-nextest             # faster test runner

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
winget install Neo4j.Neo4jDesktop
winget install DBeaver.DBeaver.Community         # 26.2.0 vs 26.2.3 on Chocolatey, 2026-10-21

# Web and APIs
winget install Bruno.Bruno
winget install Insomnia.Insomnia

# Data modelling (after installing uv above)
uv tool install --with jinja2-time copier        # creates LinkML projects from the template
uv tool install rust-just                        # task runner the template uses
uv tool install linkml                           # optional: LinkML commands outside a project
```

With Chocolatey, for tools winget lacks or only has as a preview. Install Chocolatey first (administrator PowerShell; see [Chocolatey](../tools/chocolatey.md)):

```powershell
choco install herdr                              # AI-assisted coding
choco install himalaya                           # email; or: scoop install himalaya
choco install hermes-desktop                     # personal AI agents
```

Delve, govulncheck, mypy, pytest, pre-commit, cargo-deny and cargo-audit have no winget package; install them with `go install`, uv or `cargo install` as their pages show. Himalaya has no winget package either; use Chocolatey or Scoop. The Neo4j server has no Windows package; use its zip or Docker. Qdrant has no winget or Chocolatey package; use Docker or the release zip. Colima doesn't run on Windows.

Every winget tool above except Multi Commander, ty and Neo4j Desktop also has a Chocolatey package (Insomnia's is years out of date); IDs are on each tool page. Watch for the name traps: `zed` (use `zed-editor`), `orca` and `nvm`.

These have no Chocolatey package: Octarine, Firefox Developer Edition, Orca (the `orca` package is Microsoft's MSI editor), VelaTerm, SilverBullet, OpenKnowledge, Protégé, VocBench and Pi. Install them from their websites. See [Windows platform tools](./windows-platform-tools.md) for the recommended shell setup.
