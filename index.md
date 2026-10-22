---
okf_version: "0.2"
---
# Awesome tools

Software tools worth knowing about (developer tools, everyday apps and self-hosted services), as an [Open Knowledge Format](https://github.com/GoogleCloudPlatform/open-knowledge-format) v0.2 bundle. Tool concepts are in `tools/` and categories in `concepts/`.

## Overview

- [Local machine setup](./concepts/local-machine-setup.md): essential tools first, then tools for each type of work, with platforms, licences and install commands.

## Guides

- [Python dev environments](./concepts/python-dev-environments.md): uv vs pyenv for switching Python versions (recommends uv).
- [Node.js dev environments](./concepts/node-dev-environments.md): fnm, mise, nvm and Volta for switching Node.js versions (recommends fnm).
- [Go dev environments](./concepts/go-dev-environments.md): one Go install plus built-in toolchain switching (no version manager needed).
- [LinkML dev environment](./concepts/linkml-dev-environment.md): uv, copier and just with the linkml-project-copier template (recommended), or LinkML on its own.

## Categories

Grouped like the [overview](./concepts/local-machine-setup.md): essentials first, then by type of work.

### Essentials: core setup

- [Package managers](./concepts/package-managers.md): Homebrew, winget and Chocolatey, with everyday commands side by side.
- [Password managers](./concepts/password-managers.md): encrypted credential vaults.
- [Terminal emulators](./concepts/terminal-emulators.md): applications that host shell sessions.
- [Code editors](./concepts/code-editors.md): editors and IDEs for source code.
- [Git and GitHub tools](./concepts/git-tools.md): command-line tools for Git and GitHub.
- [Windows platform tools](./concepts/windows-platform-tools.md): winget vs Chocolatey recommendation, WSL and shell setup for Windows.

### Essentials: everyday utilities

- [Web browsers](./concepts/web-browsers.md): browsers, including developer builds.
- [File managers](./concepts/file-managers.md): Finder and File Explorer alternatives.
- [macOS utilities](./concepts/macos-utilities.md): small single-purpose Mac apps.
- [Health and fitness](./concepts/health-and-fitness.md): training and body-weight tracking.

### AI-assisted coding

- [AI coding agents](./concepts/ai-coding-agents.md): command-line agents that read, edit and run code.
- [Agentic development environments](./concepts/agentic-development-environments.md): running and supervising multiple AI coding agents.

### Programming languages

- [Python developer tools](./concepts/python-tools.md): linting, formatting, type checking, testing and Git hooks for Python.
- [Go developer tools](./concepts/go-tools.md): linting, debugging, vulnerability scanning and releases for Go.

### Containers and Kubernetes

- [Containers](./concepts/containers.md): containers and Kubernetes.

### Databases and vector search

- [Databases](./concepts/databases.md): PostgreSQL, Neo4j and vector search servers, clients, extensions and MCP servers.

### Web, APIs and design

- [API clients](./concepts/api-clients.md): sending, testing and designing API requests.
- [Design tools](./concepts/design-tools.md): interface design and prototyping.

### Notes, knowledge and email

- [Knowledge management](./concepts/knowledge-management.md): Markdown-based notes and wikis.
- [Email clients](./concepts/email-clients.md): applications for reading, searching and sending email.

### Ontologies and data modelling

- [Ontology editors](./concepts/ontology-editors.md): OWL ontologies, SKOS thesauri and RDF vocabularies.
- [Data modelling](./concepts/data-modelling.md): schema languages such as LinkML, and the code and validators generated from them.

### Personal AI agents

- [Personal AI agents](./concepts/personal-ai-agents.md): agents that run everyday tasks and goals for you.

## Tools

- [Antigravity](./tools/antigravity.md): Google's desktop app for orchestrating parallel AI agents.
- [APOC Core](./tools/apoc.md): library of Cypher procedures and functions that ships with Neo4j.
- [Bitwarden](./tools/bitwarden.md): open-source password manager.
- [Chocolatey](./tools/chocolatey.md): package manager for Windows.
- [Claude Code](./tools/claude-code.md): Anthropic's agentic coding tool for the terminal.
- [Codex](./tools/codex.md): OpenAI's open-source terminal coding agent.
- [Colima](./tools/colima.md): Docker, containerd or Incus in a Lima VM on macOS and Linux.
- [Cypher Shell](./tools/cypher-shell.md): command-line client for running Cypher against Neo4j.
- [DBeaver Community](./tools/dbeaver.md): open-source desktop SQL client for 100+ databases.
- [Delve](./tools/delve.md): debugger for Go (`dlv`).
- [Docker CLI](./tools/docker-cli.md): open-source container CLI; licensing vs Docker Desktop.
- [Firefox Developer Edition](./tools/firefox-developer-edition.md): Firefox with beta DevTools and developer defaults.
- [Forel](./tools/forel.md): open-source folder automation for macOS (Hazel alternative).
- [FreeCommander](./tools/freecommander.md): free dual-panel Windows file manager.
- [Ghostty](./tools/ghostty.md): native, GPU-accelerated terminal emulator.
- [GitHub CLI (gh)](./tools/github-cli.md): GitHub's official command-line tool.
- [GitHub Copilot CLI](./tools/github-copilot.md): Copilot's coding agent in the terminal.
- [golangci-lint](./tools/golangci-lint.md): runs Go linters in parallel, and formats code.
- [GoReleaser](./tools/goreleaser.md): release automation for Go and other languages; paid Pro edition.
- [govulncheck](./tools/govulncheck.md): the Go project's tool for finding known vulnerabilities your code reaches.
- [Helm](./tools/helm.md): the package manager for Kubernetes, using charts.
- [herdr](./tools/herdr.md): terminal agent multiplexer with a background server.
- [Hermes Agent](./tools/hermes.md): Nous Research's open-source, self-hosted personal agent.
- [Himalaya](./tools/himalaya.md): command-line email client for IMAP, SMTP, JMAP, Gmail and Microsoft Graph.
- [Homebrew](./tools/homebrew.md): package manager for macOS and Linux, with setup and common commands.
- [Insomnia](./tools/insomnia.md): Kong's open-source API client for REST, GraphQL, gRPC, WebSockets and SSE.
- [k9s](./tools/k9s.md): terminal UI for Kubernetes clusters.
- [kind](./tools/kind.md): local Kubernetes clusters in Docker containers.
- [kubectl](./tools/kubectl.md): the Kubernetes command-line tool.
- [kubectx and kubens](./tools/kubectx.md): fast switching of kubectl contexts and namespaces.
- [LinkML](./tools/linkml.md): YAML data modelling language and its core Python tools, which generate JSON Schema, Pydantic, SQL, OWL and SHACL.
- [LinkML-OWL](./tools/linkml-owl.md): turns LinkML instance data into OWL ontologies.
- [LinkML-Scala](./tools/linkml-scala.md): independent LinkML implementation with a browser playground, native CLI and JVM/JS/Python libraries.
- [Logseq](./tools/logseq.md): open-source knowledge base for Markdown and Org-mode.
- [Multi Commander](./tools/multicommander.md): free, scriptable dual-pane Windows file manager.
- [Muse](./tools/muse.md): Meta's hosted personal AI agent.
- [mypy](./tools/mypy.md): stable static type checker for Python.
- [Neo4j Browser](./tools/neo4j-browser.md): web UI that ships with the Neo4j server.
- [Neo4j Community Edition](./tools/neo4j.md): open-source, single-instance graph database queried with Cypher.
- [Neo4j Desktop](./tools/neo4j-desktop.md): free app for local Neo4j databases, running Enterprise Edition under a developer licence.
- [Obsidian](./tools/obsidian.md): local-first Markdown notes.
- [Octarine](./tools/octarine.md): private Markdown notes app with a one-time licence.
- [OneCommander](./tools/onecommander.md): modern Windows Explorer alternative with Miller columns.
- [openGym](./tools/opengym.md): self-hosted gym and body-weight tracker.
- [OpenKnowledge](./tools/openknowledge.md): WYSIWYG Markdown editor and knowledge base for humans and agents.
- [Orca](./tools/orca.md): ADE for parallel agents in git worktrees.
- [Paper](./tools/paper.md): design tool with an HTML/CSS canvas that agents can edit through MCP.
- [pgAdmin 4](./tools/pgadmin.md): administration and development GUI for PostgreSQL.
- [pgcli](./tools/pgcli.md): PostgreSQL terminal client with auto-completion and syntax highlighting.
- [pgvector](./tools/pgvector.md): vector similarity search extension for PostgreSQL.
- [Postgres MCP Pro](./tools/postgres-mcp-pro.md): PostgreSQL MCP server for AI agents, with query plans, index tuning and health checks.
- [Pi](./tools/pi.md): minimal, extensible coding agent CLI.
- [Postgres.app](./tools/postgres-app.md): PostgreSQL packaged as a native macOS app.
- [PostgreSQL](./tools/postgresql.md): open-source relational database server, with the psql client.
- [pre-commit](./tools/pre-commit.md): framework for multi-language Git pre-commit hooks.
- [Protégé](./tools/protege.md): Stanford's open-source OWL 2 ontology editor.
- [Qdrant](./tools/qdrant.md): open-source vector database, with an official MCP server.
- [pytest](./tools/pytest.md): Python testing framework with plain asserts and fixtures.
- [Rascal](./tools/rascal.md): free, open-source keyboard-first Finder replacement.
- [Rill](./tools/rill.md): macOS browser (beta) that hands tasks to your Claude Code or Codex.
- [Ruff](./tools/ruff.md): Python linter and formatter from Astral.
- [Schema Automator](./tools/schema-automator.md): drafts LinkML schemas from TSV data or JSON Schema (`schemauto`).
- [SigmaOS](./tools/sigmaos.md): WebKit-based macOS browser with workspaces and an AI assistant.
- [SilverBullet](./tools/silverbullet.md): open-source, scriptable Markdown knowledge base.
- [Swift Salamander](./tools/swift-salamander.md): dual-pane file manager for macOS.
- [ty](./tools/ty.md): Astral's Python type checker and language server (beta).
- [VelaTerm](./tools/velaterm.md): terminal and coding-agent manager.
- [VocBench](./tools/vocbench.md): collaborative web platform for OWL, SKOS and RDF.
- [Vorssaint](./tools/vorssaint.md): free, open-source macOS menu bar toolkit.
- [Wick](./tools/wick.md): timers, stopwatch and alarms for Mac.
- [winget](./tools/winget.md): Windows Package Manager, built into Windows 10 1809+ and 11, with setup and common commands.
- [WSL](./tools/wsl.md): Windows Subsystem for Linux.
- [Zed](./tools/zed.md): high-performance, multiplayer code editor.
