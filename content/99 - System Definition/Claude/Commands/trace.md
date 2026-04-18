Trace the evolution of an idea across the Obsidian vault at `/Users/aaron/Obsidian Vaults/Aaron Banister`.

Topic to trace: $ARGUMENTS

## Your Task

Produce a timeline showing when this idea first appeared, how it evolved, and what it connects to now. Work through these steps:

### Step 1 — Find all mentions

Use Grep to search the vault for the topic (case-insensitive). Collect every file path and matching line. Also search for close variants (synonyms, abbreviations, plural/singular).

```
path: /Users/aaron/Obsidian Vaults/Aaron Banister
pattern: <topic>
-i: true
output_mode: content
```

### Step 2 — Determine dates for each file

For each file containing a mention:

- **Daily notes** (`01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md`): the date is in the filename.
- **Weekly notes** (`01 - Periodic Notes/01 - Weekly/YYYY-Www.md`): derive the week start date.
- **Monthly/Yearly notes**: same pattern.
- **Other notes**: check the YAML frontmatter for `created:`, `date:`, or `modified:` fields. Fall back to the file's filesystem modification date via `stat -f "%SB" -t "%Y-%m-%d" "<path>"` (birth time on macOS).

### Step 3 — Find connected notes (backlinks & forward links)

For each file that mentions the topic:

1. Extract all `[[WikiLinks]]` and `[[WikiLink|aliases]]` from that file — these are its **forward links**.
2. Search the vault for any note that links *to* this file by searching for `[[<filename-without-extension>` — these are its **backlinks**.
3. Check those linked notes for additional context about the topic (read relevant sections).

### Step 4 — Build the timeline

Sort all mentions by date (oldest first). For each entry output:

```
YYYY-MM-DD  <Note Title>  (<file path relative to vault root>)
  Context: <1-2 sentence summary of what was said about the topic here>
  Links: <any notes this entry connects to that are relevant>
```

### Step 5 — Synthesize

After the timeline, write a short narrative (3–5 sentences) covering:
- When and where the idea first appeared
- How it changed or developed over time
- What other ideas or projects it is currently linked to
- Any gaps (periods of silence) worth noting

## Formatting rules
- Use plain markdown, no emoji.
- If no mentions are found, say so clearly and suggest related search terms.
- If only one mention exists, note that it's a new or underdeveloped idea.
- Relative vault root for display purposes is `/Users/aaron/Obsidian Vaults/Aaron Banister`.
