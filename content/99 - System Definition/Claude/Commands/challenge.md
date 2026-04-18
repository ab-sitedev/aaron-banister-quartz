Pressure-test the user's thinking on a topic by finding contradictions, weak assumptions, and blind spots in their vault.

The topic is: $ARGUMENTS

If no topic is provided, ask: "What topic or decision would you like me to pressure-test?"

Follow these steps:

1. **Gather everything relevant:**
   - Run `obsidian search:context query="<topic>"` to find all mentions with surrounding context
   - Run `obsidian search:context query="<related term>"` for 2–3 closely related terms or synonyms
   - Run `obsidian tags format=json` and check if any tags map directly to this topic — if so, run `obsidian tag name="<tag>" verbose` to get all files tagged with it
   - For each note surfaced, run `obsidian read file="<name>"` to get the full content
   - Check recent periodic notes: read the last 7 daily notes and the most recent weekly note for any fresh thinking on this topic

2. **Map the stated positions:** List every distinct belief, preference, plan, or stance expressed about this topic across the notes — including approximate date if datable.

3. **Look for contradictions:** Compare positions against each other. Flag anywhere two things can't both be true, a decision conflicts with a stated value, or a position changed without acknowledgment.

4. **Identify assumptions:** For each major position, ask: what would have to be true for this to hold? List the underlying assumptions explicitly — especially ones the notes never examine or support with evidence.

5. **Find gaps and blind spots:** What relevant angles, risks, or counterarguments are completely absent? Use `obsidian search:context query="<opposing view or risk term>"` to confirm the absence isn't just a search miss.

---

Present findings as:

### Positions Found
A brief map of what the vault says about this topic — the raw material for the analysis. Cite note names.

### Contradictions
Specific cases where stated beliefs or actions conflict. Be direct. Reference the source notes.

### Questionable Assumptions
Assumptions embedded in the thinking that may not hold. For each: state the assumption, explain why it's worth questioning, and suggest what evidence would confirm or refute it.

### Blind Spots
Angles, risks, or perspectives notably absent. Only flag genuine gaps, not manufactured doubt.

### The Sharpest Challenge
One paragraph. The single strongest case against the current position or plan. Make it honest and specific, not generic.

---

Tone: direct, not harsh. The goal is to strengthen thinking, not undermine confidence. If the reasoning is solid, say so — and explain why it held up.
