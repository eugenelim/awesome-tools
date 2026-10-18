---
type: Tool
title: Protégé
description: Free, open-source OWL 2 ontology editor from Stanford, available as a desktop app and as WebProtégé.
resource: https://protege.stanford.edu/
tags:
  - ontology
  - owl
  - rdf
  - semantic-web
  - open-source
platforms:
  - Java (platform independent)
  - Web
license: BSD-2-Clause-Views
sources:
  - id: protege
    resource: /sources/protege-homepage.md
    title: Protégé homepage, software page and licence
  - id: homebrew
    resource: /sources/homebrew-api-batch-3.md
    title: Homebrew API snapshot (batch 3)
---
# Protégé

A free, open-source OWL 2 ontology editor developed at Stanford University.[^protege] Ontologies in the OBO Foundry and the NCI Thesaurus are maintained with it, and the WHO used a WebProtégé-based environment to develop ICD-11.[^protege]

## Editions

| | Protégé Desktop | WebProtégé |
| --- | --- | --- |
| Runs | Locally; platform independent, requires Java | In the browser, hosted at Stanford |
| Focus | Reasoners (HermiT, Pellet), explanations, refactoring, multiple ontologies | Collaborative editing, permissions, discussions, revision history |
| Formats | OWL 2, RDF | RDF/XML, Turtle, OWL/XML, OBO and more |

Both editions are compatible with each other. The desktop app is written in Java with a plug-in architecture and is maintained by the community. The current version is 5.6.9.[^protege]

## Licence

A BSD 2-clause licence with an extra "views" clause (SPDX `BSD-2-Clause-Views`).[^protege]

## Install

Homebrew has a `protege` cask, but it is disabled: it failed Homebrew's Gatekeeper check on 2026-09-01.[^homebrew] Download Protégé Desktop from the Protégé website instead, or use WebProtégé in the browser.[^protege]

## See also

- [Ontology editors](../concepts/ontology-editors.md)
- [VocBench](./vocbench.md)

[^protege]: [Protégé homepage, software page and licence](../sources/protege-homepage.md)
[^homebrew]: [Homebrew API snapshot (batch 3)](../sources/homebrew-api-batch-3.md)
