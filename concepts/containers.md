---
type: Category
title: Containers
description: Tools for building and running containers and working with Kubernetes.
---
# Containers

Tools for building and running containers and working with Kubernetes.

| Tool | Licence | macOS | Windows | Linux |
| --- | --- | --- | --- | --- |
| [Docker CLI](../tools/docker-cli.md) | Apache-2.0 | `brew install docker` + Colima | Docker Engine in WSL 2, or `choco install docker-cli` | Docker Engine |
| [kubectl](../tools/kubectl.md) | Apache-2.0 | `brew install kubectl` | `winget install -e --id Kubernetes.kubectl` | binary from dl.k8s.io |
| [Helm](../tools/helm.md) | Apache-2.0 | `brew install helm` | `winget install Helm.Helm` | `snap install helm --classic` |
| [k9s](../tools/k9s.md) | Apache-2.0 | `brew install k9s` | `winget install k9s` | |
| [kind](../tools/kind.md) | Apache-2.0 | `brew install kind` | `winget install Kubernetes.kind` | binary from kind.sigs.k8s.io |
| [kubectx and kubens](../tools/kubectx.md) | Apache-2.0 | `brew install kubectx` | `winget install --id ahmetb.kubectx` and `ahmetb.kubens` | `brew install kubectx` |

Docker Desktop needs a paid subscription for organisations with 250 or more employees or $10 million or more in annual revenue. The Docker CLI and Engine don't. See [Docker CLI](../tools/docker-cli.md#licensing-cli-and-engine-vs-docker-desktop).
