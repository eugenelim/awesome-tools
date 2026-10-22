---
type: Category
title: Data modelling
description: Languages and tools for defining schemas and data models, generating code and validators from them, and comparing the LinkML tool families.
---
# Data modelling

Languages and tools for defining schemas and data models and generating code and validators from them. To set up a LinkML project, see [LinkML dev environment](./linkml-dev-environment.md). For OWL ontologies and SKOS vocabularies, see [Ontology editors](./ontology-editors.md).

| Tool | Maintainer | Licence | Install |
| --- | --- | --- | --- |
| [LinkML](../tools/linkml.md) (core Python tools: `linkml` CLI and generators) | LinkML project | Apache-2.0 | `uv tool install linkml` |
| [LinkML-Scala](../tools/linkml-scala.md) (playground, native CLI, JVM/JS/Python libraries) | NeverBlink | Apache-2.0 | `mise use ubi:NeverBlink-OSS/linkml-scala`, or the [browser playground](https://linkml.neverblink.eu/playground/) |
| [LinkML-OWL](../tools/linkml-owl.md) (instance data to OWL) | LinkML project | | `uv tool install linkml-owl` |
| [Schema Automator](../tools/schema-automator.md) (draft schemas from data and other schemas) | LinkML project | BSD-3-Clause | `uv tool install schema-automator` |

A blank cell means the source doesn't state it.

## LinkML tools compared

The four aren't alternatives to each other. The core Python tools are the reference implementation; LinkML-Scala is a second implementation of the same language; LinkML-OWL and Schema Automator are add-ons that cover one job each.

| | Core Python (`linkml`) | LinkML-Scala | LinkML-OWL | Schema Automator |
| --- | --- | --- | --- | --- |
| Role | Reference implementation | Independent reimplementation | Add-on: data to OWL | Add-on: build schemas |
| Runs on | Python 3.10+ | Native binary, browser, Node.js, JVM (JDK 17+), Python | Python 3.10+ | Python 3.10+ |
| Schema checks | `linkml-lint` | `linkml-scala validate`, with a JSON report | | |
| Data validation | `linkml-validate` | Through generated classes and schemas | | |
| Generators | About 40: JSON Schema, Pydantic, SQL, OWL, SHACL, ShEx, GraphQL, Java, Go, Rust, TypeScript, docs and diagrams | JSON Schema, OWL, SHACL, RDFS, Pydantic, TypeScript, GraphQL, Scala, Frictionless, ER diagrams, Ossie | | |
| Main command | `gen-*`, `linkml-validate`, `linkml-convert` | `linkml-scala` | `linkml-data2owl` | `schemauto` |
| Speed | Baseline | 22.9 to 38.5 times faster, by its own benchmarks | | |
| Feature coverage | Reference behaviour that the others are measured against | Gaps: arrays, rules, some enum and default-value features | | |

Sources are on each tool page: [LinkML](../tools/linkml.md), [LinkML-Scala](../tools/linkml-scala.md#differences-from-the-python-implementation), [LinkML-OWL](../tools/linkml-owl.md) and [Schema Automator](../tools/schema-automator.md). The LinkML-Scala generator list is its JavaScript library's; the CLI's full list is in `linkml-scala --help`.

## Which to use

- **Start with the core Python tools.** They're the LinkML project's own implementation, and the [project template](./linkml-dev-environment.md) builds on them.
- **Add LinkML-Scala** to try LinkML in a browser with nothing installed, to validate in CI or on machines without Python, to use LinkML from JavaScript or the JVM, or when the Python tools are too slow on a large schema. Check its [implementation differences](../tools/linkml-scala.md#differences-from-the-python-implementation) first if the same schema also goes through the Python tools.
- **Add Schema Automator** to draft a schema from existing TSV files or a JSON Schema, then refine it by hand.
- **Add LinkML-OWL** when the ontology itself lives as data, for example terms in a spreadsheet, and you want to generate OWL from it. To turn a schema into OWL, use the core `gen-owl` instead.
