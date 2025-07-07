# Master Control Plan: `Bank Transaction`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | ACC-BTN-.YYYY.- | ✅ |  |  | ACC-BTN-.YYYY.- | None |
| `date` | Date | Date | None |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Pending
Settled
Unreconciled
Reconciled
Cancelled |  |  |  | Pending | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Bank Transaction |  |  | ✅ | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `deposit` | Deposit | Currency | currency |  |  |  | None | None |
| `withdrawal` | Withdrawal | Currency | currency |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `reference_number` | Reference Number | Data | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `transaction_id` | Transaction ID | Data | None |  |  | ✅ | None | None |
| `transaction_type` | Transaction Type | Data | None |  |  |  | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `column_break_oufv` | None | Column Break | None |  |  |  | None | None |
| `payment_entries` | Payment Entries | Table | Bank Transaction Payments |  |  |  | None | None |
| `section_break_18` | None | Section Break | None |  |  |  | None | None |
| `allocated_amount` | Allocated Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `unallocated_amount` | Unallocated Amount | Currency | currency |  |  | ✅ | None | None |
| `party_section` | Payment From / To | Section Break | None |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `column_break_3czf` | None | Column Break | None |  |  |  | None | None |
| `bank_party_name` | Party Name/Account Holder (Bank Statement) | Data | None |  |  |  | None | None |
| `bank_party_account_number` | Party Account No. (Bank Statement) | Data | None |  |  |  | None | None |
| `bank_party_iban` | Party IBAN (Bank Statement) | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_transaction/bank_transaction.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bank Transaction", {
	setup: function (frm) {
		frm.set_query("party_type", function () {
			return {
				filters: {
					name: ["in", Object.keys(frappe.boot.party_account_types)],
				},
			};
		});

		frm.set_query("bank_account", function () {
			return {
				filters: { is_company_account: 1 },
			};
		});

		frm.set_query("payment_document", "payment_entries", function () {
			const payment_doctypes = frm.events.get_payment_doctypes(frm);
			return {
				filters: {
					name: ["in", payment_doctypes],
				},
			};
		});

		frm.set_query("payment_entry", "payment_entries", function () {
			return {
				filters: {
					docstatus: ["!=", 2],
				},
			};
		});
	},

	refresh(frm) {
		if (!frm.is_dirty() && frm.doc.payment_entries.length > 0) {
			frm.add_custom_button(__("Unreconcile Transaction"), () => {
				frm.call("remove_payment_entries").then(() => frm.refresh());
			});
		}
	},

	bank_account: function (frm) {
		set_bank_statement_filter(frm);
	},

	get_payment_doctypes: function () {
		// get payment doctypes from all the apps
		return ["Payment Entry", "Journal Entry", "Sales Invoice", "Purchase Invoice", "Bank Transaction"];
	},
});

function set_bank_statement_filter(frm) {
	frm.set_query("bank_statement", function () {
		return {
			filters: {
				bank_account: frm.doc.bank_account,
			},
		};
	});
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
