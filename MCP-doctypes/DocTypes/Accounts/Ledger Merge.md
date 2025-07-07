# Master Control Plan: `Ledger Merge`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:{account_name} merger on {creation}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `root_type` | Root Type | Select | 
Asset
Liability
Income
Expense
Equity | ✅ |  |  | None | None |
| `account` | Account | Link | Account | ✅ |  |  | None | None |
| `account_name` | Account Name | Data | None | ✅ |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `status` | Status | Select | Pending
Success
Partial Success
Error |  |  | ✅ | None | None |
| `is_group` | Is Group | Check | None |  |  | ✅ | 0 | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `merge_accounts` | Accounts to Merge | Table | Ledger Merge Accounts | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/ledger_merge/ledger_merge.js`
```javascript
// Copyright (c) 2021, Wahni Green Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Ledger Merge", {
	setup: function (frm) {
		frappe.realtime.on("ledger_merge_refresh", ({ ledger_merge }) => {
			if (ledger_merge !== frm.doc.name) return;
			frappe.model.clear_doc(frm.doc.doctype, frm.doc.name);
			frappe.model.with_doc(frm.doc.doctype, frm.doc.name).then(() => {
				frm.refresh();
			});
		});

		frappe.realtime.on("ledger_merge_progress", (data) => {
			if (data.ledger_merge !== frm.doc.name) return;
			let message = __("Merging {0} of {1}", [data.current, data.total]);
			let percent = Math.floor((data.current * 100) / data.total);
			frm.dashboard.show_progress(__("Merge Progress"), percent, message);
			frm.page.set_indicator(__("In Progress"), "orange");
		});

		frm.set_query("account", function (doc) {
			if (!doc.company) frappe.throw(__("Please set Company"));
			if (!doc.root_type) frappe.throw(__("Please set Root Type"));
			return {
				filters: {
					root_type: doc.root_type,
					company: doc.company,
				},
			};
		});

		frm.set_query("account", "merge_accounts", function (doc) {
			if (!doc.company) frappe.throw(__("Please set Company"));
			if (!doc.root_type) frappe.throw(__("Please set Root Type"));
			if (!doc.account) frappe.throw(__("Please set Account"));
			let acc = [doc.account];
			frm.doc.merge_accounts.forEach((row) => {
				acc.push(row.account);
			});
			return {
				filters: {
					is_group: doc.is_group,
					root_type: doc.root_type,
					name: ["not in", acc],
					company: doc.company,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.page.hide_icon_group();
		frm.trigger("set_merge_status");
		frm.trigger("update_primary_action");
	},

	after_save: function (frm) {
		setTimeout(() => {
			frm.trigger("update_primary_action");
		}, 500);
	},

	update_primary_action: function (frm) {
		if (frm.is_dirty()) {
			frm.enable_save();
			return;
		}
		frm.disable_save();
		if (frm.doc.status !== "Success") {
			if (!frm.is_new()) {
				let label = frm.doc.status === "Pending" ? __("Start Merge") : __("Retry");
				frm.page.set_primary_action(label, () => frm.events.start_merge(frm));
			} else {
				frm.page.set_primary_action(__("Save"), () => frm.save());
			}
		}
	},

	start_merge: function (frm) {
		frm.call({
			method: "form_start_merge",
			args: { docname: frm.doc.name },
			btn: frm.page.btn_primary,
		}).then((r) => {
			if (r.message === true) {
				frm.disable_save();
			}
		});
	},

	set_merge_status: function (frm) {
		if (frm.doc.status == "Pending") return;
		let successful_records = 0;
		frm.doc.merge_accounts.forEach((row) => {
			if (row.merged) successful_records += 1;
		});
		let message_args = [successful_records, frm.doc.merge_accounts.length];
		frm.dashboard.set_headline(__("Successfully merged {0} out of {1}.", message_args));
	},

	root_type: function (frm) {
		frm.set_value("account", "");
		frm.set_value("merge_accounts", []);
	},

	company: function (frm) {
		frm.set_value("account", "");
		frm.set_value("merge_accounts", []);
	},
});

frappe.ui.form.on("Ledger Merge Accounts", {
	merge_accounts_add: function (frm) {
		frm.trigger("update_primary_action");
	},

	merge_accounts_remove: function (frm) {
		frm.trigger("update_primary_action");
	},

	account: function (frm, cdt, cdn) {
		let row = frappe.get_doc(cdt, cdn);
		row.account_name = row.account;
		frm.refresh_field("merge_accounts");
		frm.trigger("update_primary_action");
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
