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

[Colima](./colima.md) (MIT) runs Docker, containerd or Incus on macOS and Linux.[^colima-site] [^docker-cli]

```sh
brew install docker docker-compose docker-buildx colima
colima start
docker run hello-world
```

Homebrew installs `docker-compose` and `docker-buildx` as Docker CLI plugins in `$HOMEBREW_PREFIX/lib/docker/cli-plugins`, but the Docker CLI doesn't look there by default.[^homebrew] Add that folder to `cliPluginsExtraDirs` in `~/.docker/config.json`. With [jq](./jq.md), this creates the file if needed, keeps your other settings and existing entries, and is safe to run again:

```sh
mkdir -p ~/.docker
[ -f ~/.docker/config.json ] || echo '{}' > ~/.docker/config.json
jq --arg d "$(brew --prefix)/lib/docker/cli-plugins" \
  '.cliPluginsExtraDirs = ((.cliPluginsExtraDirs // []) + [$d] | unique)' \
  ~/.docker/config.json > /tmp/docker-config.json \
  && mv /tmp/docker-config.json ~/.docker/config.json
```

`$(brew --prefix)` is `/opt/homebrew` on Apple silicon and `/usr/local` on Intel.[^brew-prefix] Without jq, add `"cliPluginsExtraDirs": ["/opt/homebrew/lib/docker/cli-plugins"]` inside the braces of `config.json` by hand (use your own prefix on Intel).

Check the setting and that the plugins are found:

```sh
jq .cliPluginsExtraDirs ~/.docker/config.json
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

## Build images

`docker build` builds with BuildKit through the `buildx` plugin. If the CLI can't find buildx, it falls back to the legacy builder and warns:[^build-check]

```text
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
```

If you see that warning, run `docker buildx version`. On macOS, an `unknown command: docker buildx` error usually means `cliPluginsExtraDirs` is missing from `~/.docker/config.json` (see [macOS: Docker CLI + Colima](#macos-docker-cli--colima)). On Linux and in WSL, check that Docker Engine's buildx plugin package is installed (TODO: needs source for package name per distribution).

Build from the `Dockerfile` in the current folder, then run the image:[^build-check]

```sh
docker build -t myapp:dev .
docker image ls myapp
docker run --rm myapp:dev
```

To build for Intel and Arm at once, pass `--platform`:[^build-check]

```sh
docker buildx ls                  # builders and the platforms they support
docker buildx build --platform linux/amd64,linux/arm64 -t myapp:dev .
```

With Colima on an Apple silicon Mac, the default builder listed `linux/amd64` and `linux/arm64`, and the multi-platform build above worked without creating another builder.[^build-check]

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
[^build-check]: `docker build`, `docker buildx ls` and `docker buildx build` with Docker CLI 29.9.2, docker-buildx 0.38.1 (Homebrew) and Colima 0.10.3 on the maintainer's Apple silicon Mac, 2026-10-27; the warning was captured with buildx not found
