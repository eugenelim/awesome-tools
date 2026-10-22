---
type: Tool
title: LinkML-Scala
description: NeverBlink's independent LinkML implementation, with a browser playground, native CLI binaries, and JVM, JavaScript and Python libraries.
resource: https://linkml.neverblink.eu/
tags:
  - data-modelling
  - schema
  - linked-data
  - scala
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
  - Browser
license: Apache-2.0
pricing: Free
sources:
  - id: scala
    resource: https://github.com/NeverBlink-OSS/linkml-scala
    title: NeverBlink-OSS/linkml-scala README
  - id: differences
    resource: https://github.com/NeverBlink-OSS/linkml-scala/blob/main/docs/implementation_differences.md
    title: LinkML-Scala implementation differences
  - id: releases
    resource: https://github.com/NeverBlink-OSS/linkml-scala/releases
    title: NeverBlink-OSS/linkml-scala releases
---
# LinkML-Scala

A second implementation of [LinkML](./linkml.md), written in Scala 3 by NeverBlink rather than by the LinkML project. It runs on the JVM, compiles to plain JavaScript for browsers and Node.js, and compiles to native binaries that need no Python or Java. Licensed under Apache-2.0.[^scala]

- **Playground:** validate a schema and run generators in the browser at [linkml.neverblink.eu/playground](https://linkml.neverblink.eu/playground/), with nothing to install.[^scala]
- **CLI:** `linkml-scala validate` (also `lint`) reports schema problems as fatal, error or warning, and can write a JSON report. `linkml-scala generate <format>` produces JSON Schema, OWL, SHACL, Apache Ossie and more, plus a flattened LinkML schema with imports resolved and unused elements pruned.[^scala]
- **Libraries:** `@neverblink/linkml` on npm (no runtime dependencies), `eu.neverblink.linkml` on Maven Central, and `neverblink-linkml` on PyPI, with a C ABI for C, C++ and Rust.[^scala]
- **CI:** a GitHub Action, `NeverBlink-OSS/linkml-scala-action`, validates and generates in pipelines.[^scala]
- **Speed:** its own benchmarks report it as 22.9 to 38.5 times faster than the Python implementation.[^scala]
- **Data validation:** decoding with the generated Scala classes validates data, and the generated JSON Schema, SHACL, TypeScript and Pydantic enforce extra-slot rules.[^differences]

## Differences from the Python implementation

It doesn't behave identically to the core Python tools. Compared with LinkML Python 1.12.1:[^differences]

- Arrays, rules, and enum inheritance and dynamic enums aren't supported.
- Default values (`ifabsent`), computed values and type designators are only partly supported, and some generators ignore boolean expressions.
- String-based enums aren't allowed, and `slot_usage` can turn `required` or `multivalued` on but not off.
- With `extra_slots`, extra data is validated but then dropped, so it doesn't survive a round trip.
- References are checked as soon as a schema loads, and import loops are rejected.

Check the full list before relying on it for a schema that the Python tools also process.

## Install

| Method | Command |
| --- | --- |
| macOS, Linux or WSL (script) | `. <(curl -sSfL https://raw.githubusercontent.com/NeverBlink-OSS/linkml-scala/refs/heads/main/cli/install.sh)` |
| Any platform (mise) | `mise use ubi:NeverBlink-OSS/linkml-scala` |
| Manual | download the binary for your OS from the releases page, rename it `linkml-scala` and make it executable |
| Python library | `pip install neverblink-linkml` |
| JavaScript library | `npm install @neverblink/linkml` |

Read the install script before running it. Releases ship a `SHA256SUMS` file and a signed build provenance attestation for checking downloads.[^scala] The JVM library needs JDK 17 or later.[^scala] Release binaries cover macOS (Apple silicon and Intel), Linux (x86-64 and ARM) and Windows x86-64; on 2026-10-21 the latest was v0.17.1 (2026-10-21).[^releases]

## Use

```sh
linkml-scala validate personinfo.yaml
linkml-scala generate json-schema personinfo.yaml
linkml-scala generate shacl personinfo.yaml
linkml-scala generate linkml --to flat.yaml personinfo.yaml   # resolve imports, prune unused
```

The commands are from the README.[^scala]

## See also

- [Data modelling](../concepts/data-modelling.md#linkml-tools-compared)
- [LinkML](./linkml.md), the core Python tools
- [LinkML dev environment](../concepts/linkml-dev-environment.md)

[^scala]: [NeverBlink-OSS/linkml-scala README](https://github.com/NeverBlink-OSS/linkml-scala)
[^differences]: [LinkML-Scala implementation differences](https://github.com/NeverBlink-OSS/linkml-scala/blob/main/docs/implementation_differences.md)
[^releases]: [NeverBlink-OSS/linkml-scala releases](https://github.com/NeverBlink-OSS/linkml-scala/releases); checked 2026-10-21
