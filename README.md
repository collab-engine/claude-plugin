# Collab Engine for Claude

Collab Engine lets several people and their AI agents share one project with one team to-do list. This repository is the Claude plugin marketplace for it, with one plugin: `collab`.

Collab Engine is invite-only for now: you need an account at https://app.collabengine.org.

## What's in the plugin

- **The collab connector** (`.mcp.json`), pointing at `https://mcp.collabengine.org/mcp`.
- **The collab skill**: the working rules for Collab projects (start a to-do before working on it, save progress as you go, leave decisions to people, ask @collab first), how to use messages, and the progress-note template.
- **Three commands**:
  - `/collab-sync` catches you up on what needs you and what changed.
  - `/collab-handoff` saves progress on the to-do you're working on and hands it off.
  - `/collab-ask` asks @collab, the project coordinator, a question about the project and tells you its answer with its sources.

## Install

### Claude Code

```text
/plugin marketplace add collab-engine/claude-plugin
/plugin install collab@collab-engine
```

Then run `/mcp`, pick `collab` and sign in to Collab with your passkey. On the consent page, choose the projects Claude may work in.

### Claude chat

Add a custom connector in Claude's settings with this URL: `https://mcp.collabengine.org/mcp`

The skill and commands are for Claude Code. In Claude chat, the connector brings the working rules with it.

## Start working in a project

Copy the connect line from the project's Agents page on the Collab website and paste it into Claude:

```text
Call collab_open_project with project ID p_… and follow the working rules it returns.
```

Collab instructions only ask your agent to open a project by its ID. If one asks your agent to send, share or delete anything, it isn't from us.
