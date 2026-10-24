---
type: Readme
title: Awesome tools
description: How to use and contribute to this OKF bundle of software tools.
---
# Awesome tools

A catalogue of software tools worth knowing about: developer tools, everyday apps and self-hosted services, on macOS, Windows, Linux and mobile. Each tool has its own page covering what it does, which platforms it runs on, its licence and pricing, and how to install it.

The repo is an [Open Knowledge Format](https://github.com/GoogleCloudPlatform/open-knowledge-format) (OKF) v0.2 bundle: plain Markdown files with YAML frontmatter, joined by ordinary relative links.

## Start here

- [index.md](./index.md): every page in the bundle.
- [Local machine setup](./concepts/local-machine-setup.md): essential tools first, then tools for each type of work, plus Homebrew and Windows install commands.
- [Python dev environments](./concepts/python-dev-environments.md): uv vs pyenv.
- [Node.js dev environments](./concepts/node-dev-environments.md): fnm, mise, nvm and Volta.
- [Go dev environments](./concepts/go-dev-environments.md): one Go install plus built-in toolchain switching.
- [LinkML dev environment](./concepts/linkml-dev-environment.md): uv, copier and just with the LinkML project template.

## Tools by category

Grouped like [index.md](./index.md) and the [overview](./concepts/local-machine-setup.md): essentials first, then by type of work.

| Group | Category | Tools |
| --- | --- | --- |
| Essentials: core setup | [Package managers](./concepts/package-managers.md) | [Homebrew](./tools/homebrew.md), [winget](./tools/winget.md), [Chocolatey](./tools/chocolatey.md) |
| Essentials: core setup | [Password managers](./concepts/password-managers.md) | [Bitwarden](./tools/bitwarden.md) |
| Essentials: core setup | [Terminal emulators](./concepts/terminal-emulators.md) | [Ghostty](./tools/ghostty.md) |
| Essentials: core setup | [Code editors](./concepts/code-editors.md) | [Zed](./tools/zed.md) |
| Essentials: core setup | [Git and GitHub tools](./concepts/git-tools.md) | [GitHub CLI (gh)](./tools/github-cli.md) |
| Essentials: core setup | [Windows platform tools](./concepts/windows-platform-tools.md) | [winget](./tools/winget.md), [Chocolatey](./tools/chocolatey.md), [WSL](./tools/wsl.md) |
| Essentials: command-line utilities | [Command-line utilities](./concepts/command-line-utilities.md) | [ripgrep (rg)](./tools/ripgrep.md), [fd](./tools/fd.md), [jq](./tools/jq.md), [tree](./tools/tree.md) |
| Essentials: everyday utilities | [Web browsers](./concepts/web-browsers.md) | [Firefox Developer Edition](./tools/firefox-developer-edition.md), [Rill](./tools/rill.md), [SigmaOS](./tools/sigmaos.md) |
| Essentials: everyday utilities | [File managers](./concepts/file-managers.md) | macOS: [Rascal](./tools/rascal.md), [Swift Salamander](./tools/swift-salamander.md). Windows: [FreeCommander](./tools/freecommander.md), [Multi Commander](./tools/multicommander.md), [OneCommander](./tools/onecommander.md) |
| Essentials: everyday utilities | [macOS utilities](./concepts/macos-utilities.md) | [Forel](./tools/forel.md), [Vorssaint](./tools/vorssaint.md), [Wick](./tools/wick.md) |
| Essentials: everyday utilities | [Health and fitness](./concepts/health-and-fitness.md) | [openGym](./tools/opengym.md) |
| AI-assisted coding | [AI coding agents](./concepts/ai-coding-agents.md) | [Claude Code](./tools/claude-code.md), [Codex](./tools/codex.md), [GitHub Copilot CLI](./tools/github-copilot.md), [Pi](./tools/pi.md) |
| AI-assisted coding | [Agentic development environments](./concepts/agentic-development-environments.md) | [Antigravity](./tools/antigravity.md), [herdr](./tools/herdr.md), [Orca](./tools/orca.md), [VelaTerm](./tools/velaterm.md) |
| Notes, knowledge and email | [Knowledge management](./concepts/knowledge-management.md) | [Logseq](./tools/logseq.md), [Obsidian](./tools/obsidian.md), [Octarine](./tools/octarine.md), [OpenKnowledge](./tools/openknowledge.md), [SilverBullet](./tools/silverbullet.md) |
| Notes, knowledge and email | [Email clients](./concepts/email-clients.md) | [Himalaya](./tools/himalaya.md) |
| Programming languages | [Python developer tools](./concepts/python-tools.md) | [mypy](./tools/mypy.md), [pre-commit](./tools/pre-commit.md), [pytest](./tools/pytest.md), [Ruff](./tools/ruff.md), [ty](./tools/ty.md) |
| Programming languages | [Go developer tools](./concepts/go-tools.md) | [Delve](./tools/delve.md), [golangci-lint](./tools/golangci-lint.md), [GoReleaser](./tools/goreleaser.md), [govulncheck](./tools/govulncheck.md) |
| Programming languages | [Rust developer tools](./concepts/rust-tools.md) | [cargo-audit](./tools/cargo-audit.md), [cargo-deny](./tools/cargo-deny.md), [cargo-nextest](./tools/cargo-nextest.md) |
| Containers and Kubernetes | [Containers](./concepts/containers.md) | [Colima](./tools/colima.md), [Docker CLI](./tools/docker-cli.md), [Helm](./tools/helm.md), [k9s](./tools/k9s.md), [kind](./tools/kind.md), [kubectl](./tools/kubectl.md), [kubectx and kubens](./tools/kubectx.md) |
| Databases and vector search | [Databases](./concepts/databases.md) | PostgreSQL: [PostgreSQL](./tools/postgresql.md), [Postgres.app](./tools/postgres-app.md), [pgAdmin 4](./tools/pgadmin.md), [pgcli](./tools/pgcli.md), [Postgres MCP Pro](./tools/postgres-mcp-pro.md). Vector search: [pgvector](./tools/pgvector.md), [Qdrant](./tools/qdrant.md). Neo4j: [Neo4j Community Edition](./tools/neo4j.md), [Cypher Shell](./tools/cypher-shell.md), [Neo4j Browser](./tools/neo4j-browser.md), [APOC Core](./tools/apoc.md), [Neo4j Desktop](./tools/neo4j-desktop.md). Both: [DBeaver Community](./tools/dbeaver.md) |
| Web, APIs and design | [API clients](./concepts/api-clients.md) | [Insomnia](./tools/insomnia.md), [Spectral](./tools/spectral.md) |
| Web, APIs and design | [Design tools](./concepts/design-tools.md) | [ImageOptim](./tools/imageoptim.md), [Paper](./tools/paper.md) |
| Ontologies and data modelling | [Ontology editors](./concepts/ontology-editors.md) | [Protégé](./tools/protege.md), [WebProtégé (self-hosted)](./tools/webprotege.md), [VocBench](./tools/vocbench.md) |
| Ontologies and data modelling | [Data modelling](./concepts/data-modelling.md) | [LinkML](./tools/linkml.md), [LinkML-Scala](./tools/linkml-scala.md), [LinkML-OWL](./tools/linkml-owl.md), [Schema Automator](./tools/schema-automator.md) |
| Personal AI agents | [Personal AI agents](./concepts/personal-ai-agents.md) | [Hermes Agent](./tools/hermes.md), [Muse](./tools/muse.md) |

## Using the bundle

- **On GitHub:** start from this page or `index.md` and follow the links.
- **Locally:** clone the repo and open the folder in any Markdown editor or OKF-aware tool.

```sh
git clone https://github.com/eugenelim/awesome-tools.git
```

- **With an agent:** point it at `index.md`. Every page has a `type` and a one-line `description` in its frontmatter.

## Layout

```text
index.md       OKF root index (okf_version: "0.2")
concepts/      categories (type: Category), guides (type: Guide), overview (type: Overview)
tools/         one page per tool (type: Tool)
```

## Tool page format

```yaml
---
type: Tool
title: Ghostty
description: Fast, feature-rich, native terminal emulator for macOS and Linux.
resource: https://ghostty.org/
tags: [terminal, macos, linux]
platforms: [macOS, Linux]
# license / pricing: added only when the source states them
sources:
  - id: ghostty
    resource: https://ghostty.org/docs/about
    title: Ghostty Docs and About Ghostty
---
```

The body has a summary, features, platforms, pricing where known, and an **Install** section with the Homebrew command, or a note when there isn't one. Claims are cited with footnotes whose labels match `sources[].id`.

## Sources

Every claim is cited to the vendor's own page, README, docs, or Homebrew or Chocolatey package page. Citations link to those URLs. The maintainer keeps text snapshots of each source in a local `sources/` folder, which is listed in `.gitignore` and not published.

Facts were captured in October 2026. Prices, versions and platform support change, so check the vendor site before you rely on them.

## Adding a tool

1. Read the vendor page or README. Optionally keep a snapshot in your local `sources/` folder (`type: Source`, `resource:` the URL, `retrieved:` an ISO 8601 timestamp).
2. Create `tools/<slug>.md` in the format above, citing source URLs in `sources` and footnotes. Leave out any field the source doesn't support.
3. Add the tool to its category page, the matching type-of-work section of the [overview](./concepts/local-machine-setup.md) and its install commands, [index.md](./index.md) and the table in this README.
4. Check Homebrew with `brew info --cask <name>` or `brew info <name>`. Watch for name collisions: `orca` and `copilot` are unrelated packages.
5. Check Chocolatey at `https://community.chocolatey.org/packages/<id>`. Only list a package whose project URL points at the vendor.

## Licence

The content is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](./LICENSE). You can reuse and adapt it if you credit this repository. Product names and the quoted vendor material belong to their owners.
