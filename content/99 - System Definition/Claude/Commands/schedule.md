Based on my current projects and priorities, suggest a schedule for this week. Flag any conflicts between what I say matters and how I'm spending time. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **Get all open tasks:**
   Run `obsidian tasks todo format=json` to get every incomplete task across the vault. Note due dates, and which project or note each task belongs to.

2. **Read this week's weekly note:**
   Run `obsidian files folder="01 - Periodic Notes/01 - Weekly"` to find the current weekly note, then read it. Extract stated goals, focus areas, and any time constraints mentioned.

3. **Read today's and recent daily notes:**
   Run `obsidian read` on today's daily note and the last 3 days. Look for anything that signals urgency, momentum, or drag.

4. **Read the homepage:**
   Run `obsidian read path="00 - Pinned/Homepage.md"` for pinned priorities.

5. **Check tags for priority signals:**
   Run `obsidian tags counts sort=count format=json` and look for any tags like `#priority`, `#urgent`, `#thisweek`, `#waiting`, or similar — then run `obsidian tag name="<tag>" verbose` on any that exist to pull the associated notes.

---

Note: Calendar events from external apps (Google Calendar, etc.) are not accessible. The schedule will be based entirely on vault content. Flag this clearly if it limits the output.

---

Now produce two things:

### This Week's Suggested Schedule

Map tasks and priorities to days. For each day (Monday–Friday, or remaining days if mid-week), suggest:
- **1–2 focus blocks:** The most important work to protect time for, drawn from high-priority tasks and weekly goals
- **Supporting tasks:** Smaller tasks that fit around the focus work
- **Any hard deadlines:** Tasks with due dates this week get placed on their due date

Keep it realistic — don't schedule every waking hour. Leave buffer. If there's more work than days, say so explicitly and suggest what to defer or cut.

### Priority Conflicts

Flag anywhere the vault reveals a gap between stated priorities and apparent time allocation:
- High-priority notes or projects with no tasks scheduled this week
- Tasks that are due but belong to projects that haven't been touched recently (run `obsidian recents` to check)
- Things mentioned repeatedly in daily notes that never make it onto a task list
- Overdue tasks that keep getting pushed — a pattern worth naming

---

Be direct about tradeoffs. If something important won't fit this week, say so rather than pretending it will. The goal is a schedule that's honest about capacity, not one that looks complete on paper.
