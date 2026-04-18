---
author: Aaron Banister
modified: 2025-12-09
publish: true
order: 4
tags:
  - access_management
  - business_process
---
> [!warning]- Active Issues
> **Feature Support**
> 1. The "Obligate Provisioning Resources" subflow does not support "Access to keep". If a user is retaining access to an application during a role change, but their groups within the application need to change, this is currently up to the RITM fulfiller to coordinate


The Role Change application supports IT and HR personnel by standardizing and automating as much of the process as possible.
# Access Comparison
Role changes are challenging and tedious for everyone involved if the process lacks insight into the user's existing and incoming [[Access Grant|access grants]]. The Role Change form simplifies this part of the process from the very beginning by exposing that information to the requestor.

When filling out the Role Change form, you will select the transitioning user along with their new [[Access Profile|access profile]]. The system will compare the user's current access grants with those they will be inheriting from the new access profile.

Any new access grants the user is inheriting will appear in the "Access to add" box.
Any existing access grants that carry over to their new role will appear in the "Access to keep" box.
Any existing grants not relevant to their new role will appear in the "Access to remove" box.

# Access Provisioning
The Role Change back-end logic will handle access provisioning and removal automatically when possible. If any of the chosen access grants can't be automatically fulfilled, those will be communicated to the request fulfiller via the RITM's description field and checklist interface. By the end of the process, new access is granted and existing access is modified or removed either fully automated or partially automated depending on what applications were chosen in the form and which of those are able to be automated.

![[90 - Work/Documentation/Products/Access Management Suite/Access Management Overview#u_m2m_business_applications_companies Practice-Specific Provisioning Resources|Access Management Overview]]

> [!NOTE]- Upcoming Enhancements
> # NYOH
> - Send notification to endemployment@nyoh.com containing all request variables on submission. Utilize watchlist functionality to meet this need.