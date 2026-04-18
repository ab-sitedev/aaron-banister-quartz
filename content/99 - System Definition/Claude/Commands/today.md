Build a prioritized plan for today by reading my vault. Today's date is available via the `currentDate` system variable.

Follow these steps:

1. **All incomplete tasks:** Run `obsidian tasks todo format=json` to get every open task in the vault at once. From the results, identify:
   - Tasks with today's due date
   - Tasks with past due dates (overdue)
   - Tasks from the current week's periodic notes

2. **Today's daily note:** Run `obsidian read path="01 - Periodic Notes/00 - Daily/YYYY-MM-DD.md"` (today's date). Extract anything written under `## Notes` and any tasks not already captured above.

3. **This week's weekly note:** Run `obsidian files folder="01 - Periodic Notes/01 - Weekly"` to find the most recent weekly note, then `obsidian read` it. Extract weekly goals and focus areas from `## Notes` and `## Todo`.

4. **Recently active context:** Run `obsidian recents` to see what files have been open lately — this signals what's actually in motion.

---

Synthesize into a prioritized daily plan:

### Today's Plan

**Priority 1 — Due Today / Overdue**
Tasks with today's due date or past-due, in order of urgency.

**Priority 2 — This Week's Focus**
Based on the weekly note, the most relevant things to advance today.

**Priority 3 — Everything Else**
Other open tasks worth doing if time allows.

**Notes & Context**
Anything from today's or this week's `## Notes` sections relevant to how I should spend my time. Include anything notable from recently opened files if it suggests active work.

---

Keep it actionable. Skip completed tasks. Flag anything overdue or mentioned multiple times. If a task references a note (e.g., `[[Some Note]]`), include enough context to know what it's about without opening it.

Note: Calendar events from external apps are not accessible — this plan is based solely on what's in the vault.
