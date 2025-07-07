# Master Control Plan: `Process Payment Reconciliation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `format:ACC-PPR-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `party_type` | Party Type | Link | DocType | ✅ |  |  | None | None |
| `column_break_io6c` | None | Column Break | None |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type | ✅ |  |  | None | None |
| `receivable_payable_account` | Receivable/Payable Account | Link | Account | ✅ |  |  | None | None |
| `default_advance_account` | Default Advance Account | Link | Account | ✅ |  |  | None | Only 'Payment Entries' made against this advance account are supported. |
| `filter_section` | Filters | Section Break | None |  |  |  | None | None |
| `from_invoice_date` | From Invoice Date | Date | None |  |  |  | None | None |
| `to_invoice_date` | To Invoice Date | Date | None |  |  |  | None | None |
| `column_break_kegk` | None | Column Break | None |  |  |  | None | None |
| `from_payment_date` | From Payment Date | Date | None |  |  |  | None | None |
| `to_payment_date` | To Payment Date | Date | None |  |  |  | None | None |
| `column_break_uj04` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `bank_cash_account` | Bank/Cash Account | Link | Account |  |  |  | None | None |
| `section_break_2n02` | Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Queued
Running
Paused
Completed
Partially Reconciled
Failed
Cancelled |  |  | ✅ | None | None |
| `error_log` | Error Log | Long Text | None |  |  |  | None | None |
| `section_break_a8yx` | None | Section Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Process Payment Reconciliation |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_payment_reconciliation/process_payment_reconciliation.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Process Payment Reconciliation", {
	onload: function (frm) {
		// set queries
		frm.set_query("party_type", function () {
			return {
				filters: {
					name: ["in", Object.keys(frappe.boot.party_account_types)],
				},
			};
		});
		frm.set_query("receivable_payable_account", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
					account_type: frappe.boot.party_account_types[doc.party_type],
				},
			};
		});

		frm.set_query("default_advance_account", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
					account_type: doc.party_type == "Customer" ? "Receivable" : "Payable",
					root_type: doc.party_type == "Customer" ? "Liability" : "Asset",
				},
			};
		});
		frm.set_query("cost_center", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
				},
			};
		});
		frm.set_query("bank_cash_account", function (doc) {
			return {
				filters: [
					["Account", "company", "=", doc.company],
					["Account", "is_group", "=", 0],
					["Account", "account_type", "in", ["Bank", "Cash"]],
				],
			};
		});
	},
	refresh: function (frm) {
		if (frm.doc.docstatus == 1 && ["Queued", "Paused"].find((x) => x == frm.doc.status)) {
			let execute_btn = __("Start / Resume");

			frm.add_custom_button(execute_btn, () => {
				frm.call({
					method: "erpnext.accounts.doctype.process_payment_reconciliation.process_payment_reconciliation.trigger_job_for_doc",
					args: {
						docname: frm.doc.name,
					},
				}).then((r) => {
					if (!r.exc) {
						frappe.show_alert(__("Job Started"));
						frm.reload_doc();
					}
				});
			});
		}
		if (
			frm.doc.docstatus == 1 &&
			["Completed", "Running", "Paused", "Partially Reconciled"].find((x) => x == frm.doc.status)
		) {
			frm.call({
				method: "erpnext.accounts.doctype.process_payment_reconciliation.process_payment_reconciliation.get_reconciled_count",
				args: {
					docname: frm.docname,
				},
			}).then((r) => {
				if (r.message) {
					let progress = 0;
					let description = "";

					if (r.message.processed) {
						progress = (r.message.processed / r.message.total) * 100;
						description = r.message.processed + "/" + r.message.total + " processed";
					} else if (r.message.total == 0 && frm.doc.status == "Completed") {
						progress = 100;
					}

					frm.dashboard.add_progress("Reconciliation Progress", progress, description);
				}
			});
		}
		if (frm.doc.docstatus == 1 && frm.doc.status == "Running") {
			let execute_btn = __("Pause");

			frm.add_custom_button(execute_btn, () => {
				frm.call({
					method: "erpnext.accounts.doctype.process_payment_reconciliation.process_payment_reconciliation.pause_job_for_doc",
					args: {
						docname: frm.docname,
					},
				}).then((r) => {
					if (!r.exc) {
						frappe.show_alert(__("Job Paused"));
						frm.reload_doc();
					}
				});
			});
		}
	},
	company(frm) {
		frm.set_value("party", "");
		frm.set_value("receivable_payable_account", "");
		frm.set_value("default_advance_account", "");
	},
	party_type(frm) {
		frm.set_value("party", "");
	},

	party(frm) {
		frm.set_value("receivable_payable_account", "");
		frm.set_value("default_advance_account", "");
		if (!frm.doc.receivable_payable_account && frm.doc.party_type && frm.doc.party) {
			return frappe.call({
				method: "erpnext.accounts.party.get_party_account",
				args: {
					company: frm.doc.company,
					party_type: frm.doc.party_type,
					party: frm.doc.party,
					include_advance: 1,
				},
				callback: (r) => {
					if (!r.exc && r.message) {
						if (typeof r.message === "string") {
							frm.set_value("receivable_payable_account", r.message);
						} else if (Array.isArray(r.message)) {
							frm.set_value("receivable_payable_account", r.message[0]);
							frm.set_value("default_advance_account", r.message[1]);
						}
					}
					frm.refresh();
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
