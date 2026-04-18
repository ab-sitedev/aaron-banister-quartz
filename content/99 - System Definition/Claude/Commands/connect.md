Find connections between two topics in my Obsidian vault.

The user will provide two topics as arguments: $ARGUMENTS
Parse them as "topic A" and "topic B" — they may be separated by "and", a comma, or just a space.

If no topics are provided, ask: "What two topics would you like me to connect?"

Follow these steps:

1. **Find notes for each topic:**
   - Run `obsidian search query="<topic A>" format=json` — collect the file list
   - Run `obsidian search query="<topic B>" format=json` — collect the file list

2. **Find direct overlap:** Identify files that appear in both result sets. These are the immediate connection points. Read each with `obsidian read file="<name>"` to understand the context.

3. **Traverse the graph for indirect connections:**
   - For each note in topic A's set, run `obsidian links file="<name>"` to get its outgoing links
   - Check whether any of those linked notes appear in topic B's set
   - Run `obsidian backlinks file="<name>"` on the top topic B notes to see what links into them — check if any of those sources appear in topic A's set
   - This finds bridge notes without manually scanning wikilink syntax

4. **Read the bridges:** For any note serving as a bridge, read it to understand the context in which it connects both topics.

---

Present findings as:

### Direct Connections
Notes that mention both **[topic A]** and **[topic B]** — quote or summarize the relevant passage showing how they appear together.

### Bridge Notes
Notes that connect the topics indirectly through the link graph. Describe the path (e.g., "[[Note X]] links to [[Note Y]], which is in topic B's cluster").

### Patterns
Based on everything found, describe recurring themes, relationships, or tensions between the two topics as they appear across the vault. What does the vault suggest about how these two things relate in your thinking?

### Gaps
If the connection is weak or nonexistent, say so honestly — and suggest what kind of note might be worth writing to explore the relationship further.
