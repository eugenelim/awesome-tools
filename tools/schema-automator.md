---
type: Tool
title: Schema Automator
description: A LinkML project toolkit that drafts LinkML schemas from existing data and schemas, and enhances them.
resource: https://linkml.io/schema-automator/
tags:
  - data-modelling
  - schema
  - python
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: BSD-3-Clause
pricing: Free
sources:
  - id: automator
    resource: https://github.com/linkml/schema-automator
    title: linkml/schema-automator README
  - id: pypi
    resource: https://pypi.org/project/schema-automator/
    title: "PyPI: schema-automator"
---
# Schema Automator

A toolkit from the LinkML project that helps generate and enhance [LinkML](./linkml.md) schemas. Its command is `schemauto`. Licensed under BSD-3-Clause.[^automator]

- **Generalise:** infer a draft schema from a data file, such as a TSV.[^automator]
- **Import:** convert another schema format, such as JSON Schema, into LinkML.[^automator]
- **Annotate:** enhance an existing schema.[^automator]

Use it to start a schema from data or schemas you already have, then edit and validate the draft with the core tools.

## Install

```sh
uv tool install schema-automator   # or: pip install schema-automator
```

The README gives the pip command.[^automator] It needs Python 3.10 or later; on 2026-10-21 the latest release was 0.5.7.[^pypi]

## Use

```sh
schemauto generalize-tsv my-data.tsv > my-schema.yaml
schemauto import-json-schema their.schema.json > my-schema.yaml
schemauto annotate-schema my-schema.yaml
```

The commands are from the README; the full list is in the [CLI docs](https://linkml.io/schema-automator/cli).[^automator]

## See also

- [Data modelling](../concepts/data-modelling.md#linkml-tools-compared)
- [LinkML](./linkml.md)

[^automator]: [linkml/schema-automator README](https://github.com/linkml/schema-automator)
[^pypi]: PyPI: [schema-automator](https://pypi.org/project/schema-automator/) (0.5.7, requires Python 3.10+); checked 2026-10-21
