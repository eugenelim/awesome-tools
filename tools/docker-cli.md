---
type: Tool
title: Docker CLI
description: Open-source command-line client for building and running containers; needs a Docker Engine to talk to.
resource: https://github.com/docker/cli
tags:
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
  - id: docker-cli
    resource: https://github.com/docker/cli
    title: docker/cli repository
  - id: desktop-license
    resource: https://docs.docker.com/subscription/desktop-license/
    title: Docker Desktop license agreement
  - id: colima-site
    resource: https://colima.run/
    title: Colima
  - id: engine-ubuntu
    resource: https://docs.docker.com/engine/install/ubuntu/
    title: Install Docker Engine on Ubuntu
  - id: brew-prefix
    resource: https://docs.brew.sh/Installation
    title: Homebrew installation docs
  - id: homebrew
    resource: https://formulae.brew.sh/formula/docker
    title: "Homebrew: docker, docker-compose, docker-buildx, colima"
  - id: winget-pkg
    resource: https://github.com/microsoft/winget-pkgs/tree/master/manifests/d/Docker/DockerCLI
    title: "winget: Docker.DockerCLI"
  - id: choco-pkg
    resource: https://community.chocolatey.org/packages/docker-cli
    title: "Chocolatey: docker-cli"
---
# Docker CLI

The `docker` command-line client, licensed under Apache-2.0.[^docker-cli] It sends commands to a Docker Engine (from the Moby project, also Apache-2.0).[^docker-cli] The engine runs on Linux, so on macOS and Windows you also need something that provides one: Docker Desktop, or a free alternative.

## Licensing: CLI and Engine vs Docker Desktop

- **Docker CLI and Docker Engine** are open source and need no subscription. Docker states that the licensing and distribution terms of its open-source projects, "such as Docker Engine", "aren't changing".[^desktop-license]
- **Docker Desktop** is free only for small businesses (fewer than 250 employees *and* under $10 million in annual revenue), personal use, education and non-commercial open-source projects. "Professional use in larger organizations" and government entities need a paid subscription.[^desktop-license]
- So if your organisation is above those thresholds, you need either a Docker Desktop subscription or a setup that leaves Desktop out. You don't need Podman to stay licensed; the free options below use the Docker CLI with an open-source engine.

## Setup without Docker Desktop

### macOS: Docker CLI + Colima

[Colima](https://colima.run/) (MIT) runs Docker, containerd or Incus on macOS and Linux.[^colima-site] [^docker-cli]

```sh
brew install docker docker-compose docker-buildx colima
colima start
docker run hello-world
```

Homebrew installs `docker-compose` and `docker-buildx` as Docker CLI plugins in `$HOMEBREW_PREFIX/lib/docker/cli-plugins`, but the Docker CLI doesn't look there by default.[^homebrew] Add that folder to `~/.docker/config.json`, creating the file if it doesn't exist:

```json
{
  "cliPluginsExtraDirs": ["/opt/homebrew/lib/docker/cli-plugins"]
}
```

`/opt/homebrew` is Homebrew's default prefix on Apple silicon.[^brew-prefix] On an Intel Mac, use the folder printed by `echo "$(brew --prefix)/lib/docker/cli-plugins"`. If `config.json` already has other settings, add the `cliPluginsExtraDirs` line inside the existing braces rather than replacing the file.

Check that the plugins are found:

```sh
docker compose version
docker buildx version
```

### Windows: Docker Engine inside WSL 2

Install [WSL](./wsl.md) with Ubuntu (the default distribution), then install Docker Engine inside it using Docker's Ubuntu instructions:[^engine-ubuntu]

```sh
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Run `docker` from the WSL terminal. For a Windows-side client, use `winget install Docker.DockerCLI`[^winget-pkg] or `choco install docker-cli`.[^choco-pkg]

### Linux

Install Docker Engine directly; the CLI comes with it.[^engine-ubuntu]

## With Docker Desktop

If your organisation is under the thresholds, or pays for a subscription, Docker Desktop installs the CLI and an engine together: `brew install --cask docker-desktop` or `choco install docker-desktop`.[^homebrew] [^choco-pkg]

## Podman

Podman is an Apache-2.0 alternative with its own CLI. On macOS it runs containers in a VM started with `podman machine`. It's available as `brew install podman` and `choco install podman-cli`.[^homebrew] [^choco-pkg] Licensing doesn't require it.

## See also

- [Containers](../concepts/containers.md)
- [Windows platform tools](../concepts/windows-platform-tools.md)

[^docker-cli]: [docker/cli](https://github.com/docker/cli), [moby/moby](https://github.com/moby/moby) and [abiosoft/colima](https://github.com/abiosoft/colima) repositories (licences)
[^desktop-license]: [Docker Desktop license agreement](https://docs.docker.com/subscription/desktop-license/)
[^colima-site]: Colima website: [colima.run](https://colima.run/)
[^engine-ubuntu]: [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
[^brew-prefix]: [Homebrew installation docs](https://docs.brew.sh/Installation)
[^homebrew]: Homebrew: [docker](https://formulae.brew.sh/formula/docker), [docker-compose](https://formulae.brew.sh/formula/docker-compose), [docker-buildx](https://formulae.brew.sh/formula/docker-buildx), [colima](https://formulae.brew.sh/formula/colima), [podman](https://formulae.brew.sh/formula/podman), [docker-desktop](https://formulae.brew.sh/cask/docker-desktop)
[^choco-pkg]: Chocolatey: [docker-cli](https://community.chocolatey.org/packages/docker-cli), [docker-desktop](https://community.chocolatey.org/packages/docker-desktop), [podman-cli](https://community.chocolatey.org/packages/podman-cli)

[^winget-pkg]: [winget: Docker.DockerCLI](https://github.com/microsoft/winget-pkgs/tree/master/manifests/d/Docker/DockerCLI)
