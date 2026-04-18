---
title: IDEA - NavC contact to account relationships
status: done
priority: normal
scheduled: 2026-04-06
contexts:
  - work
dateCreated: 2026-04-06T11:59:10.546-05:00
dateModified: 2026-04-08T12:12:18.044-05:00
tags:
  - idea
  - task
completedDate: 2026-04-08
---

M2M table Contacts to Accounts
Each relationship definition would include the contact's MRN depending on the account they're related to

Contact = Aaron Banister

| Account  | MRN         |
| -------- | ----------- |
| Alliance | 15309872345 |
| Texas    | 52342398475 |
On cases:
1. Agent enters account manually
2. System looks up accounts related to contact
3. If there is already a relationship for that account, populate the NCID and MRN fields on the case
4. Else leave those fields blank for the agent to fill from their internal tooling
