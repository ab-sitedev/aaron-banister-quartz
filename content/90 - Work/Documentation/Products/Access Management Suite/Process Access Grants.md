---
created: 2025-11-26
modified: 2025-12-09
publish: true
order: 10
tags:
  - access_management
  - subflow
---
Needs to be streamlined: Ditch the scenarios. Every invocation should either be an Add, Keep, or Remove  
  
Inputs
- **RITM** > To find the relevant checklist
- **User** > Definitive target for processing (its not always the RITM’s requested_for)
- **App List** > (to be refactored using JSON) Determines apps to add, modify, or remove
```
{
	"Add": [
		"Candid",
		"Phreesia"
	],
	"Modify": [
		"Aria",
		"OncoEMR"
	],
	"Remove": [
		"AzureAD",
		"Lumen ISP"
	]
}
```