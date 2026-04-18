This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Vault Structure

Numbered prefix system: `00` Pinned, `10` Diary, `20` People, `30` Places, `40` Activities, `50` Products, `60` Projects, `90` Work, `99` System Definition. Templates live at `99 - System Definition/Templates/`.

# obsidian CLI

Always prefer the `obsidian` CLI over raw Grep/Glob/Read when working with vault content — it has lower token overhead and exposes graph data that file tools can't see.

```
obsidian tasks todo format=json
obsidian tasks done format=json
obsidian search:context query="<text>"
obsidian backlinks file="<name>"
obsidian links file="<name>"
obsidian recents
obsidian append path="<path>" content="<text>"
obsidian read file="<name>"
obsidian create name="<name>" content="<text>"
obsidian files folder="<path>"
```

# Memory

Memory files live at `99 - System Definition/Claude/Memories/` and sync via Obsidian Sync. When saving, write the file there and add a pointer to `MEMORY.md` at the system path.

**New device bootstrap:** if `MEMORY.md` is absent or empty, run `obsidian files folder="99 - System Definition/Claude/Memories"`, read each file, and rebuild the index at `~/.claude/projects/-Users-aaronbanister-Obsidian-Aaron-Banister/memory/MEMORY.md`.

# Scratchpad

Use `99 - System Definition/Claude/Scratchpad.md` to persist intermediate state during multi-step tasks. Write a plan at the start, update at milestones.

# Rules

- Don't modify or delete any of my .md notes without asking first.
- Before creating a slash command, check `99 - System Definition/Claude/Commands/` for duplicates and flag any to the user. Commands go there, not elsewhere.
