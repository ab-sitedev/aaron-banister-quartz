Scan my daily notes from the past 14 days. Find ideas that deserve their own note. For each one, create a standalone file with the core claim, context, and connections to other notes. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **Read daily notes (last 14 days):** Run `obsidian read path="01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md"` for each of the past 14 days. Focus on:
   - Freeform content under `## Notes`
   - Inline ideas or observations that aren't task items
   - Any phrases that feel like the seed of a claim

2. **Identify graduation candidates:** An idea is worth graduating if it:
   - Makes a claim or observation that could stand on its own
   - Has appeared more than once (same idea, different words)
   - Is specific enough to title and explore further
   - Is NOT just a task, reminder, or logistical note

3. **Check for duplicates:** For each candidate, run `obsidian search query="<key phrase>"` to check if a note already covers it. If one exists, note the connection but skip creating a duplicate.

4. **Check for connections:** For any strong candidates, run `obsidian backlinks file="<related note>"` on notes that seem relevant — this reveals whether the idea is already embedded in the graph or genuinely new territory.

5. **Present candidates before creating anything:**

---

### Graduation Candidates

For each candidate:
- **Title:** A short, specific note title
- **Core claim:** One sentence — the idea in its sharpest form
- **Source:** Which daily note(s) it appeared in, and the relevant quote or paraphrase
- **Why it deserves its own note:** What makes it worth developing further
- **Possible connections:** Existing notes or threads it might link to (use backlinks findings here)

---

Ask: "Should I create these notes? You can approve all, pick specific ones, or refine any before I write them."

If approved, create each note using `obsidian create` with this structure:

```
# [Title]

[Core claim — the idea in one crisp sentence.]

## Context

[Where this idea came from, what prompted it, any relevant quotes from the daily note.]

## Development

[2–3 paragraphs expanding on the idea — implications, questions it raises, what would need to be true for it to be right or wrong.]

## Connections

[Bullet list of related notes as [[wikilinks]].]

## Source
- Originated in daily note: [[YYYY-MM-DD]]
```

Do not create files without confirmation. Do not graduate tasks, logistics, or ideas too vague to title.
