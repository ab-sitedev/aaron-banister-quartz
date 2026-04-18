Before reading, understand the anatomy of an email address:

| Display Name   | SMTP Address                       |
| -------------- | ---------------------------------- |
| Aaron Banister | \<aaron.banister@oneoncology.com\> |
# The Default Behavior
Every ServiceNow email comes from a system-defined sender (`sys_email_account`).

At OneOncology, that default looks like:  
**OneOncology ServiceNow \<oneoncology@service-now.com\>**

You _can_ override this on a notification-by-notification basis using the `from` field on the notification record.

**Example:**
- Default → _OneOncology ServiceNow_
- Notification override → _IT Service Desk_
# Where Things Break Down
==What if the display name should change based on the **record itself**?==
**Example:** *A different name depending on Incident assignment group*.

The naive approach is to duplicate notifications with different conditions:
- Same notification (Duplicated for each scenario)
- Slightly different filters
- Different “From” values

	That's clunky, error-prone, and it doesn't scale.

You end up with:
- Duplicate configs
- Fragile conditions
- Confusing behavior for users

And when emails come from the wrong name, users stop trusting the system.
# The Better Approach: Email Display Name Override
**One notification. *Dynamic* display names.**
Instead of cloning notifications, move the logic to a dedicated table.
## Notification (Keep it simple)

| Name                | Table    | On Insert | Conditions | From    |
| ------------------- | -------- | --------- | ---------- | ------- |
| Incident was opened | Incident | True      | (Blank)    | (Blank) |
## Email Display Name Overrides

|Name|Table|Conditions|Email Display Name|
|---|---|---|---|
|Default|Incident|(Blank)|IT Service Desk|
|Verily|Incident|Assignment Group = OO-Corp-Research-Verily|Verily Support|

**Now:**
- One notification config, firing only once
- The display name is resolved dynamically
- No duplication, no overlap
## Execution Order
1. Notification `from` field
2. Email Display Name Override table
3. System default (`sys_email_account`)
# Key Takeaway
**Don’t duplicate notifications to change who an email appears to come from.**  
Centralize that logic and let it scale cleanly.