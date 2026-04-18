Find notes in my vault that haven't been touched in a long time and assess whether they need to be updated, archived, or deleted. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **Find the oldest notes:**
   Run this Bash command to get markdown files sorted by oldest modification date, excluding periodic notes and system files:
   ```
   find "/Users/aaron/Obsidian Vaults/Aaron Banister" \
     -name "*.md" \
     -not -path "*/01 - Periodic Notes/*" \
     -not -path "*/99 - System Definition/*" \
     -not -path "*/.claude/*" \
     -not -path "*/.trash/*" \
     | xargs stat -f "%m %N" \
     | sort -n \
     | head -20 \
     | awk '{print $2}' \
     | sed "s|/Users/aaron/Obsidian Vaults/Aaron Banister/||"
   ```
   This gives you the 20 oldest files by filesystem modification date.

2. **Read each note:**
   For each file path returned, run `obsidian read path="<path>"`. Skip any file that is clearly a template or stub (fewer than ~5 lines of real content).

3. **Check for connections:**
   For any note with substantive content, run `obsidian backlinks file="<name>"` to see if other notes still reference it. A note with zero backlinks and stale content is a stronger deletion/archival candidate than one that's woven into the graph.

4. **Assess each note for staleness** using these signals:
   - **Outdated facts:** References to things that may have changed (people's roles, project statuses, medical info, plans that were made)
   - **Stranded action items:** Prose or informal tasks that were never captured as checkboxes and never resolved
   - **Dead context:** Notes that only made sense in a past moment — decisions already made, events already past
   - **Orphaned stubs:** Notes with almost no content and no connections — placeholders that never got filled in
   - **Still-valid reference:** Content that's evergreen and accurate — these are fine, just note them

---

### Stale Notes Report

For each note reviewed, produce a brief entry:

**[Note title]** — `path/to/note.md` *(last modified: approx. date if determinable)*
- **Status:** `Needs update` / `Consider deleting` / `Archive candidate` / `Still valid`
- **Why:** One sentence explaining what makes it stale (or why it's fine)
- **Suggested action:** Specific — what to update, what to delete, what to confirm, or "no action needed"

---

At the end, give a short summary:
- How many notes reviewed
- How many need attention vs. are fine
- Any patterns (e.g., a whole folder that's gone stale, a recurring type of note that decays fast)

Do NOT modify or delete any notes without asking first. Surface the findings and let me decide.
