---
type: Tool
title: VocBench
description: Web-based, collaborative platform for managing OWL ontologies, SKOS(/XL) thesauri, OntoLex lexicons and RDF datasets.
resource: https://vocbench.uniroma2.it/
tags:
  - ontology
  - skos
  - rdf
  - semantic-web
  - open-source
platforms:
  - Java 17+
  - Docker
license: Open source
sources:
  - id: vocbench
    resource: https://vocbench.uniroma2.it/
    title: VocBench homepage, downloads and docs
  - id: homebrew
    resource: https://formulae.brew.sh/formula/openjdk@21
    title: "Homebrew: openjdk@21, openjdk@25, openjdk, neo4j"
---
# VocBench

A web-based, multilingual, collaborative platform for managing OWL ontologies, SKOS and SKOS-XL thesauri, OntoLex-lemon lexicons and other RDF datasets. It is free and open source.[^vocbench]

The ART Research Group at the University of Rome Tor Vergata builds it on its Semantic Turkey platform. Development is managed by the Publications Office of the EU and funded by the Digital Europe Programme; the European Commission's ISA² programme funded it originally.[^vocbench]

## Install

VocBench has no Homebrew package.[^homebrew] It needs Java 17 or later.[^vocbench] Use Homebrew's `openjdk@21` (21.0.13 on 2026-10-24). If you've installed [Neo4j](./neo4j.md) or [Cypher Shell](./cypher-shell.md) with Homebrew, you already have it: both depend on `openjdk@21`. Homebrew also has newer JDKs, `openjdk@25` and `openjdk` (27).[^homebrew]

```sh
brew install openjdk@21      # skip if Neo4j is installed
```

The formula is keg-only, so `java` isn't on `PATH`. For the system Java wrappers to find it, Homebrew says to symlink it:[^homebrew]

```sh
sudo ln -sfn "$(brew --prefix)/opt/openjdk@21/libexec/openjdk.jdk" /Library/Java/JavaVirtualMachines/openjdk-21.jdk
```

Then:[^vocbench]

1. Download the VocBench 3 standalone distribution from its Bitbucket page and unzip it.
2. Run `bin/semanticturkey.sh`, or `semanticturkey.bat` on Windows.
3. Open http://localhost:1979/vocbench3 in a browser.

There is also a Docker distribution.[^vocbench]

## See also

- [Ontology editors](../concepts/ontology-editors.md)
- [Protégé](./protege.md)
- [WebProtégé (self-hosted)](./webprotege.md)

[^vocbench]: [VocBench homepage](https://vocbench.uniroma2.it/), [downloads](https://vocbench.uniroma2.it/downloads/) and [docs](https://vocbench.uniroma2.it/doc/)
[^homebrew]: Homebrew: [openjdk@21](https://formulae.brew.sh/formula/openjdk@21) (keg-only; caveats), [openjdk@25](https://formulae.brew.sh/formula/openjdk@25), [openjdk](https://formulae.brew.sh/formula/openjdk) and [neo4j](https://formulae.brew.sh/formula/neo4j) dependencies, checked 2026-10-24; no VocBench package in the [catalogue](https://formulae.brew.sh/)
