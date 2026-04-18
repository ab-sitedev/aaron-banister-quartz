#ui_action
# Condition
`new OOProcurementUtils().canGenerateIncident(current)`
# Execution
Synchronously starts the `global.hardware_procurement__generate_incident` subflow
# Description
Intended for use in the Hardware Procurement context. If the RITM was generated via an incident, we shouldn't need to generate an incident from the RITM. Conversely, if the RITM was generated from the portal, and the agent decides they can fix the device instead of ordering a replacement, this button facilitates proper work tracking via incident record.

Simplified condition: At least one MRVS row needs to be marked "Fix", the RITM's parent is NOT an incident, the item is procurement related, and assigned to is not empty.