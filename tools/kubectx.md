---
type: Tool
title: kubectx and kubens
description: Two small tools for switching kubectl contexts (clusters) and namespaces quickly.
resource: https://kubectx.dev/
tags:
  - kubernetes
  - cli
  - open-source
platforms:
  - macOS
  - Windows
  - Linux
license: Apache-2.0
pricing: Free
sources:
  - id: kubectx
    resource: https://github.com/ahmetb/kubectx
    title: ahmetb/kubectx README
  - id: packages
    resource: https://formulae.brew.sh/formula/kubectx
    title: "Homebrew: kubectx; winget: ahmetb.kubectx, ahmetb.kubens; Chocolatey: kubectx, kubens"
---
# kubectx and kubens

Two tools from one repository, licensed under Apache-2.0:[^kubectx] [^packages]

- **kubectx** switches between kubectl contexts (clusters) and can open read-only or isolated shells for one context.
- **kubens** switches the active namespace.

## Install

| Platform | Command |
| --- | --- |
| macOS and Linux | `brew install kubectx` (installs both) |
| Windows (recommended) | `winget install --id ahmetb.kubectx && winget install --id ahmetb.kubens` |
| Windows (alternatives) | `choco install kubens kubectx`, or Scoop |
| As kubectl plugins | `kubectl krew install ctx && kubectl krew install ns` |

The commands are from the README.[^kubectx] All three package managers had 0.11.0 on 2026-10-21.[^packages]

With [fzf](https://github.com/junegunn/fzf) installed, both tools offer an interactive picker; set `KUBECTX_IGNORE_FZF=1` to turn it off.[^kubectx]

## Use

```sh
kubectx minikube          # switch to the "minikube" context
kubectx -                 # switch back to the previous context
kubectx -r prod           # read-only shell: write operations are blocked
kubectx -s minikube       # isolated shell with only that context
kubens kube-system        # change the active namespace
```

These examples are from the README.[^kubectx] The read-only shell (`-r`) is a useful guard when you inspect a production cluster.

## See also

- [Containers and Kubernetes](../concepts/containers.md)
- [kubectl](./kubectl.md)

[^kubectx]: [ahmetb/kubectx README](https://github.com/ahmetb/kubectx)
[^packages]: Homebrew: [kubectx](https://formulae.brew.sh/formula/kubectx); winget: [ahmetb.kubectx](https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/ahmetb/kubectx) and [ahmetb.kubens](https://github.com/microsoft/winget-pkgs/tree/master/manifests/a/ahmetb/kubens); Chocolatey: [kubectx](https://community.chocolatey.org/packages/kubectx) and [kubens](https://community.chocolatey.org/packages/kubens); versions checked 2026-10-21
