Process all unhandled instructions left for Claude in a specified note. This command is invoked with a file path argument (e.g. `/triage 50 - Projects/Websites/NBBC Sermon Catalog`).

The file path is provided as: $ARGUMENTS

Follow these steps:

1. **Read the note:**
   Run `obsidian read path="<file path from $ARGUMENTS>.md"` (append `.md` if not already present). If the file is not found, report the error and stop.

2. **Extract incomplete Claude prompts:**
   Scan the note for any line that begins with or contains `claude,` or `claude:` (case-insensitive). These are instructions left for you.

   - Capture the full block: the trigger line plus any immediately following lines that are indented or continuation content (ends at the next blank line or next unindented line that isn't a continuation).
   - **Skip any prompt block that is immediately followed by a ✅ quote block** — these have already been handled.

   If no incomplete prompts are found, report that the note is fully triaged and stop.

3. **Execute each incomplete prompt in sequence:**
   For each incomplete prompt block, in order from top to bottom:

   a. **Announce which prompt you're working on** — print it clearly so the user knows what's being executed.

   b. **Load context before executing:** Before responding to the prompt, build a full picture of its surroundings:
      - The rest of the note itself — headings, content, structure, and any other context outside the prompt block
      - Run `obsidian backlinks file="<note name>"` and read any notes that link to this one
      The prompt is the entry point, but your response should be informed by everything the note contains and everything that references it. Treat the prompt as the question and the note + its graph as the answer space.

   c. **Execute the instruction** as if it were a standalone prompt typed directly into the terminal. Apply full judgment — this could be anything: storing a memory, doing research, creating a note, answering a question, making a plan, etc.

   d. **Work with the user synchronously** if the prompt requires back-and-forth or a decision. Don't move to the next prompt until this one is fully resolved.

   e. **Once resolved, immediately write a summary back into the source note.** Use `obsidian read` to get the current file content, then use the Edit tool to insert the following block directly beneath the prompt block:

   ```
   > ✅ **Triaged [date]:** [1–3 sentence summary of what was done, decided, or produced. Be specific — mention any files created, memories saved, or decisions made.]
   ```

   Use today's date from the `currentDate` system variable.

   f. Confirm the write succeeded, then move to the next incomplete prompt.

4. **When all prompts are handled**, print a brief summary: how many prompts were triaged, and a one-line recap of each.

---

**Rules:**
- Never skip a prompt silently — if one is ambiguous, ask for clarification before proceeding.
- Never modify the prompt text itself — only insert the ✅ quote block beneath it.
- Do not modify or delete any other content in the note.
- If a file write fails, report it immediately and do not continue to the next prompt until it's resolved.
