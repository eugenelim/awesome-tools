---
type: Tool
title: kubectl
description: The Kubernetes command-line tool for running commands against Kubernetes clusters.
resource: https://kubernetes.io/docs/reference/kubectl/
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
  - id: k8s-macos
    resource: https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
    title: Install and Set Up kubectl on macOS
  - id: k8s-windows
    resource: https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
    title: Install and Set Up kubectl on Windows
  - id: k8s-linux
    resource: https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
    title: Install and Set Up kubectl on Linux
  - id: packages
    resource: https://formulae.brew.sh/formula/kubernetes-cli
    title: "Homebrew: kubernetes-cli; winget: Kubernetes.kubectl; Chocolatey: kubernetes-cli"
---
# kubectl

The Kubernetes command-line tool. Kubernetes, which includes kubectl, is licensed under Apache-2.0.[^packages]

## Match your cluster's version

Use a kubectl version within one minor version of your cluster. For example, a v1.37 client can talk to v1.36, v1.37 and v1.38 control planes.[^k8s-macos] If you work with clusters on different versions, check `kubectl version` against each one.

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install kubectl` (same as `brew install kubernetes-cli`)[^k8s-macos] |
| Windows (recommended) | `winget install -e --id Kubernetes.kubectl`[^k8s-windows] |
| Windows (alternatives) | `choco install kubernetes-cli` or `scoop install kubectl`[^k8s-windows] |
| Linux | download the binary, as below[^k8s-linux] |

All three package managers had kubectl 1.37.1 on 2026-10-21.[^packages] On Windows, winget comes first, following this bundle's [winget-first recommendation](../concepts/windows-platform-tools.md#package-managers-winget-first-chocolatey-as-fallback).

**Linux** (x86-64; for ARM64, replace `amd64` with `arm64`), from the Kubernetes docs:[^k8s-linux]

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256) kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

Then check the installed client version:[^k8s-macos]

```sh
kubectl version --client
```

**Docker Desktop on Windows** adds its own kubectl to `PATH`. If you've installed Docker Desktop, put your kubectl's `PATH` entry before Docker Desktop's, or remove Docker Desktop's copy.[^k8s-windows] The [Docker CLI](./docker-cli.md) setup in this bundle doesn't use Docker Desktop.

## Shell autocompletion

**zsh** (macOS default): add this to `~/.zshrc`:[^k8s-macos]

```sh
source <(kubectl completion zsh)
```

If you get `command not found: compdef`, add these lines to the beginning of `~/.zshrc`:[^k8s-macos]

```sh
autoload -Uz compinit
compinit
```

**PowerShell:** add this line to your `$PROFILE`:[^k8s-windows]

```powershell
kubectl completion powershell | Out-String | Invoke-Expression
```

## See also

- [Containers](../concepts/containers.md)
- [Docker CLI](./docker-cli.md)

[^k8s-macos]: [Install and Set Up kubectl on macOS](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/)
[^k8s-windows]: [Install and Set Up kubectl on Windows](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/)
[^k8s-linux]: [Install and Set Up kubectl on Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
[^packages]: Homebrew: [kubernetes-cli](https://formulae.brew.sh/formula/kubernetes-cli); winget: [Kubernetes.kubectl](https://github.com/microsoft/winget-pkgs/tree/master/manifests/k/Kubernetes/kubectl); Chocolatey: [kubernetes-cli](https://community.chocolatey.org/packages/kubernetes-cli); licence from the [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) repository
