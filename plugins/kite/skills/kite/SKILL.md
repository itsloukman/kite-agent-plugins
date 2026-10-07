---
name: kite
description: Design in Kite (kite.new) — draw the visual assets you make (banners, posts, ads, logos, landing pages) into a design file the user's team edits and comments on.
---

# Kite skill

Use Kite when you make visual assets for the user — banners, social posts, ads, thumbnails, logos, icons, landing pages, an identity board — so they are kept in one design file the user and their team can edit and comment on, instead of being lost in the chat.

## Setup
This plugin adds Kite's MCP server (https://kite.new/api/mcp, server name `kite`). The first time a Kite tool is used, the user signs in to Kite in the browser and allows the agent; there is no key to copy. If a tool says the user isn't signed in, ask them to connect the `kite` server in their MCP settings.

## Design files
When you make visual assets, draw them into a design file instead of leaving them in the chat:
- file_new { title, design_system? } -> url, once per piece of work (file_list and file_search find existing ones). Give the user its link — a frame has no link of its own.
- Before drawing, system_read { file } returns the file's design system: tokens (colour, type, spacing, radii, shadows — each with what it is for) and a guide. Write them as var(--name) in inline styles and follow the guide; never paste its CSS. No system yet: system_list and system_apply, or system_new (from tokens, a preset or the user's website).
- Plan before you draw: tokens and shared components (component_make) first, then the screens. Variants go beside the original, named "<name> (Variant 1)".
- A file is a tree of nodes — frames, text, images, SVGs — with CSS on each, on pages. file_outline { file } reads the outline (ids, sizes, board positions) and the file's design system; layer_source { file, node } reads any node as HTML with its ids.
- layer_draw { file, html } draws: each top-level element becomes a frame (an artboard) on the board; give it a parent to draw inside a node, or replace to swap one. Write in small pieces — one section, card or row per call — because the person watches each one appear. Inline styles only (no <style>, classes or scripts), flexbox for layout, px sizes, images by https URL, or picture_add for a picture file (it returns the src); never base64 inside the HTML. Give every artboard an explicit width (and height for a fixed format, e.g. 1500×500 for a Twitter header).
- layer_edit changes CSS, words, names and positions in place; layer_nest and layer_remove do the rest. Change what is there rather than redrawing it: people edit the same file, and redrawing loses their work.
- When you have finished in a file, call finish_working { file }: the person sees you stop at once.
- font_lookup { families, file } says whether Kite has a font (the workspace's own uploads, every Google font, and the system's) and which weights and italics it really has: check before you style text, and use only those weights.
- token_edit { project | system, tokens } adds or changes tokens in a design system, made from a design or a codebase's CSS variables when asked; give each a description of what it is for.
- A file is shared like a Figma file, not published: anyone with the link can view it, and only view, or file_share { page, audience: "restricted", emails } makes it only the people invited. It has no code and no email gate. Viewers can always comment; only the owner and their workspace can download.
- comment_list { page } is what people said: a comment left on a frame names it (asset: its id and name), so layer_source reads what it is about. Apply it with layer_edit or layer_draw { replace }; comment_reply answers as the user.

## Finding and removing
- file_search { query } searches inside files, not just titles — use it when the user describes a file rather than names it.
- file_archive { page } archives a file; the link stops working and it can be unarchived in the app at any time.

## Vocabulary
Say "file", "frame", "layer" and "link". Do not mention MCP, node ids, slugs or tokens to the user.
