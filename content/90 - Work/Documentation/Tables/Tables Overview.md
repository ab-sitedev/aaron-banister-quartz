---
publish: true
created: 2026-03-17T18:53:19.490-05:00
modified: 2025-12-16
---

# OneOncology's Approach to Custom Tables

Creating a net-new table is not a decision taken lightly by database admins striving for a high degree of data hygiene. If the data you're looking to store can fit into an "out-of-box" table, it's often best to try sticking with that table to reduce technical debt and repetition.

However in some cases, you can't avoid it - a custom table is the only way to go.
The Enterprise Solutions team has identified 2 principal categories into which a custom table will fall.

- [[Tables Overview#Actionable Tables|Actionable]]
- [[Tables Overview#Relational Tables|Relational]]

## Actionable Tables

This category represents tables that store data of _varying actionability._

This can range from high actionability like task-extended tables, to low actionability like the Group table. _**For example:**_ Task-extended tables store records which literally represent work to be acted upon by an agent while the Group table stores configurable records which determine actions taken by the system such as "Assign X record to Y group."

### List of Actionable Tables

- [[Access Grant]]
- [[Access Profile]]
- [[Entity Definition]]
- [[OO Application Role]]
- (more to come)

## Relational Tables

These are intermediary tables used to link records from two or more other tables, where multiple records on each side can be related to each other. This is accomplished by creating a table with two reference fields, each pointing to one of the related tables.

_**Picture this:**_ You're building a solution that enables several different practices to all use the same form to request access to the same business application. Each practice wants access for that application to be provisioned to the end-user through a group of their choice. You can't exactly add a reference field to the business app table called "Provisioning group" right? If we mapped every request to that, the same group would be obligated regardless of the practice that invoked it! _**Enter [[u_m2m_business_applications_companies]]**_

Records on that table represent a relationship between a:

- Business application
- Company
- Group (or)
- Provisioning engine

We can now check that table for any records matching the current operation's company and application. If we find a match, we use the group or provisioning engine defined therein.
See [[01 - Software/ServiceNow/01 - Products/Access Management Suite/Access Management Overview|Standard Access Management]]

## List of Relational Tables

- [[u_m2m_business_applications_companies]]
- [[u_m2m_announcement_company]]
- [[u_m2m_announcement_topic]]
- [[Product Onboarding Legal Requests]]
- [[u_m2m_RCM Requests_Legal Requests]]
- (more to come, also I really gotta pretty up those display names 😅)
