---
type: Guide
title: LinkML dev environment
description: "Setting up a LinkML project: uv, copier and just, the linkml-project-copier template, and the validate, test and docs loop."
---
# LinkML dev environment

How to set up a machine and a project for writing [LinkML](../tools/linkml.md) schemas.

**Recommendation:** for a schema you'll keep, generate the project from the official `linkml-project-copier` template. It sets up uv, tests, linting, pre-commit and documentation published to GitHub Pages. For a quick experiment, install LinkML on its own with uv.

## 1. One-time machine setup

The template needs Git and a GitHub account, Python 3.10 or later, and uv, copier and just.[^copier]

1. Install uv; see [Python dev environments](./python-dev-environments.md). uv also installs Python for you.
2. Install copier, which generates and later updates projects from the template, with the `jinja2-time` extension it needs:[^copier]

   ```sh
   uv tool install --with jinja2-time copier
   ```

3. Install just, the command runner the generated project uses:[^copier]

   ```sh
   uv tool install rust-just
   ```

4. Optionally install [pre-commit](../tools/pre-commit.md) to run the project's checks on every commit:[^copier]

   ```sh
   uv tool install pre-commit --with pre-commit-uv
   ```

Behind a private PyPI mirror, point uv at it, for example `export UV_DEFAULT_INDEX=https://nexus.example.com/repository/pypi-all/simple`.[^copier]

## 2. Create a project

In a new, empty folder:[^copier]

```sh
mkdir my-schema && cd my-schema
copier copy --trust https://github.com/linkml/linkml-project-copier .
just setup
```

`--trust` is needed because the template uses the `jinja2_time` extension. The defaults suit most projects, but choose the project name carefully; it's also used as the GitHub repository name. New projects default to the Apache-2.0 licence. On WSL 2, run `export JUST_TEMPDIR=/tmp` first.[^copier]

The schema is the YAML file in `src/<project_name>/schema/`. Generator options go in `config.yaml`.[^copier]

## 3. Day-to-day loop

| Command | What it does |
| --- | --- |
| `just test` | Generate the artifacts from the schema, run pytest on the Python model, and load every valid and invalid example |
| `just lint` | Run the LinkML linter on the schema |
| `just testdoc` | Build and preview the documentation locally |
| `pre-commit install` | Run yamllint, Ruff, codespell and typos on every commit |
| `pre-commit run -a` | Run those checks on demand |

All commands are from the template's README.[^copier] To publish, create an empty GitHub repository (no README or `.gitignore`), push, then enable the "Deploy docs" workflow and GitHub Pages from the `gh-pages` branch, as the README describes.[^copier]

## Without the template

For a quick try, or to add LinkML to an existing Python project:

```sh
uv init linkml-sandbox && cd linkml-sandbox
uv add linkml
uv run linkml-validate -s personinfo.yaml data.yaml
uv run gen-pydantic personinfo.yaml > models.py
```

`uv add` makes LinkML a project dependency, so everyone on the project gets the same version; `uv run` runs its commands in the project environment. To run LinkML without Python at all, use the Docker image; see [LinkML](../tools/linkml.md#install).

## Add-ons and alternatives

- [Schema Automator](../tools/schema-automator.md): draft the first schema from existing TSV files or a JSON Schema with `schemauto`, then refine it in the project.
- [LinkML-OWL](../tools/linkml-owl.md): build an OWL ontology from instance data with `linkml-data2owl`.
- [LinkML-Scala](../tools/linkml-scala.md): try schemas in a browser playground, or validate in CI without Python; it differs from the Python tools in places.

All three are compared with the core tools in [Data modelling](./data-modelling.md#linkml-tools-compared). Install the Python ones with `uv tool install`, or `uv add --dev` to pin them in the project.

## See also

- [LinkML](../tools/linkml.md)
- [Data modelling](./data-modelling.md)
- [Python dev environments](./python-dev-environments.md)

[^copier]: [linkml/linkml-project-copier README](https://github.com/linkml/linkml-project-copier)
