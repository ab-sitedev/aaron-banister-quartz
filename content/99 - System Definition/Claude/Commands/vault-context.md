Read the vault to build a summary of my current overall context. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **All open tasks:** Run `obsidian tasks todo format=json` to get every incomplete task in the vault. Note what's pending, due soon, or overdue.

2. **Daily notes (last 7 days):** Run `obsidian read path="01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md"` for each of the past 7 days. Extract freeform notes from `## Notes` sections and any tasks not already captured.

3. **Weekly note:** Run `obsidian files folder="01 - Periodic Notes/01 - Weekly"` to find the most recent weekly note, then read it. Extract anything under `## Notes` and `## Todo`.

4. **Pinned/Homepage:** Run `obsidian read path="00 - Pinned/Homepage.md"` for pinned priorities and context.

5. **Recent activity signal:** Run `obsidian recents` to see what's been actively opened — this reveals what's actually in motion beyond what's written down.

---

Synthesize into a structured summary:

### Active Projects & Tasks
Distinct ongoing efforts and open todos visible across the notes, grouped loosely by theme. Draw from both the task list and the freeform notes.

### Recent Reflections
Summarize freeform `## Notes` content — thoughts, observations, decisions, things on my mind. Quote or paraphrase directly where useful.

### Priorities (Last 7 Days)
Anything urgent, overdue, or mentioned multiple times. Flag anything that appears stuck or stalled.

---

Be concise. Skip completed tasks. If a section has nothing to report, omit it.
