---
type: Tool
title: Rill
description: Free macOS browser (beta) that sends tasks from any page to your own Claude Code or Codex agents.
resource: https://rill.love/
tags:
  - browser
  - macos
  - ai-agents
platforms:
  - macOS
pricing: Free (AI features use your Claude Code or Codex plan)
sources:
  - id: rill
    resource: /sources/rill-homepage.md
    title: Rill homepage
---
# Rill

A macOS browser, currently in beta, built to work with your local [Claude Code](./claude-code.md) or [Codex](./codex.md). From any page you press ⌘E to send a task or question to your agent, and keep browsing while it works. It runs on the Claude Code or Codex plan you already have, with no extra subscription or API keys.[^rill]

## Features

From the Rill site:[^rill]

- Picks up your projects from your Claude Code and Codex history and sends each request to the right one.
- Web tasks, such as finding a flight, run in a background tab. They stop before paying, ordering, sending, posting or deleting unless you clearly told the agent to.
- Agents tell you when they're done or need an answer.
- Groups tabs by what you were doing, and keeps a history you can search by describing a page.
- A project map of everything your agents have worked on.
- Ask about a page; compare up to six tabs as a table that quotes each page.
- Voice input: hold Fn and speak (beta).
- Works as a normal browser without an agent. Passwords are kept in Keychain, private windows are available, and it imports sign-ins from Chrome, Arc or Safari.

## Safety and privacy

From the Rill FAQ and privacy section:[^rill]

- New coding tasks are read-only until you allow edits, and in git repositories each edit can be undone.
- Agents can't type into password, card or one-time-code fields.
- Inside a project, agents browse in their own tabs without your logins. Web tasks use your sign-ins within the limits above. Rill says this "lowers the risk; it doesn't remove it" for prompt injection.
- History is stored as files on your Mac. Tab sorting and day summaries can be switched off.

## Requirements

Apple silicon Mac with macOS 14 or later. Agent features need Claude Code 2.1.261+ or Codex CLI 0.144.4+.[^rill]

## Install

No Homebrew package. Download the `.dmg` from rill.love and drag Rill to Applications, then sign in to Claude Code or Codex.[^rill]

## See also

- [Web browsers](../concepts/web-browsers.md)
- [AI coding agents](../concepts/ai-coding-agents.md)

[^rill]: [Rill homepage](../sources/rill-homepage.md)
