---
type: Tool
title: Helm
description: The package manager for Kubernetes, which installs and manages applications packaged as charts.
resource: https://helm.sh/
tags:
  - kubernetes
  - containers
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: helm
    resource: https://github.com/helm/helm
    title: helm/helm README
  - id: packages
    resource: https://formulae.brew.sh/formula/helm
    title: "Homebrew: helm; winget: Helm.Helm; Chocolatey: kubernetes-helm"
---
# Helm

The package manager for Kubernetes; the project compares it to apt, yum or Homebrew for Kubernetes. Licensed under Apache-2.0.[^helm] [^packages]

- **Charts** are packages of pre-configured Kubernetes resources. Each holds a `Chart.yaml` description and one or more templates of Kubernetes manifests.[^helm]
- Helm renders the templates and sends them to the Kubernetes API, then manages the resulting **releases**.[^helm]
- Charts can be stored on disk or fetched from remote chart repositories. Artifact Hub lists published charts.[^helm]

## Versions

Helm v4 is the current stable release. Helm v3 is in support mode: bug fixes ended on 8 July 2026, and security fixes end on 11 November 2026.[^helm]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install helm` |
| Windows (recommended) | `winget install Helm.Helm` |
| Windows (alternatives) | `choco install kubernetes-helm` or `scoop install helm` |
| Linux | `snap install helm --classic`, or the binary from GitHub releases |

The install commands are from the Helm README.[^helm] On 2026-10-21, Homebrew and winget had 4.3.1 but Chocolatey had 4.1.4, so winget is the better choice on Windows.[^packages] Helm talks to the cluster in your current [kubectl](./kubectl.md) context.

## See also

- [Containers and Kubernetes](../concepts/containers.md)
- [kubectl](./kubectl.md)

[^helm]: [helm/helm README](https://github.com/helm/helm)
[^packages]: Homebrew: [helm](https://formulae.brew.sh/formula/helm); winget: [Helm.Helm](https://github.com/microsoft/winget-pkgs/tree/master/manifests/h/Helm/Helm); Chocolatey: [kubernetes-helm](https://community.chocolatey.org/packages/kubernetes-helm); versions checked 2026-10-21
