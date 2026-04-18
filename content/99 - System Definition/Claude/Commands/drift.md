Scan my vault for recurring themes or phrases that appear across unrelated notes. What ideas am I drifting toward without realizing it? Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **Tag frequency map:** Run `obsidian tags counts sort=count format=json`. Note the top tags, but more importantly note mid-frequency tags (not the obvious dominant ones) — these often signal emerging interests that haven't been named yet.

2. **Orphaned notes:** Run `obsidian orphans` — notes with no incoming links are often ideas that exist in isolation, not yet connected to anything. Read a sample of them. These are strong drift signals.

3. **Dead-end notes:** Run `obsidian deadends` — notes that don't link out anywhere. Another signal of ideas that haven't found their neighborhood yet.

4. **Targeted searches for marginal language:** Run these to surface what's in the margins:
   - `obsidian search:context query="I keep thinking"`
   - `obsidian search:context query="not sure why"`
   - `obsidian search:context query="somehow"`
   - `obsidian search:context query="I wonder"`
   - `obsidian search:context query="maybe"`
   - `obsidian search:context query="interesting that"`

5. **Daily notes (last 30 days):** Run `obsidian read` on each daily note for the past 30 days. Collect only `## Notes` content — skip tasks entirely.

6. **Cross-reference:** For any recurring phrase or theme found above, run `obsidian search query="<phrase>" total` to confirm how widely it appears across the vault.

Do NOT look for what I'm explicitly working on — those are known. Look for what's unnamed, marginal, and recurring.

---

### Drift Report

For each drift (aim for 4–7 total):

**[Drift name — a short evocative label, not a project title]**
- **The signal:** Specific words, tags, note titles, or search hits that keep appearing, and where
- **What it might mean:** Your best interpretation of what I'm actually drawn to or wrestling with — stated as a hypothesis, not a fact
- **The question underneath:** The core question this drift seems to be orbiting
- **One provocation:** A single question or prompt to help me decide whether to pursue this or let it go

---

Be specific — cite actual content: tag names, note titles, quoted phrases, search hit counts. Avoid observations like "you seem interested in productivity." The goal is to surface something I haven't consciously named yet. Skip anything already well-represented in the active project graph.
