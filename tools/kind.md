---
type: Tool
title: kind
description: Runs local Kubernetes clusters using Docker containers as nodes, for testing, local development and CI.
resource: https://kind.sigs.k8s.io/
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
  - id: kind
    resource: https://github.com/kubernetes-sigs/kind
    title: kubernetes-sigs/kind README
  - id: packages
    resource: https://formulae.brew.sh/formula/kind
    title: "Homebrew: kind; winget: Kubernetes.kind; Chocolatey: kind"
---
# kind

**K**ubernetes **in** **D**ocker: runs local Kubernetes clusters with Docker containers as the "nodes". It was built mainly to test Kubernetes itself, but also suits local development and CI. It's a Kubernetes SIGs project under Apache-2.0.[^kind] [^packages]

It needs a container engine: Docker, Podman or nerdctl.[^kind] On a Mac without Docker Desktop, use the [Docker CLI with Colima](./docker-cli.md#macos-docker-cli--colima).

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install kind`[^kind] |
| Windows (recommended) | `winget install Kubernetes.kind`[^packages] |
| Windows (alternative) | `choco install kind`[^kind] |
| Linux | binary from the kind site (below)[^kind] |
| Any, with Go | `go install sigs.k8s.io/kind@v0.33.0`[^kind] |

**Linux**, from the kind README:[^kind]

```bash
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.33.0/kind-$(uname)-amd64
# For ARM64
[ $(uname -m) = aarch64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.33.0/kind-$(uname)-arm64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```

All three package managers had 0.33.0 on 2026-10-21.[^packages]

## Use

```sh
kind create cluster
kind delete cluster
```

Once the cluster exists, use [kubectl](./kubectl.md) against it. The project notes that kind is still a work in progress towards 1.0.[^kind]

## See also

- [Containers and Kubernetes](../concepts/containers.md)

[^kind]: [kubernetes-sigs/kind README](https://github.com/kubernetes-sigs/kind)
[^packages]: Homebrew: [kind](https://formulae.brew.sh/formula/kind); winget: [Kubernetes.kind](https://github.com/microsoft/winget-pkgs/tree/master/manifests/k/Kubernetes/kind); Chocolatey: [kind](https://community.chocolatey.org/packages/kind); versions checked 2026-10-21
