Find clusters of related ideas in my vault that could become a project, essay, or product. Show me what's emerging and what notes connect to it.

Follow these steps:

1. **Build the signal map:**
   - Run `obsidian tags counts sort=count format=json` — tags with mid-range frequency (not the dominant ones, not singletons) often mark ideas gaining mass
   - Run `obsidian orphans` — isolated notes that haven't been linked yet may be waiting to join a cluster
   - Run `obsidian search:context query="I keep"` and `obsidian search:context query="keeps coming up"` and `obsidian search:context query="related to"` — these surface self-aware pattern recognition

2. **Find densely connected neighborhoods:**
   For any note that appears in multiple search results or has a mid-frequency tag, run `obsidian backlinks file="<name>" counts` to see how many notes point to it. Notes with growing backlink counts are gravitational centers — ideas other ideas are orbiting.

3. **Trace the clusters:**
   For each candidate center note, run `obsidian links file="<name>"` and `obsidian backlinks file="<name>"` to map its immediate neighborhood. Read the center note and 2–3 of its closest neighbors to understand what the cluster is actually about.

4. **Check recent daily notes:**
   Run `obsidian read` on the last 14 daily notes. Look for ideas that have appeared more than once in `## Notes` sections without ever becoming a standalone project or note — these are clusters still living in the margins.

5. **Assess readiness:** For each cluster, judge:
   - How many distinct notes touch it?
   - How recently has it been active?
   - Does it have a clear "so what" — a direction it's pulling toward?
   - Is there a missing note that would make it cohere?

---

### Emergence Report

For each cluster (aim for 3–5):

**[Cluster name — a working title, not a final one]**
- **What it is:** 2–3 sentences on the idea or theme at the center
- **The notes in it:** List the key notes as [[wikilinks]], with one line on what each contributes
- **What form it wants to take:** Your best read on whether this wants to be a project, an essay, a product, a conversation, or something else — and why
- **The missing piece:** What single note, decision, or action would cause this to cohere into something real
- **Readiness:** Hot / Warming / Dormant — based on recency and density of activity

---

Focus on what's *becoming*, not what's already defined. Skip anything with an existing project note or active task list — those are already projects. The goal is to find the pre-project: the cluster that doesn't know it's a project yet.
