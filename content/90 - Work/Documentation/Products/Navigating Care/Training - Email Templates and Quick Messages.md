Before making any changes, always ensure your changes are being recorded!
ServiceNow records your changes in what they call "Update sets".
Update sets are confined to specific application scopes (In your case, the Customer Service scope)

**Here's how to make sure:**
1. Switch to application scope "Customer Service."
	1. Click the globe icon in the upper-right corner of your screen.
	2. Click the "Application scope" section of the dropdown menu.
	3. Select "Customer Service."
	4. The window will refresh.
2. Enter update set "TM - STRY0011705 - Email Templates and Quick Messages."
	1. Click the globe icon in the upper-right corner of your screen.
	2. Click the "Update set" section of the dropdown menu.
	3. Select "TM - STRY0011705 - Email Templates and Quick Messages."
	4. The window will NOT refresh (This is expected).
# Email Client Templates
These are automatically applied to email drafts initiated from cases that match the conditions in the config.
Currently only being used to set the **subject line** and the **recipients** without conditions (every time).
## Basic Anatomy

| Name       | A recognizable name                                                                              |     |
| ---------- | ------------------------------------------------------------------------------------------------ | --- |
| Table      | The table the template applies to                                                                |     |
| Conditions | The metadata state required in order for the template to be applied                              |     |
| Subject    | Will become the subject line of the email. Include case metadata using [[#${field_name} syntax]] |     |
| To         | The recipients of the email. Include case metadata using [[#raw field name references]]          |     |

# Quick Messages
These are manually selected from a dropdown menu at the top of the email client. They're conditionally available, meaning you can use case metadata to determine which quick messages are selectable.
## Basic Anatomy

| Title      | A recognizable name                                                                                                              |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Table      | The table the quick message applies to                                                                                           |
| Conditions | The metadata state required in order for the quick message to be available                                                       |
| Body       | Will become the body of the email. Include case metadata using [[#${field_name} syntax]] or by using the "Select variables" pane |

# Help References
## ${field_name} Syntax
A field name can be pulled directly from the record (such as `number`) or from a referenced record (such as `assigned_to.name`).
When its necessary to invoke these using the ${} syntax, simply wrap the field name or dot-walked field name inside of the ${} wrapper.
## Raw field name references
Same as above, just without the wrapper.