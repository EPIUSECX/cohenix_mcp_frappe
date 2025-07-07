# Master Control Plan: `Accounting Period`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:period_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `period_name` | Period Name | Data | None | ✅ |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `closed_documents` | Closed Documents | Table | Closed Document | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/accounting_period/accounting_period.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Accounting Period", {
	onload: function (frm) {
		if (
			frm.doc.closed_documents.length === 0 ||
			(frm.doc.closed_documents.length === 1 && frm.doc.closed_documents[0].document_type == undefined)
		) {
			frappe.call({
				method: "get_doctypes_for_closing",
				doc: frm.doc,
				callback: function (r) {
					if (r.message) {
						cur_frm.clear_table("closed_documents");
						r.message.forEach(function (element) {
							var c = frm.add_child("closed_documents");
							c.document_type = element.document_type;
							c.closed = element.closed;
						});
						refresh_field("closed_documents");
					}
				},
			});
		}

		frm.set_query("document_type", "closed_documents", () => {
			return {
				query: "erpnext.controllers.queries.get_doctypes_for_closing",
			};
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
