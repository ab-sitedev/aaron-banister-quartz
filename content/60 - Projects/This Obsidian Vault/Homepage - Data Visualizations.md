## Homepage Data Visualizations

The three stat cards at the top of `Homepage.md` are rendered by a `dataviewjs` block. Each card shows a live count and responds to clicks.

---

### The Three Cards

#### Open Tasks

**Count:** Queries all notes tagged `#task` via Dataview, then counts those where `status` is neither `done` nor `cancelled`.

```js
const taskNotes = dv.pages('#task');
const open = taskNotes.where(t => t.status !== "done" && t.status !== "cancelled").length;
```

**On click:** Calls `switchBasesView("Not done")`, switching the embedded TaskNotes base below to its **Not done** view.

---

#### Done This Week

**Count:** Queries the same `#task` pages, filters for `status === "done"` with a `completedDate` falling on or after the start of the current calendar week (Monday, via Luxon's `startOf("week")`).

```js
const startOfWeek = dv.date("now").startOf("week");
const completedThisWeek = taskNotes.where(t =>
  t.status === "done" &&
  t.completedDate &&
  dv.date(t.completedDate) >= startOfWeek
).length;
```

**On click:** Calls `switchBasesView("Done this week")`, switching the embedded base to its **Done this week** view. That view uses the same ISO week logic (`YYYY-[W]WW` format comparison) so the count and the view always agree. See [[Homepage - Tasks]] for details on that view's filter.

---

#### Orphaned Notes

**Count:** Queries all vault pages and counts those with no inlinks and no outlinks, excluding `Homepage` itself and several high-volume system/diary folders.

```js
const excludedPaths = [
  "99 - System Definition",
  "10 - Diary/00 - Daily",
  "10 - Diary/01 - Weekly",
  "10 - Diary/02 - Monthly",
  "10 - Diary/03 - Yearly"
];
const orphans = pages.where(p =>
  p.file.inlinks.length === 0 &&
  p.file.outlinks.length === 0 &&
  p.file.name !== "Homepage" &&
  !excludedPaths.some(x => p.file.path.startsWith(x))
).length;
```

**On click:** Opens `99 - System Definition/Utilities/Orphaned Notes` in a modal overlay (see [Modal Behavior](#modal-behavior) below).

---

### Switching the Embedded Base View

The **Open Tasks** and **Done This Week** cards both call `switchBasesView(viewName)`, which programmatically switches the TaskNotes base embed without navigating away from the homepage.

```js
const switchBasesView = (viewName) => {
  const findEmbed = (comp) => {
    if (comp.controller?.update && comp.containerEl?.classList?.contains("bases-embed") && comp.containerEl?.getAttribute?.("src")?.includes("tasks-default.base")) return comp;
    for (const child of (comp._children || [])) {
      const r = findEmbed(child);
      if (r) return r;
    }
    return null;
  };
  const embed = findEmbed(app.workspace.activeLeaf?.view);
  if (!embed) return;
  embed.viewName = viewName;
  embed.controller.viewName = viewName;
  embed.controller.update?.();
};
```

**How it works:** Obsidian's internal component tree is traversed recursively starting from the active leaf's view. The traversal looks for the embed wrapper component — identified by its `containerEl` carrying the `bases-embed` CSS class and a `src` DOM attribute containing `tasks-default.base`. The `src` attribute is set by Obsidian's markdown processor from the `![[...]]` link text and is more reliable than any JS property. Scoping by `src` ensures other base embeds on the page are unaffected.

Once found, the view is switched by directly setting `embed.viewName` and `embed.controller.viewName`, then calling `embed.controller.update()`. The Bases controller's `selectView()` method was intentionally avoided — it calls `setEphemeralState` on the view after the async `runQuery` is dispatched, which interferes with the render and prevents the visual update. The direct approach bypasses that bookkeeping entirely.

---

### Modal Behavior

Clicking **Orphaned Notes** opens a `NoteModal` — a custom class extending Obsidian's built-in `Modal`.

```js
class NoteModal extends Modal {
  constructor(app, linkPath) { ... }

  async onOpen() {
    // Size the modal
    this.modalEl.style.width = '80vw';
    this.modalEl.style.maxWidth = '900px';

    // Resolve and read the file
    const file = app.metadataCache.getFirstLinkpathDest(this.linkPath, "");
    const content = await app.vault.read(file);

    // Render markdown (including Dataview queries) into the modal
    await MarkdownRenderer.render(app, content, this.contentEl, file.path, this);

    // Make internal links navigable
    this.contentEl.addEventListener('click', (e) => {
      const link = e.target.closest('a.internal-link');
      if (!link) return;
      e.preventDefault();
      const href = link.getAttribute('data-href') || link.getAttribute('href');
      if (href) { app.workspace.openLinkText(href, file.path, true); this.close(); }
    });
  }

  onClose() { this.contentEl.empty(); }
}
```

**Key details:**

| Aspect | Detail |
|---|---|
| File resolution | Uses `metadataCache.getFirstLinkpathDest` — handles paths without `.md` extension |
| Rendering | `MarkdownRenderer.render` executes the note's Dataview query inside the modal |
| Link handling | A click listener on `contentEl` intercepts `.internal-link` clicks, opens the target in a new tab, and closes the modal |
| `data-href` vs `href` | `data-href` is checked first since Obsidian sometimes stores the resolved path there while `href` holds the raw link text |
| Cleanup | `onClose` empties `contentEl` to prevent memory leaks from Dataview's live query |
