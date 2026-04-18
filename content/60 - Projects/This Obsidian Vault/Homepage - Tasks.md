## Task Dashboard

The homepage task list was migrated from the **Tasks plugin** (checkbox-based inline tasks) to the **TaskNotes plugin**. Tasks are now standalone notes rather than inline checkboxes scattered across the vault.

---

### How Tasks Are Stored

Each task is its own markdown note under `99 - System Definition/TaskNotes/Tasks/`. Legacy inline tasks can be converted using the TaskNotes plugin. Once converted, their new task-per-note counterpart is stored under `{{currentNotePath}}/Tasks`.

Tasks are identified by a `task` tag in their frontmatter. Key frontmatter fields:

| Field | Description |
|---|---|
| `title` | Task name |
| `status` | Current state: `todo`, `in-progress`, `done`, `cancelled` |
| `priority` | `low`, `normal`, `high`, `none` |
| `scheduled` | Scheduled date/time |
| `due` | Due date |
| `completedDate` | Set automatically when status is changed to `done` |
| `contexts` | List of context tags (e.g. `work`) |
| `tags` | Always includes `task`; may include additional topic tags |

---

### Homepage Embed

The `## Tasks` section of the homepage embeds the TaskNotes base view, defaulting to the **Not done** view on load:

```
![[tasks-default.base#Not done]]
```

The base file lives at `99 - System Definition/TaskNotes/Views/tasks-default.base`. It defines all views, formulas, filters, and sort orders used across the task dashboard.

#### Available Views

| View | What it shows |
|---|---|
| All Tasks | Every task regardless of status |
| Not done | All tasks where `status != done` |
| Not Blocked | Non-done tasks with no incomplete blockers |
| Today | Tasks due or scheduled today |
| Overdue | Non-done tasks with a past due date |
| This Week | Non-done tasks due or scheduled within the next 7 days |
| Unscheduled | Non-done tasks with no due or scheduled date |
| Done this week | Tasks completed during the current calendar week |

The **Done this week** view uses this filter:

```
status == "done"
date(completedDate).format("YYYY-[W]WW") == today().format("YYYY-[W]WW")
```

This compares ISO week numbers, so the window resets on Monday — it is not a rolling 7-day range.

---

### Relationship to the Stat Cards

The **Open Tasks** and **Done This Week** stat cards at the top of the homepage (see [[Homepage - Data Visualizations]]) count task notes directly and also switch the embedded base view when clicked.
