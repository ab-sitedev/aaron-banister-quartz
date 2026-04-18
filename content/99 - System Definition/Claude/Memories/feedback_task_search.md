---
name: Search vault for tasks, not just TaskList
description: When the user asks about tasks, search Obsidian markdown files in addition to (or instead of) the TaskList tool
type: feedback
---

When the user asks about tasks or todos, don't rely solely on the `TaskList` tool. Tasks in this project are stored as markdown checkboxes (`- [ ]`) in Obsidian notes (especially daily notes in `01 - Periodic Notes/00 - Daily/`).

**Why:** TaskList returned empty when asked about a BMW task, but the task existed as a `- [ ]` item in the daily note. Stopping at TaskList missed it entirely.

**How to apply:** When asked about tasks/todos, also search the vault with `Grep` for the keyword (e.g., `- [ ].*BMW`) or check the current daily note. Use both approaches.
