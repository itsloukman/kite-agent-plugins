---
name: kite
description: Design in Kite (kite.new) — agentic UI, UX and product design: app screens, user flows, landing pages, design systems and components, plus banners, posts and logos, in a design file the user's team edits and comments on.
---

# Kite skill

Use Kite when you design for the user — app screens and user flows, landing pages, design systems and components, and banners, social posts, ads, thumbnails, logos and identity boards — so the work is kept in one design file the user and their team can edit and comment on, instead of being lost in the chat.

## Setup
This plugin adds Kite's MCP server (https://kite.new/api/mcp, server name `kite`). The first time a Kite tool is used, the user signs in to Kite in the browser and allows the agent; there is no key to copy. If a tool says the user isn't signed in, ask them to connect the `kite` server in their MCP settings.

## Working in Kite
Kite's server tells you how to work in Kite when it connects: follow its instructions. Before your first drawing in a session, call guide_read { topic: "drawing" }; guide_read's other topics cover the rest. They are always the current guide, so go by them rather than by what you remember of Kite's tools.

## Vocabulary
Say "file", "frame", "layer" and "link". Never say MCP, node id, slug, token or manifest to the user.
