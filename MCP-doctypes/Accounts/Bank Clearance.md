# Master Control Plan: `Bank Clearance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `account` | Account | Link | Account | ✅ |  |  | None | None |
| `account_currency` | Account Currency | Link | Currency |  | ✅ |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | Select the Bank Account to reconcile. |
| `include_reconciled_entries` | Include Reconciled Entries | Check | None |  |  |  | 0 | None |
| `include_pos_transactions` | Include POS Transactions | Check | None |  |  |  | 0 | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `payment_entries` | Payment Entries | Table | Bank Clearance Detail |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_clearance/bank_clearance.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Bank Clearance", {
	setup: function (frm) {
		frm.add_fetch("account", "account_currency", "account_currency");

		frm.set_query("account", function () {
			return {
				filters: {
					account_type: ["in", ["Bank", "Cash"]],
					is_group: 0,
				},
			};
		});

		frm.set_query("bank_account", function () {
			return {
				filters: {
					is_company_account: 1,
				},
			};
		});
	},

	onload: function (frm) {
		let default_bank_account = frappe.defaults.get_user_default("Company")
			? locals[":Company"][frappe.defaults.get_user_default("Company")]["default_bank_account"]
			: "";
		frm.set_value("account", default_bank_account);

		frm.set_value("from_date", frappe.datetime.month_start());
		frm.set_value("to_date", frappe.datetime.month_end());
	},

	refresh: function (frm) {
		frm.disable_save();
		frm.add_custom_button(__("Get Payment Entries"), () => frm.trigger("get_payment_entries"));

		frm.change_custom_button_type(__("Get Payment Entries"), null, "primary");
		if (frm.doc.payment_entries.length) {
			frm.add_custom_button(__("Update Clearance Date"), () => frm.trigger("update_clearance_date"));
			frm.change_custom_button_type(__("Get Payment Entries"), null, "default");
			frm.change_custom_button_type(__("Update Clearance Date"), null, "primary");
		}
	},

	update_clearance_date: function (frm) {
		return frappe.call({
			method: "update_clearance_date",
			doc: frm.doc,
			callback: function (r, rt) {
				frm.refresh();
			},
		});
	},

	get_payment_entries: function (frm) {
		return frappe.call({
			method: "get_payment_entries",
			doc: frm.doc,
			callback: function () {
				frm.refresh();
			},
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
