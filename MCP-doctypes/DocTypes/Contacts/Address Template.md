# Master Control Plan: `Address Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Contacts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:country`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `country` | Country | Link | Country | ✅ |  |  | None | None |
| `is_default` | Is Default | Check | None |  |  |  | 0 | This format is used if country specific format is not found |
| `template` | Template | Code | None |  |  |  | None | <h4>Default Template</h4>
<p>Uses <a href="http://jinja.pocoo.org/docs/templates/">Jinja Templating</a> and all the fields of Address (including Custom Fields if any) will be available</p>
<pre><code>{{ address_line1 }}&lt;br&gt;
{% if address_line2 %}{{ address_line2 }}&lt;br&gt;{% endif -%}
{{ city }}&lt;br&gt;
{% if state %}{{ state }}&lt;br&gt;{% endif -%}
{% if pincode %} PIN:  {{ pincode }}&lt;br&gt;{% endif -%}
{{ country }}&lt;br&gt;
{% if phone %}Phone: {{ phone }}&lt;br&gt;{% endif -%}
{% if fax %}Fax: {{ fax }}&lt;br&gt;{% endif -%}
{% if email_id %}Email: {{ email_id }}&lt;br&gt;{% endif -%}
</code></pre> |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/contacts/doctype/address_template/address_template.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Address Template", {
	refresh: function (frm) {
		if (frm.is_new() && !frm.doc.template) {
			// set default template via js so that it is translated
			frappe.call({
				method: "frappe.contacts.doctype.address_template.address_template.get_default_address_template",
				callback: function (r) {
					frm.set_value("template", r.message);
				},
			});
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
No dashboard charts found.


### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
