---
type: Tool
title: WebProtégé (self-hosted)
description: Browser-based, collaborative OWL 2 ontology editor from the Protégé project, run on your own server with Docker Compose.
resource: https://github.com/protegeproject/webprotege-deploy
tags:
  - ontology
  - owl
  - semantic-web
  - self-hosted
  - open-source
platforms:
  - Docker (self-hosted)
sources:
  - id: deploy
    resource: https://github.com/protegeproject/webprotege-deploy
    title: protegeproject/webprotege-deploy README, .env.example, docker-compose.yml and LICENSE
  - id: protege
    resource: https://protege.stanford.edu/software
    title: Protégé software page
---
# WebProtégé (self-hosted)

The browser-based edition of [Protégé](./protege.md), for editing OWL 2 ontologies together. It has sharing and permissions, threaded notes and discussions, watches and email notifications, and change tracking with full revision history. Ontologies can be uploaded and downloaded as RDF/XML, Turtle, OWL/XML, OBO and other formats.[^protege]

This page covers running it yourself, so ontologies stay on your own network. The `webprotege-deploy` repo runs the current microservice version with Docker Compose. It has no tagged releases; the Compose file pins each image, for example `webprotege-backend-service:5.0.17` and `webprotege-gwt-ui-server:9.0.28`.[^deploy]

## What runs

The Compose stack starts these services:[^deploy]

| Service | Role |
| --- | --- |
| nginx | Reverse proxy and entry point (port 80) |
| Keycloak | Sign-in and user accounts |
| MongoDB | Database |
| RabbitMQ | Message broker |
| MinIO | Object storage |
| Mailpit | SMTP server for development only; it catches all outgoing mail |
| WebProtégé services | API gateway, web UI, backend, authorisation, user management, event history, ontology processing, revision history and snapshot generation |

## Install

Docker must be running (`docker info`).[^deploy] On a Mac, see [Docker CLI](./docker-cli.md).

1. Clone the repo and create the environment file:[^deploy]

   ```sh
   git clone https://github.com/protegeproject/webprotege-deploy
   cd webprotege-deploy
   cp .env.example .env
   ```

2. Pick a hostname. On one machine, add `127.0.0.1  webprotege-local.edu` to `/etc/hosts` (Windows: `C:\Windows\System32\drivers\etc\hosts`). On a server, set `SERVER_HOST` in `.env` to its hostname instead.[^deploy]
3. Before the first start of anything other people can reach, change `KEYCLOAK_ADMIN`/`KEYCLOAK_ADMIN_PASSWORD` (default `admin`/`password`) and `MINIO_ROOT_USER`/`MINIO_ROOT_PASSWORD` in `.env`. Changing the Keycloak password later means resetting its volume. Leave `ENABLE_JAVA_DEBUG` unset: it opens unauthenticated remote debug ports.[^deploy]
4. Start the stack and wait for Keycloak to log `[entrypoint] Realm configuration complete.`:[^deploy]

   ```sh
   docker compose up -d
   docker compose logs -f webprotege-keycloak
   ```

5. Open http://webprotege-local.edu (or your `SERVER_HOST`), not `localhost`, so sign-in cookies work. Click **Register** to create an account.[^deploy]

## First admin

No user is an admin on a fresh install. To make yourself one:[^deploy]

1. Sign in to the Keycloak admin console at `http://<SERVER_HOST>/keycloak/admin/` with the Keycloak credentials from `.env`.
2. Switch the realm from `master` to `webprotege`.
3. Go to **Clients → webprotege → Roles → SystemAdmin** and assign the role to your account.
4. Sign out of WebProtégé and back in.

By default only users with the `ProjectCreator` role can create projects. To let any signed-in user create them, turn on **Empty project creation allowed** in **Application Settings**.[^deploy]

For real email (password resets), replace Mailpit with your own SMTP server in the `smtpServer` section of the Keycloak realm file `webprotege.json`.[^deploy]

## Stop and reset

From the README:[^deploy]

```sh
docker compose down      # stop, keep data
docker compose down -v   # stop and delete all data
```

## Licence

The deployment repo is BSD-2-Clause, as are the authorisation service and API gateway. GitHub recognises no standard licence in some other service repos, such as the backend and UI.[^deploy]

## See also

- [Ontology editors](../concepts/ontology-editors.md)
- [Protégé](./protege.md)
- [VocBench](./vocbench.md)

[^deploy]: [protegeproject/webprotege-deploy](https://github.com/protegeproject/webprotege-deploy) README, `.env.example`, `docker-compose.yml` and LICENSE; service licences from the GitHub repos of [webprotege-authorization-service](https://github.com/protegeproject/webprotege-authorization-service), [webprotege-gwt-api-gateway](https://github.com/protegeproject/webprotege-gwt-api-gateway), [webprotege-backend-service](https://github.com/protegeproject/webprotege-backend-service) and [webprotege-gwt-ui](https://github.com/protegeproject/webprotege-gwt-ui)
[^protege]: [Protégé software page](https://protege.stanford.edu/software)
