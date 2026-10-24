---
type: Tool
title: Spectral
description: Stoplight's open-source JSON and YAML linter, with ready-made rulesets for OpenAPI, AsyncAPI and Arazzo and custom rules for API style guides.
resource: https://github.com/stoplightio/spectral
tags:
  - api
  - openapi
  - linter
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: spectral
    resource: https://github.com/stoplightio/spectral
    title: stoplightio/spectral README, LICENSE and releases
  - id: packages
    resource: https://formulae.brew.sh/formula/spectral-cli
    title: "Homebrew: spectral-cli; winget: Stoplight.Spectral"
---
# Spectral

A JSON and YAML linter from Stoplight. Its ready-made rulesets validate and lint OpenAPI 2, 3.0, 3.1 and 3.2, AsyncAPI and Arazzo 1 documents, and you can write your own rules and functions to enforce an API style guide. Licensed under Apache-2.0.[^spectral]

- **Rulesets:** Spectral needs a ruleset to lint anything. A ruleset is a JSON, YAML or JavaScript/TypeScript file, usually `.spectral.yaml`.[^spectral]
- **Where to run it:** in editors, Git hooks, CI and GitHub Actions, or from JavaScript.[^spectral]
- **Shared rulesets:** Stoplight's API Stylebook has style guides you can export as Spectral files, including OWASP Top 10 API security rules.[^spectral]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install spectral-cli` |
| Any (Node.js) | `npm install -g @stoplight/spectral-cli` |
| Windows | `spectral.exe` from the GitHub releases, or npm |
| Docker | `docker run --rm -it -v $(pwd):/tmp stoplight/spectral lint --ruleset "/tmp/.spectral.yaml" "/tmp/file.yaml"` |

npm is the README's recommended install. Releases also have standalone binaries for macOS, Linux and Windows.[^spectral] On 2026-10-24 Homebrew had 6.17.0, the latest release, and it depends on Node.js. Homebrew lists the licence as MIT, but the repository's licence is Apache-2.0. winget's `Stoplight.Spectral` is stuck at 6.9.0, so it isn't listed.[^packages]

The Docker image sends an anonymous telemetry ping (version and platform) on startup; set `DO_NOT_TRACK=1` to turn it off.[^spectral]

## Use

From the README:[^spectral]

```sh
echo 'extends: ["spectral:oas", "spectral:asyncapi", "spectral:arazzo"]' > .spectral.yaml
spectral lint myapifile.yaml                          # uses .spectral.yaml in this folder
spectral lint myapifile.yaml --ruleset myruleset.yaml # or a ruleset elsewhere
```

## See also

- [API clients](../concepts/api-clients.md)
- [Insomnia](./insomnia.md)

[^spectral]: [stoplightio/spectral README](https://github.com/stoplightio/spectral), [LICENSE](https://github.com/stoplightio/spectral/blob/develop/LICENSE) and [releases](https://github.com/stoplightio/spectral/releases); v6.17.0 checked 2026-10-24
[^packages]: Homebrew: [spectral-cli](https://formulae.brew.sh/formula/spectral-cli); winget: [Stoplight.Spectral](https://github.com/microsoft/winget-pkgs/tree/master/manifests/s/Stoplight/Spectral); checked 2026-10-24
