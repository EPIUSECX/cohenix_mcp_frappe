# Master Control Plan: `Personal Data Deletion Request`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `email` | Email | Data | Email | ✅ |  |  | None | None |
| `status` | Status | Select | Pending Verification
Pending Approval
On Hold
Deleted |  |  | ✅ | Pending Verification | None |
| `anonymization_matrix` | Anonymization Matrix | Code | JSON |  |  | ✅ | None | None |
| `deletion_steps` | Deletion Steps  | Table | Personal Data Deletion Step |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/personal_data_deletion_request/personal_data_deletion_request.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Personal Data Deletion Request", {
	refresh: function (frm) {
		if (
			frappe.user.has_role("System Manager") &&
			(frm.doc.status == "Pending Approval" || frm.doc.status == "On Hold")
		) {
			frm.add_custom_button(__("Delete Data"), function () {
				return frappe.call({
					doc: frm.doc,
					method: "trigger_data_deletion",
					freeze: true,
					callback: function () {
						frm.refresh();
					},
				});
			});
		}

		if (frappe.user.has_role("System Manager") && frm.doc.status == "Pending Approval") {
			frm.add_custom_button(__("Put on Hold"), function () {
				return frappe.call({
					doc: frm.doc,
					method: "put_on_hold",
					callback: function () {
						frm.refresh();
					},
				});
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
