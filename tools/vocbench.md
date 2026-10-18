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
    resource: https://formulae.brew.sh/formula/openjdk@17
    title: "Homebrew: openjdk@17"
---
# VocBench

A web-based, multilingual, collaborative platform for managing OWL ontologies, SKOS and SKOS-XL thesauri, OntoLex-lemon lexicons and other RDF datasets. It is free and open source.[^vocbench]

The ART Research Group at the University of Rome Tor Vergata builds it on its Semantic Turkey platform. Development is managed by the Publications Office of the EU and funded by the Digital Europe Programme; the European Commission's ISA² programme funded it originally.[^vocbench]

## Install

VocBench has no Homebrew package.[^homebrew] It needs Java 17 or later,[^vocbench] which Homebrew provides as `openjdk@17`.[^homebrew]

```sh
brew install openjdk@17
```

Then:[^vocbench]

1. Download the VocBench 3 standalone distribution from its Bitbucket page and unzip it.
2. Run `bin/semanticturkey.sh`, or `semanticturkey.bat` on Windows.
3. Open http://localhost:1979/vocbench3 in a browser.

There is also a Docker distribution.[^vocbench]

## See also

- [Ontology editors](../concepts/ontology-editors.md)
- [Protégé](./protege.md)

[^vocbench]: [VocBench homepage](https://vocbench.uniroma2.it/), [downloads](https://vocbench.uniroma2.it/downloads/) and [docs](https://vocbench.uniroma2.it/doc/)
[^homebrew]: [Homebrew: openjdk@17](https://formulae.brew.sh/formula/openjdk@17); no VocBench package in the [catalogue](https://formulae.brew.sh/)
