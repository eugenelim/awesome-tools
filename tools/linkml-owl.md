---
type: Tool
title: LinkML-OWL
description: A LinkML project tool that turns instance data into OWL ontologies, using mapping annotations in a LinkML schema.
resource: https://linkml.io/linkml-owl/
tags:
  - data-modelling
  - owl
  - ontology
  - linked-data
  - python
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
pricing: Free
sources:
  - id: owl
    resource: https://linkml.io/linkml-owl/
    title: LinkML-OWL documentation
  - id: usage
    resource: https://linkml.io/linkml-owl/usage/
    title: LinkML-OWL usage
  - id: repo
    resource: https://github.com/linkml/linkml-owl
    title: linkml/linkml-owl repository and pyproject
  - id: pypi
    resource: https://pypi.org/project/linkml-owl/
    title: "PyPI: linkml-owl"
---
# LinkML-OWL

A framework from the LinkML project for translating LinkML instance data into OWL ontologies, both classes (TBoxes) and individuals (ABoxes). It treats ontology elements, especially classes, as data that conforms to a schema.[^owl]

That's the opposite direction to the core `gen-owl` generator in [LinkML](./linkml.md), which turns the schema itself into OWL.[^repo] Use LinkML-OWL when you keep ontology terms in a spreadsheet or YAML file and want to build the ontology from them.

- **Inputs:** a LinkML schema with annotations that map data to OWL, plus data that conforms to it, in YAML, JSON, RDF or TSV.[^usage]
- **Output:** an OWL ontology, for example in Turtle.[^usage]
- **Command:** `linkml-data2owl`.[^repo] [^usage]

## Install

```sh
uv tool install linkml-owl   # or: pip install linkml-owl
```

The docs give the pip command.[^usage] It needs Python 3.10 or later. On 2026-10-21 the latest release was 0.5.0 (2026-03-19).[^pypi] The repository doesn't declare a licence that GitHub recognises, so check it before redistributing.[^repo]

## Use

```sh
linkml-data2owl -s my_schema.yaml my_data.tsv -o my_ontology.owl.ttl
linkml-data2owl --help
```

The command is from the usage docs.[^usage]

## See also

- [Data modelling](../concepts/data-modelling.md#linkml-tools-compared)
- [LinkML](./linkml.md)
- [Ontology editors](../concepts/ontology-editors.md)

[^owl]: [LinkML-OWL documentation](https://linkml.io/linkml-owl/)
[^usage]: [LinkML-OWL usage](https://linkml.io/linkml-owl/usage/)
[^repo]: [linkml/linkml-owl repository](https://github.com/linkml/linkml-owl) (pyproject command list; no licence detected by GitHub), and [linkml/linkml](https://github.com/linkml/linkml) for `gen-owl`; checked 2026-10-21
[^pypi]: PyPI: [linkml-owl](https://pypi.org/project/linkml-owl/) (0.5.0, requires Python 3.10+); checked 2026-10-21
