
```dataviewjs
const hour = new Date().getHours();
const greeting = hour < 12 ? "Good morning" : hour < 17 ? "Good afternoon" : "Good evening";
dv.el("h1", `${greeting}, Aaron.`, {
  attr: { style: "margin-top: 0.5rem; margin-bottom: 1.75rem;" }
});
```
```dataviewjs
const pages = dv.pages();
const taskNotes = dv.pages('#task');
const open = taskNotes.where(t => t.status !== "done" && t.status !== "cancelled").length;
const startOfWeek = dv.date("now").startOf("week");
const completedThisWeek = taskNotes.where(t => t.status === "done" && t.completedDate && dv.date(t.completedDate) >= startOfWeek).length;
const excludedPaths = ["99 - System Definition", "10 - Diary/00 - Daily", "10 - Diary/01 - Weekly", "10 - Diary/02 - Monthly", "10 - Diary/03 - Yearly"];
const orphans = pages.where(p => p.file.inlinks.length === 0 && p.file.outlinks.length === 0 && p.file.name !== "Homepage" && !excludedPaths.some(x => p.file.path.startsWith(x))).length;

const { Modal, MarkdownRenderer } = require('obsidian');
class NoteModal extends Modal {
  constructor(app, linkPath) {
    super(app);
    this.linkPath = linkPath;
  }
  async onOpen() {
    this.modalEl.style.width = '80vw';
    this.modalEl.style.maxWidth = '900px';
    const file = app.metadataCache.getFirstLinkpathDest(this.linkPath, "");
    if (!file) { this.contentEl.setText('File not found.'); return; }
    const content = await app.vault.read(file);
    await MarkdownRenderer.render(app, content, this.contentEl, file.path, this);
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

const switchBasesView = (viewName) => {
  const findEmbed = (comp) => {
    if (comp.controller?.update && comp.containerEl?.classList?.contains("bases-embed") && comp.containerEl?.getAttribute?.("src")?.includes("tasks-default.base")) return comp;
    for (const child of (comp._children || [])) { const r = findEmbed(child); if (r) return r; }
    return null;
  };
  const embed = findEmbed(app.workspace.activeLeaf?.view);
  if (!embed) return;
  embed.viewName = viewName;
  embed.controller.viewName = viewName;
  embed.controller.update?.();
};

const stats = [
  { value: open,              label: "Open Tasks",     onClick: () => switchBasesView("Not done") },
  { value: completedThisWeek, label: "Done This Week", onClick: () => switchBasesView("Done this week") },
  { value: orphans,           label: "Orphaned Notes", onClick: () => new NoteModal(app, "99 - System Definition/Utilities/Orphaned Notes").open() },
];

const row = dv.el("div", "", {
  attr: { style: "display:flex; gap:0.75rem; margin-bottom:2rem;" }
});

for (const s of stats) {
  const card = row.createEl("div", {
    attr: { style: "flex:1; text-align:center; padding:1rem 0.5rem; background:var(--background-secondary); border-radius:10px;" }
  });
  if (s.onClick) {
    card.style.cursor = "pointer";
    card.addEventListener("click", s.onClick);
  }
  card.createEl("div", {
    text: String(s.value),
    attr: { style: "font-size:1.75rem; font-weight:700; color:var(--interactive-accent);" }
  });
  card.createEl("div", {
    text: s.label,
    attr: { style: "font-size:0.75rem; text-transform:uppercase; letter-spacing:0.06em; opacity:0.55; margin-top:0.25rem;" }
  });
}
```
## Tasks
![[tasks-default.base#Not done]]


---
## Quick Links

> [!summary] Work
> 🪪 [OneID](https://oneid.oneoncology.com/)

>[!important] Personal
>📊 [Budget](https://docs.google.com/spreadsheets/d/1DAMspBFqktQLHm8-ehjQaQZwuEi1OS_WBAQuGuo5Bs8/edit?gid=1404363005#gid=1404363005)


---

## Recent Notes

```dataview
TABLE WITHOUT ID file.link as "Note", file.folder as "Location", dateformat(file.mtime, "MMM d, yyyy") as "Updated"
FROM ""
WHERE file.name != "Homepage" AND !startswith(file.path, "99 - System Definition") AND !startswith(file.path, "10 - Diary") AND !contains(file.tags, "task")
SORT file.mtime DESC
LIMIT 8
```
