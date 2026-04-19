---
publish: true
created: 2026-04-18T23:28:12.406-05:00
modified: 2026-04-18T23:49:53.325-05:00
published: 2026-04-18T23:49:53.325-05:00
---

# Putting It Into Practice

Now that you've familiarized yourself with [[Dynamic Email Display Names (Exposit)|the concept]], you can put this data architecture to work with just 1 table and these 2 components:

**TABLES:**

1. Email Display Name Override ([[#Example Override Data|data example]])
   1. Name (String)
   2. Table (Table Name)
   3. Conditions (Conditions)
      1. Dependent on `Table`
   4. Email display name (String)

**COMPONENTS:**

1. A [[#The Script Include|script include]] (To house the logic)
2. A [[#The Mail Script|mail script]] (To run email.setFrom())

## The Script Include

**Name:** EmailUtils

```javascript
setDisplayName: function(current) {
	// Variables
	var senderAddress = ' <' + gs.getProperty('instance_name') + '@service-now.com>';
	var defaultDisplayName = 'companyName ServiceNow';
	
	// Look up configs enabled for the current table
	var configGr = new GlideRecord('u_email_display_name_override');
	configGr.addActiveQuery();
	configGr.addQuery('u_table', current.getTableName());
	configGr.orderBy('order');
	configGr.query();
	
	// Evaluate each config against the current record until first match
	while (configGr.next()) {
		var query = (configGr.getValue('u_conditions') || '').trim();
		
		if (!query) {
			return configGr.getValue('u_email_display_name') + senderAddress;
		}
	
		var filter = new GlideFilter(query, 'email_display_name_filter');
		filter.setCaseSensitive(false);
		if (filter.match(current, true)) {
			return configGr.getValue('u_email_display_name') + senderAddress;
		}
	}
	
	// Fallback
	return defaultDisplayName + senderAddress;
}
```

Something to note: The GlideRecord query looks up matching records in order based on the `order` field. Use this to your advantage and thoughtfully set your `order` values in the override records. First match wins.

## The Mail Script

**Name:** set\_email\_display\_name

```javascript
email.setFrom(new EmailUtils().setDisplayName(current));
```

Now all you have to do is create an Email Display Name Override record that applies to the records you want, and include the mail script in any notifications where you wish to opt-in to this functionality.

# Example Override Data

## Default Fallback

| Name    | Table    | Conditions | Email display name | Active | Order  |
| ------- | -------- | ---------- | ------------------ | ------ | ------ |
| Default | Incident |            | IT Service Desk    | true   | 10,000 |

### Result

Email from: **IT Service Desk \<instanceName@service-now.com>**

## Assignment Group Specific

| Name             | Table    | Conditions               | Email display name   | Active | Order |
| ---------------- | -------- | ------------------------ | -------------------- | ------ | ----- |
| Firewall Support | Incident | assignment\_group=_sysId_ | ACME Network Support | True   | 100   |

### Result

Email from: **ACME Network Support \<instanceName@service-now.com>**
