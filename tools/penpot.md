---
type: Tool
title: Penpot
description: Open-source design and prototyping platform built on SVG, CSS and HTML, used in the browser or self-hosted, with design tokens and an MCP server.
resource: https://penpot.app/
tags:
  - design
  - prototyping
  - self-hosted
  - open-source
platforms:
  - Web
  - Docker (self-hosted)
license: MPL-2.0
pricing: Free; paid Unlimited and Enterprise plans
sources:
  - id: penpot
    resource: https://github.com/penpot/penpot
    title: penpot/penpot README
  - id: pricing
    resource: https://penpot.app/pricing
    title: Penpot pricing
  - id: docker
    resource: https://help.penpot.app/technical-guide/getting-started/docker/
    title: "Penpot technical guide: Docker"
---
# Penpot

An open-source design platform for interfaces and prototypes, licensed under MPL-2.0. Use it in the browser at penpot.app or host it on your own servers, which keeps design files under your control. It works with open standards (SVG, CSS, HTML and JSON) and has real-time collaboration.[^penpot]

- **Code-like layouts:** CSS Grid and Flex layouts, so responsive designs behave like real code. The Inspect tab gives SVG, CSS and HTML for each element.[^penpot]
- **Design tokens:** built in, as a single source of truth between design and development.[^penpot]
- **Agents and automation:** an MCP server lets AI tools read and change designs, and there's an open API and plugin system.[^penpot]

## Pricing

| Plan | Price | Notes |
| --- | --- | --- |
| Professional | $0 | "Free and fully featured. No limits, no missing tools." |
| Unlimited | $7/editor/month | Capped at $175/month per team; more storage and history; 14-day trial |
| Enterprise | $25/member/month | Central admin, team permissions and governance; 14-day trial |
| Private Server | $50,000/year | Dedicated infrastructure |

Prices from Penpot's pricing page on 2026-10-24. It also offers discounts for non-profits, education and open-source projects.[^pricing]

## Self-host with Docker

There's no Homebrew package. To run it on your own machine or server with Docker Compose:[^docker]

```sh
curl -o docker-compose.yaml https://raw.githubusercontent.com/penpot/penpot/main/docker/images/docker-compose.yaml
docker compose -p penpot -f docker-compose.yaml up -d
```

Then open http://localhost:9001. To pin a version instead of `latest`, set `PENPOT_VERSION` in a `.env` file. Settings are flags in the `PENPOT_FLAGS` variable of the compose file.[^docker]

- **First user:** if registration is turned off, create one with `docker exec -ti penpot-penpot-backend-1 python3 manage.py create-profile`. Check the container name with `docker ps`.[^docker]
- **HTTPS:** the guide strongly recommends HTTPS, with Penpot behind a proxy such as NGINX, Caddy or Traefik. Over plain HTTP on a domain you have to set `disable-secure-session-cookies`, which isn't meant for production, and some browser features such as the clipboard won't work.[^docker]

For Docker without Docker Desktop on a Mac, see [Colima](./colima.md).

## See also

- [Design tools](../concepts/design-tools.md)
- [Paper](./paper.md)

[^penpot]: [penpot/penpot README](https://github.com/penpot/penpot)
[^pricing]: [Penpot pricing](https://penpot.app/pricing), checked 2026-10-24
[^docker]: [Penpot technical guide: Docker](https://help.penpot.app/technical-guide/getting-started/docker/)
