Parse a meeting transcript file and extract structured meaning from it.

The file path is provided as: \$ARGUMENTS

Follow these steps:

1. **Read the transcript:**
   Run \`obsidian read path="<file path from \$ARGUMENTS>"\` (append \`.md\` if not already present). If the file is not found, report the error and stop.

2. **Load the people index:**
   Run \`obsidian files folder="20 - People"\` to get the full list of people notes. Extract the note name (without path or extension) for each file — these are the names to match against.

3. **Parse the transcript:**
   Read through the full transcript carefully and build a picture of:
   - **Who is speaking** — identify all speakers and their roles if discernible
   - **Who is being spoken to** — note directed statements, questions, and assignments
   - **Key discussion points** — major topics covered, decisions made, and context shared
   - **Action items** — any commitment, follow-up, or task assigned to anyone (including yourself)

4. **Resolve people to wikilinks:**
   For every person mentioned by name anywhere in your output (speakers, assignees, attendees, etc.):
   - Compare against the list from step 2
   - If a match is found (exact or clear first/last name match), replace the plain text name with a wikilink: \`[[Note Name|Display Name]]\` if the display name differs, or \`[[Name]]\` if it matches exactly
   - If no match is found, leave as plain text

5. **Convert action items to tasks:**
   Format each action item using Tasks plugin syntax:
   - \`- [ ] <task description>\`
   - If a specific due date was mentioned: append \`[due:: YYYY-MM-DD]\`
   - If a specific person is responsible, prefix with their name (wikilinked if matched): e.g. \`- [ ] [[Jane Smith]] — follow up on budget approval [due:: 2026-03-25]\`
   - If no responsible party is clear, omit the prefix

6. **Produce the summary output** in this structure:

   ---
   ## Meeting Summary

   **Date:** (from filename or transcript, if available)
   **Attendees:** (comma-separated, wikilinked where matched)

   ### Discussion
   (Narrative summary of what was discussed, organized by topic. Reference speakers by name where relevant. Use wikilinks where matched.)

   ### Action Items
   (Task list using Tasks plugin syntax from step 5. Group by assignee if multiple people have tasks.)

   ---

   Once the summary is composed, prepend it to the transcript file by using the `Edit` tool on the file's absolute path. Match the very first line of the transcript as `old_string` and replace it with:

   ```
   <full summary block>

   ---

   ## Transcript

   <first line of transcript>
   ```

   This places the summary at the top and pushes the transcript under a collapsible `## Transcript` heading (Obsidian folds headings natively).

   After editing, confirm to the user that the summary was written to the file.