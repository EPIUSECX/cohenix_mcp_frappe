# Master Control Plan: `Transaction Deletion Record`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `TDL.####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_qpwb` | None | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Queued
Running
Failed
Completed
Cancelled |  |  | ✅ | None | None |
| `error_log` | Error Log | Long Text | None |  |  |  | None | None |
| `tasks_section` | Tasks | Section Break | None |  |  |  | None | None |
| `delete_bin_data` | Delete Bins | Check | None |  |  | ✅ | 0 | None |
| `delete_leads_and_addresses` | Delete Leads and Addresses | Check | None |  |  | ✅ | 0 | None |
| `reset_company_default_values` | Reset Company Default Values | Check | None |  |  | ✅ | 0 | None |
| `clear_notifications` | Clear Notifications | Check | None |  |  | ✅ | 0 | None |
| `initialize_doctypes_table` | Initialize Summary Table | Check | None |  |  | ✅ | 0 | None |
| `delete_transactions` | Delete Transactions | Check | None |  |  | ✅ | 0 | None |
| `section_break_tbej` | None | Section Break | None |  |  |  | None | None |
| `doctypes` | Summary | Table | Transaction Deletion Record Details |  |  | ✅ | None | None |
| `doctypes_to_be_ignored` | Excluded DocTypes | Table | Transaction Deletion Record Item |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Transaction Deletion Record |  |  | ✅ | None | None |
| `process_in_single_transaction` | Process in Single Transaction | Check | None |  | ✅ | ✅ | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/transaction_deletion_record/transaction_deletion_record.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Transaction Deletion Record", {
	onload: function (frm) {
		if (frm.doc.docstatus == 0) {
			let doctypes_to_be_ignored_array;
			frappe.call({
				method: "erpnext.setup.doctype.transaction_deletion_record.transaction_deletion_record.get_doctypes_to_be_ignored",
				callback: function (r) {
					doctypes_to_be_ignored_array = r.message;
					populate_doctypes_to_be_ignored(doctypes_to_be_ignored_array, frm);
					frm.refresh_field("doctypes_to_be_ignored");
				},
			});
		}
	},

	refresh: function (frm) {
		if (frm.doc.docstatus == 1 && ["Queued", "Failed"].find((x) => x == frm.doc.status)) {
			let execute_btn = frm.doc.status == "Queued" ? __("Start Deletion") : __("Retry");

			frm.add_custom_button(execute_btn, () => {
				// Entry point for chain of events
				frm.call({
					method: "start_deletion_tasks",
					doc: frm.doc,
				});
			});
		}
	},
});

function populate_doctypes_to_be_ignored(doctypes_to_be_ignored_array, frm) {
	if (frm.doc.doctypes_to_be_ignored.length === 0) {
		var i;
		for (i = 0; i < doctypes_to_be_ignored_array.length; i++) {
			frm.add_child("doctypes_to_be_ignored", {
				doctype_name: doctypes_to_be_ignored_array[i],
			});
		}
	}
}

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
