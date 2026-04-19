---
publish: true
created: 2025-11-12
modified: 2026-02-12
tags:
  - hardware_procurement
  - asset_management
  - service_catalog
---

The **Hardware Procurement Request System** is a unified request framework designed to streamline hardware provisioning across the enterprise, with intelligent routing that adapts to both requestor persona and fulfillment method.

The system dynamically tailors catalog visibility based on user criteria, ensuring that standard users see only company-approved hardware, while procurement agents have visibility appropriate to their scope of responsibility.

At the end of each process, the system routes the request through one of three distinct fulfillment pathways, depending on the nature of the request:

- **Break-Fix Fulfillment** generates related _Incidents_ for device replacement due to hardware failure.
- **Existing Inventory Distribution** generates related _SCTASKs_ for fulfillment teams to locate and ship hardware from stock.
- **Net-New Hardware Ordering** generates related _Purchase Orders_ for procurement agents to order new devices with full AP-ready documentation.

---

# Core Components

**Request Intake**

- Hardware Request Form
- Dynamic Catalog Filtering

**Fulfillment Pathways**

- Break-Fix via Incident Management
- Inventory Distribution via SCTASKs
- Net-New Procurement via Purchase Orders

**Supporting Infrastructure**

- Hardware Catalog Management
- Company Hardware Standards
- Asset Management Integration

---

# Common Requestor Experience

When designing a request system that serves thousands of users across multiple companies with varying hardware standards, it's critical to build a solution that presents the right options to the right people at the right time.

Here are the core concepts to familiarize with in order to fully understand how this was achieved in OneOncology's Hardware Procurement Request System:

## Hardware Product Models

are the specific devices users can request (Ex. Dell Latitude 5440, iPad Pro 12.9", Cisco IP Phone 8851, etc.).

## User Personas

determine what catalog visibility and fulfillment options a user has access to.

- **Standard Users** see only company-approved hardware appropriate for their role and location.
- **Procurement Agents** see all hardware available at ITSM practices, plus the ability to route requests through specialized fulfillment pathways.
- **Procurement Administrators** have full catalog visibility including corporate-level options not available to other personas.

## Company Hardware Standards

are practice-specific standards that define which hardware models are approved for use within their organization.

Each company maintains their own hardware standards based on factors like:

- Supportability and parts availability in their region
- Existing vendor relationships and bulk purchasing agreements
- Technical requirements specific to their clinical or operational workflows
- Budget constraints and device lifecycle policies

We encourage decision makers to carefully consider their hardware standards and update them regularly as new devices become available or organizational needs change.

## Dynamic Catalog Filtering

is the backbone of our request framework, ensuring that users are only presented with hardware options that make sense for their specific context.

The system evaluates multiple criteria before presenting catalog options:

- User's persona (standard user vs. support agent vs. procurement staff)
- User's assigned company, location, department
- Further filtering is also possible via scripted user criteria

This prevents common logistical problems like users requesting hardware that isn't approved for their company, or procurement agents requesting hardware not approved for their role.

---

# Common Fulfiller Experience

All fulfillment pathways share a consistent framework, ensuring a unified experience for IT support and procurement staff.

## Request-First Methodology

Each hardware request generates a single RITM, which serves as the _parent record_ for any downstream fulfillment records (Incidents, SCTASKs, or Purchase Orders).

## Intelligent Fulfillment Routing

Before the system allows fulfillment to move forward, it waits for the support agent to identify a fulfillment action on each line item in the hardware request. Possible fulfillment actions per line-item are:

- Fix
- Replace
- Stock Order
- Project _(Coming soon)_

### Break-Fix via Incident Management

When a line item is identified as a "fix" fulfillment due to solvable faults, the system generates a related **Incident** record.

- The Incident is linked to the parent Hardware Request for full visibility
- Support agents follow standard break-fix processes to diagnose and repair the faulty device

### Existing Inventory Distribution

When a line item is identified as a "replace" fulfillment due to unresolvable faults, the system first checks for existing inventory for the given model. If enough inventory is found to fulfil the request without going under the inventory threshold, the system generates an SCTASK for the appropriate distribution team.

This pathway prevents unnecessary purchasing when suitable hardware already exists in stock.

### Net-New Hardware Ordering

When a line item is identified as a "stock order" fulfillment, the system generates one or more **Purchase Order** records linked to the parent Hardware Request depending on how many unique vendors are necessary to fulfill the order(s).

- Each PO is specific to one vendor.
- The PO includes all information needed for AP processing (vendor, line items, cost centers, approvals)
- Procurement agents manage the ordering process through the PO record
- When devices arrive, they are easily imported into the CMDB with pre-populated information from the PO
- Asset records are automatically created for each device with full chain of custody

This pathway ensures proper documentation for financial auditing and streamlines asset management for newly acquired devices.

## Unified Request Tracking

Regardless of fulfillment pathway, the **parent Hardware Request** provides a single pane of glass for monitoring progress.

- Related records (Incidents, SCTASKs, POs) are visible directly from the request
- Status updates from any fulfillment pathway automatically roll up to the parent request
- Requestors can track their hardware request from submission to delivery without knowing the underlying fulfillment complexity

---

# Key Business Problems Solved

## Company-Specific Hardware Standards Enforcement

The dynamic catalog filtering ensures users can only request hardware approved for use at their company. This eliminates requests for devices that:

- Cannot be supported by local IT staff
- Conflict with existing vendor agreements
- Don't meet clinical or operational requirements for that location

## Appropriate Use of Incident Management

The system enables agents to appropriately deflect would-be stock orders towards Incident Management. By intelligently routing device break/fixes to the proper channel, we ensure:

- Break-fix SLAs are properly applied and tracked
- Problem Management can identify patterns in hardware failures
- Asset lifecycle data accurately reflects device health and replacement rates

## Inventory Optimization

Before generating purchase orders for new hardware, the system checks existing inventory and routes requests through distribution SCTASKs when stock is available. This reduces:

- Unnecessary capital expenditure on redundant devices
- Inventory carrying costs for unused equipment
- Procurement cycle time for end users who can receive existing stock faster than new orders

## AP-Ready Purchase Order Documentation

All net-new hardware orders generate structured Purchase Order records that include complete information for Accounts Payable processing:

- Vendor information and payment terms
- Line item details with quantities and unit costs
- Cost center allocations and approval chains
- Receiving documentation linked to specific PO line items

This eliminates manual paperwork and provides a clear audit trail for financial compliance.

## Streamlined Asset Management

When new hardware arrives, the system simplifies CMDB population by:

- Pre-populating asset records with information from the PO
- Providing bulk import capabilities for multiple devices from a single order
- Automatically linking assets to their originating request and end user
- Maintaining full chain of custody from order placement to user assignment

This reduces manual data entry for IT asset managers and ensures accurate, complete asset records from day one.
