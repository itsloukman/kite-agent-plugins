# Kite agent plugins

Use [Kite](https://kite.new) with your agent. Kite is a design tool built for agents: your agent draws banners, social posts, ads, logos and screens into a design file your team opens, edits and comments on.

The plugin adds Kite's hosted MCP server (`https://kite.new/api/mcp`) and the Kite design skill. You sign in to Kite once in the browser — there is no key to copy.

## Cursor and Grok Bot

Install **Kite** from the [Cursor Marketplace](https://cursor.com/marketplace) — Grok Bot installs plugins from the same marketplace — then connect the `kite` server and allow it when Kite asks.

## Claude Code

```sh
/plugin marketplace add itsloukman/kite-agent-plugins
/plugin install kite@kite
```

Then run `/mcp`, choose `kite` and sign in.

## Codex

```sh
codex plugin marketplace add itsloukman/kite-agent-plugins
```

Then install **Kite** from `/plugins` and sign in when asked.

## Without a plugin

Any MCP client that supports remote servers with OAuth can use Kite: add `https://kite.new/api/mcp`. Claude, ChatGPT, Grok and Muse take it as a custom connector — see [kite.new/docs](https://kite.new/docs).

## Privacy

Kite only acts on files in the Kite account you sign in with, and you can disconnect an agent at any time in Kite's settings. See [kite.new/privacy](https://kite.new/privacy) and [kite.new/terms](https://kite.new/terms).
