
```dataviewjs
dv.table(["Note", "Folder"],
  dv.pages()
    .where(p => {
      const excluded = ["99 - System Definition", "10 - Diary/00 - Daily", "10 - Diary/01 - Weekly", "10 - Diary/02 - Monthly", "10 - Diary/03 - Yearly"];
      return p.file.inlinks.length === 0
          && p.file.outlinks.length === 0
          && p.file.name !== "Homepage"
          && !excluded.some(x => p.file.path.startsWith(x));
    })
    .sort(p => p.file.folder)
    .map(p => [p.file.link, p.file.folder])
)
```