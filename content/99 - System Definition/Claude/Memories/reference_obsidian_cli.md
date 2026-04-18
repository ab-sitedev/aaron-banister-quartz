---
name: Obsidian CLI
description: The `obsidian` CLI tool is installed and should be used instead of raw file reads/greps when working with this vault
type: reference
---

The `obsidian` CLI is available via the `obsidian` command. Prefer it over Grep/Glob/Read when working with vault structure and content — it's lower token overhead and exposes graph data (backlinks, orphans, etc.) that raw file tools can't see.

Key commands to use:

- `obsidian tasks todo format=json` — all incomplete tasks across vault (replaces grep for checkboxes)
- `obsidian tasks done format=json` — all completed tasks
- `obsidian search:context query="<text>"` — search with surrounding line context (replaces grep for content)
- `obsidian backlinks file="<name>"` — incoming links to a note (graph traversal)
- `obsidian links file="<name>"` — outgoing links from a note
- `obsidian tags counts sort=count format=json` — tag frequency map
- `obsidian orphans` — notes with no incoming links (isolated ideas)
- `obsidian deadends` — notes with no outgoing links
- `obsidian recents` — recently opened files (signals active work)
- `obsidian append path="<path>" content="<text>"` — append to a note without reading first
- `obsidian read file="<name>"` — read by wikilink name (not just path)
- `obsidian create name="<name>" content="<text>"` — create a new note
- `obsidian files folder="<path>"` — list files in a folder
- `obsidian properties file="<name>"` — frontmatter properties for a file
