---
type: Tool
title: Colima
description: Runs Docker, containerd or Incus in a Lima Linux VM on macOS and Linux, with minimal setup.
resource: https://colima.run/
tags:
  - containers
  - docker
  - kubernetes
  - macos
  - linux
  - cli
  - open-source
platforms:
  - macOS
  - Linux
license: MIT
pricing: Free
sources:
  - id: colima
    resource: https://github.com/abiosoft/colima
    title: abiosoft/colima README
  - id: install
    resource: https://github.com/abiosoft/colima/blob/main/docs/INSTALL.md
    title: Colima installation options
  - id: faq
    resource: https://github.com/abiosoft/colima/blob/main/docs/FAQ.md
    title: Colima FAQ
  - id: packages
    resource: https://formulae.brew.sh/formula/colima
    title: "Homebrew: colima"
  - id: services
    resource: https://docs.brew.sh/Manpage#services-subcommand
    title: "Homebrew manpage: brew services"
---
# Colima

Container runtimes on macOS and Linux with minimal setup; the name means "Containers on Lima". It runs on Intel and Apple silicon Macs, and is licensed under MIT.[^colima] With the [Docker CLI](./docker-cli.md), it replaces Docker Desktop on a Mac.

- **Runtimes:** Docker (the default) or containerd, either with optional Kubernetes, or Incus for containers and virtual machines.[^colima]
- **VM:** automatic port forwarding, volume mounts and multiple instances. The default VM has 2 CPUs, 2 GiB of memory and 100 GiB of storage; change it with flags such as `--cpu` and `--memory`, or `colima start --edit`.[^colima]
- **Rosetta 2:** on Apple silicon with macOS 13 or later, `--vm-type=vz --vz-rosetta` creates the VM with Rosetta 2 emulation.[^colima]
- **AI models:** from v0.10.0, GPU-accelerated containers on Apple silicon with macOS 13+, using the separately installed `krunkit` VM type.[^colima]

## Install

| Platform | Command |
| --- | --- |
| macOS | `brew install colima` |
| macOS (MacPorts) | `sudo port install colima` |
| Linux (Arch) | `yay -S lima-bin colima-bin` (AUR) |
| Any (Nix) | `nix-env -iA nixpkgs.colima` |
| Any (mise) | `mise use -g colima@latest` |

Binaries for each release are also on the GitHub releases page.[^colima] [^install] The Docker runtime needs the Docker client (`brew install docker`), and Kubernetes needs [kubectl](./kubectl.md).[^colima] On 2026-10-21 Homebrew had 0.10.3, the latest release, and installs Lima with it.[^packages]

## Use

```sh
colima start                      # Docker runtime
docker run hello-world

colima start --kubernetes         # adds Kubernetes
kubectl get pods

colima start --runtime containerd # use nerdctl instead of docker
colima stop
```

After `colima start`, the `docker` client on macOS works with no extra setup. To resize an existing VM, run `colima stop`, then `colima start` with new `--cpu` or `--memory` values.[^colima]

## Start at login with Homebrew

If you installed Colima with Homebrew, the Colima FAQ says the easiest way to start it automatically is a Homebrew service:[^faq]

```sh
brew services start colima        # start now, and again at every login
brew services list                # check it's running
brew services restart colima
brew services stop colima         # stop, and don't start at login
```

Without `sudo`, `brew services` starts the service at login.[^services] The service runs `colima start -f` and logs to `$(brew --prefix)/var/log/colima.log`.[^packages] It uses no extra flags; to start with other settings, such as Kubernetes, set them in the config file with `colima start --edit`.[^faq]

## Run without a background service

Start and stop Colima yourself; it won't start again at login:[^faq] [^help]

```sh
colima start                      # start the VM; your terminal is free again
colima status
colima stop                       # when you're done

colima start --foreground         # or keep Colima attached to this terminal
```

## See also

- [Containers](../concepts/containers.md)
- [Docker CLI](./docker-cli.md#macos-docker-cli--colima)
- [kind](./kind.md)

[^colima]: [abiosoft/colima README](https://github.com/abiosoft/colima)
[^install]: [Colima installation options](https://github.com/abiosoft/colima/blob/main/docs/INSTALL.md)
[^faq]: [Colima FAQ: Does Colima support autostart?](https://github.com/abiosoft/colima/blob/main/docs/FAQ.md#does-colima-support-autostart)
[^packages]: Homebrew: [colima](https://formulae.brew.sh/formula/colima) (versions checked 2026-10-21; service definition checked 2026-10-23); [releases](https://github.com/abiosoft/colima/releases)
[^help]: `colima --help` and `colima start --help`, Colima 0.10.3 on the maintainer's Mac, 2026-10-23
[^services]: [Homebrew manpage: brew services](https://docs.brew.sh/Manpage#services-subcommand)
