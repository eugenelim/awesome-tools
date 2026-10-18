---
type: Tool
title: openGym
description: Self-hosted, open-source gym and body-weight tracker with routines, guided workouts and progress tracking.
resource: https://opengym.ch/
tags:
  - fitness
  - self-hosted
  - open-source
platforms:
  - Docker (self-hosted)
  - Android
  - Web (PWA)
license: AGPL-3.0
pricing: Free
sources:
  - id: opengym
    resource: https://github.com/DuarteSantos8/openGym
    title: DuarteSantos8/openGym README
---
# openGym

A gym and body-weight tracker you host yourself. It plans routines, guides workouts, logs every set and tracks progress. Your data stays in a folder on your own server, with no subscription, ads or telemetry. It installs to the home screen, works offline and syncs between devices behind passkey sign-in. Licensed under AGPL-3.0.[^opengym]

## Features

From the README:[^opengym]

- **Planning:** weekly routines or a rotation, using a library of more than 5,600 exercises with animated demos, browsable by muscle and filterable by your equipment. Four starter plans, plus supersets, warm-ups, drop sets, timed exercises and cardio.
- **Training:** guided sessions with weights pre-filled from last time, a rest timer, personal-record detection, optional RIR/RPE effort tracking, and plate maths.
- **Progress:** progression rules (linear, Greyskull LP, double and triple progression), estimated one-rep-max curves, and a muscle map showing trained, recovering and untrained muscles. Also body-weight and progress-photo tracking.
- **Data:** imports from FitNotes, Strong, Hevy and Apple Health weight exports, and exports everything as JSON. Optional invite-only signup and admin dashboard. 19 languages.
- **Optional, off by default:** an AI coach that uses your own provider key, with every change needing your approval, and a read-only local MCP server for assistants such as Claude Desktop.

## Install

There's no Homebrew or Chocolatey package. Run it with Docker Compose:[^opengym]

```sh
git clone https://github.com/DuarteSantos8/openGym
cd openGym
cp .env.example .env
docker compose pull
docker compose up -d
```

Then open http://localhost:8080. Using passkeys from a phone requires HTTPS on a domain; the project has self-hosting guides for this.[^opengym]

- **Android:** a signed APK from the GitHub releases page or the website (not on the Play Store). It runs standalone on the phone, with no server.[^opengym]
- **iPhone:** add the self-hosted web app to the home screen from Safari, or build the native app with Xcode.[^opengym]

A live demo is available at opengym.ch/demo.[^opengym]

## See also

- [Health and fitness](../concepts/health-and-fitness.md)

[^opengym]: [DuarteSantos8/openGym README](https://github.com/DuarteSantos8/openGym)
