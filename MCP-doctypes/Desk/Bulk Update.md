# Master Control Plan: `Bulk Update`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `field` | Field | Select | None | ✅ |  |  | None | None |
| `update_value` | Update Value | Small Text | None | ✅ |  |  | None | None |
| `condition` | Condition | Small Text | None |  |  |  | None | SQL Conditions. Example: status="Open" |
| `limit` | Limit | Int | None |  |  |  | 500 | Max 500 records at a time |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/bulk_update/bulk_update.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bulk Update", {
	refresh: function (frm) {
		frm.set_query("document_type", function () {
			return {
				filters: [
					["DocType", "issingle", "=", 0],
					["DocType", "name", "not in", frappe.model.core_doctypes_list],
				],
			};
		});

		frm.page.set_primary_action(__("Update"), function () {
			if (!frm.doc.update_value) {
				frappe.throw(__('Field "value" is mandatory. Please specify value to be updated'));
			} else {
				frm.call("bulk_update").then((r) => {
					let failed = r.message;
					if (!failed) failed = [];

					if (failed.length && !r._server_messages) {
						frappe.throw(
							__("Cannot update {0}", [
								failed.map((f) => (f.bold ? f.bold() : f)).join(", "),
							])
						);
					} else {
						frappe.msgprint({
							title: __("Success"),
							message: __("Updated Successfully"),
							indicator: "green",
						});
					}

					frappe.hide_progress();
					frm.save();
				});
			}
		});
	},

	document_type: function (frm) {
		// set field options
		if (!frm.doc.document_type) return;

		frappe.model.with_doctype(frm.doc.document_type, function () {
			var options = $.map(frappe.get_meta(frm.doc.document_type).fields, function (d) {
				if (d.fieldname && frappe.model.no_value_type.indexOf(d.fieldtype) === -1) {
					return d.fieldname;
				}
				return null;
			});
			frm.set_df_property("field", "options", options);
		});
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
