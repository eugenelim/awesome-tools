---
type: Tool
title: LinkML
description: The Linked Data Modeling Language and its Python toolkit, which validates YAML schemas and generates JSON Schema, Pydantic, SQL, OWL, SHACL and docs from them.
resource: https://linkml.io/
tags:
  - data-modelling
  - schema
  - linked-data
  - rdf
  - python
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: linkml
    resource: https://github.com/linkml/linkml
    title: linkml/linkml README and pyproject
  - id: install
    resource: https://linkml.io/linkml/intro/install.html
    title: LinkML installation docs
  - id: tutorial
    resource: https://linkml.io/linkml/intro/tutorial01.html
    title: LinkML tutorial part 1
  - id: pypi
    resource: https://pypi.org/project/linkml/
    title: "PyPI: linkml"
  - id: runtime
    resource: https://github.com/linkml/linkml-runtime
    title: linkml/linkml-runtime README
  - id: automator
    resource: https://github.com/linkml/schema-automator
    title: linkml/schema-automator
---
# LinkML

A data modelling language that follows object-oriented and ontological principles. You write models in YAML and convert them to other schema formats, such as JSON Schema or RDF. The `linkml` package holds the tools; it's licensed under Apache-2.0.[^linkml]

- **Generators:** one schema produces JSON Schema (`gen-json-schema`), Pydantic and Python classes (`gen-pydantic`, `gen-python`), SQL DDL and SQLAlchemy (`gen-sqlddl`, `gen-sqla`), OWL (`gen-owl`), SHACL and ShEx (`gen-shacl`, `gen-shex`), JSON-LD contexts, GraphQL, Protobuf, TypeScript, Java, Go, Rust, Excel templates, Mermaid and PlantUML diagrams, and Markdown docs (`gen-doc`).[^linkml]
- **Validation:** `linkml-validate` checks data files against a schema.[^tutorial]
- **Conversion:** `linkml-convert` turns data between YAML, JSON and RDF formats such as Turtle.[^tutorial]
- **Linting:** `linkml-lint` checks a schema for problems.[^linkml]
- **Runtime:** `linkml-runtime`, the library generated code depends on, moved into the main `linkml` repository on 2025-12-01; its old repository is archived.[^runtime]

Schema Automator (BSD-3-Clause) is a separate LinkML project for automated help across the schema development lifecycle.[^automator]

## Install

It needs Python 3.10 or later. On 2026-10-21 the latest release on PyPI was 1.12.1.[^pypi]

| Method | Command |
| --- | --- |
| Project dependency (uv) | `uv add linkml` |
| Global command (uv) | `uv tool install linkml` |
| pip | `pip install linkml` |
| Docker | `docker run -v ./:/work -w /work/ --rm -ti docker.io/linkml/linkml` |

LinkML's docs give the pip and Docker commands.[^install] For a full project setup with uv, see [LinkML dev environment](../concepts/linkml-dev-environment.md). There's no Homebrew package; use uv on every platform.

## Use

```yaml
# personinfo.yaml
id: https://w3id.org/linkml/examples/personinfo
name: personinfo
prefixes:
  linkml: https://w3id.org/linkml/
  personinfo: https://w3id.org/linkml/examples/personinfo
imports:
  - linkml:types
default_range: string
default_prefix: personinfo
classes:
  Person:
    attributes:
      id:
      full_name:
      age:
```

```sh
linkml-validate -s personinfo.yaml data.yaml     # check data against the schema
gen-json-schema personinfo.yaml > personinfo.schema.json
linkml-convert -s personinfo.yaml data.yaml -t ttl  # data as RDF Turtle
```

The example is adapted from part 1 of the LinkML tutorial.[^tutorial]

## See also

- [LinkML dev environment](../concepts/linkml-dev-environment.md)
- [Data modelling](../concepts/data-modelling.md)
- [Ontology editors](../concepts/ontology-editors.md)

[^linkml]: [linkml/linkml README](https://github.com/linkml/linkml) and [package pyproject](https://github.com/linkml/linkml/blob/main/packages/linkml/pyproject.toml) (command list)
[^install]: [LinkML installation docs](https://linkml.io/linkml/intro/install.html)
[^tutorial]: [LinkML tutorial part 1](https://linkml.io/linkml/intro/tutorial01.html)
[^pypi]: PyPI: [linkml](https://pypi.org/project/linkml/) (1.12.1, requires Python 3.10+); checked 2026-10-21
[^runtime]: [linkml/linkml-runtime README](https://github.com/linkml/linkml-runtime)
[^automator]: Schema Automator repository: [linkml/schema-automator](https://github.com/linkml/schema-automator)
