---
type: Tool
title: pytest
description: A Python testing framework that runs plain assert-based tests and scales to complex functional testing.
resource: https://pytest.org/
tags:
  - python
  - testing
  - library
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: MIT
pricing: Free
sources:
  - id: pytest
    resource: https://github.com/pytest-dev/pytest
    title: pytest-dev/pytest README
  - id: pytest-docs
    resource: https://docs.pytest.org/en/stable/getting-started.html
    title: pytest Get Started
  - id: uv-deps
    resource: https://docs.astral.sh/uv/concepts/projects/dependencies/#development-dependencies
    title: uv development dependencies and tools docs
  - id: packages
    resource: https://pypi.org/project/pytest/
    title: "PyPI: pytest; Homebrew: pytest"
---
# pytest

A Python testing framework that makes small tests easy to write and scales to complex functional testing of applications and libraries. Licensed under MIT.[^pytest]

- **Plain `assert`:** detailed output for failing `assert` statements, so you don't need `self.assert*` methods.[^pytest]
- **Auto-discovery** of test modules and functions.[^pytest]
- **Fixtures** manage test resources, from small to long-lived and parametrised.[^pytest]
- Runs `unittest` suites as they are, has over 1,300 plugins, and needs Python 3.10+ or PyPy3.[^pytest]

## Install

pytest is a library you install into each project, so there's no winget or Chocolatey package. A Homebrew formula exists, but it installs outside your project's environment.[^packages]

| Platform | Command |
| --- | --- |
| macOS, Windows, Linux | `uv add --dev pytest`, then `uv run pytest` |

The pytest docs install it with `pip install -U pytest`.[^pytest-docs] uv's docs use `uv add --dev pytest` as their development-dependency example, and say to run pytest with `uv run` rather than `uvx`, since it needs your project installed.[^uv-deps] On 2026-10-21, PyPI had 9.1.1.[^packages]

## Use

```python
# test_sample.py
def inc(x):
    return x + 1

def test_answer():
    assert inc(3) == 5
```

```sh
uv run pytest
```

The example is from the README, and fails on purpose to show the assertion output.[^pytest]

## See also

- [Python developer tools](../concepts/python-tools.md)
- [Python dev environments](../concepts/python-dev-environments.md)

[^pytest]: [pytest-dev/pytest README](https://github.com/pytest-dev/pytest)
[^pytest-docs]: [pytest: Get Started](https://docs.pytest.org/en/stable/getting-started.html)
[^uv-deps]: [uv: Development dependencies](https://docs.astral.sh/uv/concepts/projects/dependencies/#development-dependencies) and [Using tools](https://docs.astral.sh/uv/guides/tools/)
[^packages]: PyPI: [pytest](https://pypi.org/project/pytest/); Homebrew: [pytest](https://formulae.brew.sh/formula/pytest); versions checked 2026-10-21
