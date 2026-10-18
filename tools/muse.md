---
type: Tool
title: Muse
description: Meta's hosted personal AI agent that carries out tasks in its own cloud VM, used through an app or WhatsApp.
resource: https://muse.ai/
tags:
  - ai-agents
  - personal-assistant
  - meta
platforms:
  - iOS
  - Android
  - macOS
  - WhatsApp
license: Proprietary (hosted service)
sources:
  - id: muse
    resource: /sources/muse-homepage.md
    title: Muse homepage and Homebrew entry
---
# Muse

A hosted personal AI agent from Meta, launched on 2026-09-08.[^muse] You give it a goal or task, such as sorting email, booking reservations, shopping, managing calendars or building fitness plans, and it carries it out.[^muse]

## How it works

From the Muse site:[^muse]

- Each user gets a **Muse Secure VM**, a persistent, isolated Linux computer in the cloud with a full browser. Both you and the agent can use it, and you can step in at any point.
- You chat with it through the Muse app on mobile or Mac, or in WhatsApp.
- You approve actions such as sending email or making purchases before they happen, and an audit trail records what the agent has done and plans to do.
- Logins go in a credential store the agent can't see. Purchases use one-time card numbers, and eligible purchases are covered by Link's purchase protections.
- Conversations are not shared with Meta's ad systems.
- It connects to apps such as email, calendar and Instagram, with permissions you control, and can build its own tools for a task.

## Install

Homebrew's `muse` cask was **disabled** on 2026-10-01 because the download requires a signed URL that Homebrew can't handle.[^muse] Use the app from muse.ai or your app store, or WhatsApp.

## See also

- [Personal AI agents](../concepts/personal-ai-agents.md)
- [Hermes Agent](./hermes.md)

[^muse]: [Muse homepage and Homebrew entry](../sources/muse-homepage.md)
