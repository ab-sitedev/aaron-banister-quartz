Review what I worked on today. Summarize progress, capture any new ideas that came up, and note anything unfinished that should carry over to tomorrow. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **Today's completed tasks:** Run `obsidian tasks done format=json` and filter for tasks completed today. This is the ground truth of what got done.

2. **Today's open tasks:** Run `obsidian tasks todo format=json` and filter for tasks that were due today but are still incomplete — these are carry-forwards.

3. **Today's daily note:** Run `obsidian read path="01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md"`. Extract freeform content from `## Notes` — this is where half-formed ideas and observations live.

4. **Recent activity:** Run `obsidian recents` to catch anything worked on today that might not have generated a task.

---

Now append a `## Close` section to today's daily note using `obsidian append path="01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md" content=<text>`. Do not overwrite anything.

The section should contain:

### What Got Done
Concise bullet list of meaningful progress — completed tasks, decisions reached, things shipped or finished. Skip trivial or administrative items unless they were time-consuming.

### What Came Up
New ideas, observations, or threads that surfaced during the day and aren't already captured. These are candidates for `/graduate` later.

### Carry Forward
Incomplete tasks or open threads that should move to tomorrow. Phrase each as an action item.

### One Thing
The single most important thing that happened or was learned today. One sentence.

---

Keep the tone plain and factual — this is a log, not a journal entry. If a section has nothing to report, omit it. After writing, confirm what was appended.
