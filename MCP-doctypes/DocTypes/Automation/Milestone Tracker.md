# Master Control Plan: `Milestone Tracker`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Automation`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:{document_type}-{track_field}`
- **Description:** Track milestones for any document

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Document Type to Track | Link | DocType | ✅ |  |  | None | None |
| `track_field` | Field to Track | Select | None | ✅ |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/milestone_tracker/milestone_tracker.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Milestone Tracker", {
	refresh: function (frm) {
		frm.trigger("update_options");
	},
	document_type: function (frm) {
		frm.trigger("update_options");
	},
	update_options: function (frm) {
		// update select options for `track_field`
		let doctype = frm.doc.document_type;
		let track_fields = [];

		if (doctype) {
			frappe.model.with_doctype(doctype, () => {
				// get all date and datetime fields
				frappe.get_meta(doctype).fields.map((df) => {
					if (["Link", "Select"].includes(df.fieldtype)) {
						track_fields.push({ label: df.label, value: df.fieldname });
					}
				});
				frm.set_df_property("track_field", "options", track_fields);
			});
		} else {
			// update select options
			frm.set_df_property("track_field", "options", []);
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
