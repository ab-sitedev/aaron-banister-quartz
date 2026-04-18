Answer a question in the user's voice, grounded in their vault.

The question is: $ARGUMENTS

If no question is provided, ask: "What question would you like me to answer in your voice?"

Follow these steps:

1. **Search for relevant notes:**
   - Run `obsidian search:context query="<core concept from question>"` — this surfaces matching passages with context, not just file names
   - Run additional searches for 2–3 related terms or synonyms if the first search is thin
   - Run `obsidian tags format=json` to check if any tags map to this topic — if so, use `obsidian tag name="<tag>" verbose` to pull all files with that tag

2. **Read the most relevant notes:** From the matches, run `obsidian read file="<name>"` on the notes most directly related to the question. Pay attention to:
   - Opinions, preferences, or stances explicitly stated
   - Recurring themes or values that show up across multiple notes
   - How the topic is framed — the specific language and way of thinking used
   - Tensions or unresolved questions the user seems to be sitting with

3. **Check for recency:** Run `obsidian recents` to see if any relevant notes have been active lately. Read the last 7 daily notes (skipping days with no `## Notes` content) to catch any recent evolution in thinking on this topic.

4. **Check backlinks on key notes:** For the 1–2 most central notes, run `obsidian backlinks file="<name>"` — notes that link *into* a topic often contain the strongest opinions about it.

---

Now answer the question as the user would — in first person, in their voice.

Guidelines:
- Write as if the user is speaking, not as if you are summarizing them
- Match the tone and register visible in their notes (casual, precise, reflective, etc.)
- Ground every significant claim in something actually found in the vault — don't invent beliefs
- After the answer, add a brief **Sources** section listing the specific notes you drew from
- If the vault doesn't contain enough to answer confidently, say so clearly — note what IS known and what's a gap

The goal is a response the user could read and say "yes, that sounds like me."
