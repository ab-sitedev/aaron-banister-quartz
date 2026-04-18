---
publish: true
created: 2026-03-17T18:41:54.298-05:00
modified: 2025-12-15
tags:
  - access_management
---

The **Access Management Suite** is a collection of five components, each designed to handle a specific business process related to personnel management, with a focus on managing a user’s application access.

At the end of each process, the system logs any changes made to the user’s [[Access Grant|access grants]], depending on the process invoked:

- **New Hire Onboarding**, **Third Party Access** (Deprecated), and **Access Request** _add_ new access grants.
- **Termination of Employment** _removes (deactivates)_ existing access grants.
- **Role Change** and **Extend Renew Access** are fully dynamic. They can _add, retain, or remove_ access grants as needed.

[[90 - Work/Documentation/Products/Access Management Suite/Standard Access Management - System Diagram.canvas|Standard Access Management - System Diagram]]

---

# Core Components

**Onboarding**

- [[New Hire Onboarding]]

**Intermediate Changes**

- [[Access Request]]
- [[Role Change]]
- [[Extend Renew Access]]

**Off-Boarding**

- [[Termination of Employment|End of Employment]]

---

# Common Requestor Experience

When designing a suite of applications that perform similar but distinctly different duties, it's important to build each solution with a unified user experience in mind.

Here are the core concepts to familiarize with in order to fully understand how this was achieved in OneOncology's Standard Access Management Suite:

## [[Business Application|Business Applications]]

are apps that users can receive access to (Ex. OncoEMR, Aria, etc...).

## [[Access Grant|Access Grants]]

represent applications a user has access to.

## [[Access Profile|Practice-Specific Access Profiles]]

are templates for access grants common to a job function.

Each practice has their own idea of what those access grants should be, and it varies even further from function to function. We encourage decision makers to carefully consider a list of [[Access Profile|access profiles]] that make sense for their organization. There can be any number of access profiles for a given company.

## [[u_m2m_business_applications_companies|Practice-Specific Provisioning Resources]]

are the back-bone of our access provisioning framework, enabling a granular duty obligation for the modification of user access while staying fully unique to each practice.

By default, all applications are provisioned by the same assignment group where the RITM is assigned. This way, any practice can make use of our access management suite with minimal configuration.

However, if a practice has reached a level of process maturity where specific user groups (ITIL or not) can be obligated for specific applications, a provisioning resource can be defined for that practice and such applications.

### [[90 - Work/Documentation/Products/Access Management Suite/Obligate Provisioning Resources|Obligate a Resource to Handle Access Provisioning]]

First decide if the access can be provisioned automatically via a [[#Provisioning Engines|provisioning engine]], or if it needs to be handled manually by a specific user group.

> [!NOTE]
> If you don't have a specific user group to obligate, do not define a provisioning resource. Apps that lack a provisioning resource will fall back to the RITM fulfiller to handle manually at the RITM level.

- **Provisioning Engine Obligation**
  For a given business application, [[Tables Overview#Relational Tables|define a relationship]] between a practice and a _provisioning engine_.

- **Human Obligation**
  For a given business application, [[Tables Overview#Relational Tables|define a relationship]] between a practice and a _user group_.

The system will refer to these relationships when deciding who or what to obligate for a given list of applications.
If it finds a relationship between:

- An application
- The user's company
- And a user group or provisioning engine
  it will trigger an obligation SCTASK to either the user group or the provisioning engine under the main request's RITM.

#### SCTASK Fulfillment

Provisioning groups and provisioning engines are both assigned an SCTASK under the main request's RITM. Both resources are expected to update the SCTASK when user access modifications are made. This allows the RITM fulfiller to easily follow the request's progress behind a single pane of glass.

Non-ITIL provisioning groups are sent an actionable email containing a list of applications to provision, modify, or remove. That email includes a clickable button which tells the system that the provisioning obligations on their SCTASK were completed.

---

# Common Fulfiller Experience

All components share a consistent fulfillment framework, ensuring a unified experience for fulfillment agents.

## RITM-First Methodology

Each process generates a single **RITM**, which serves as the _parent record_ for any downstream related records (SCTASKs).
If desired, the entire fulfillment process can be managed directly within the RITM itself.

## SCTASK Opt-In Availability

In most cases, specific teams are responsible for provisioning access to certain applications.\
When these mappings are defined in the **CMDB**, the system automatically generates one **SCTASK** per team based on the selected business process.

Each SCTASK includes only the applications relevant to its assigned team.\
Teams fulfill their respective items, and any remaining unassigned applications are noted in the **parent RITM’s description** for a generalist to complete.

## Checklist-Driven Access Grants

The **parent RITM** includes an interactive checklist listing all access grant operations required to complete the request.

- When SCTASKs are completed, their matching checklist items on the RITM are automatically checked off.
- Any unchecked items remain visible for the RITM fulfiller to verify and complete.

When the RITM is closed as _Complete_, access grants are created or updated based on the state of each checklist item.\
Unchecked items result in no changes to their corresponding access grants.

## Provisioning Engines

Some applications can be provisioned automatically through **provisioning engines** such as _Okta, Active Directory, Intune_, and others.

These engines can be configured just like team-specific fulfillment groups.\
The system treats each provisioning engine as if it were its own fulfillment team — responsible for making the requested access changes, tracking progress in its own **SCTASK**, and closing it when complete.

This design ensures that fulfillers can monitor provisioning progress in one place, regardless of whether the work is performed by a human or an automated system.
