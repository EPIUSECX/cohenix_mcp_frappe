# Master Control Plan: `Bank Guarantee`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `ACC-BG-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `bg_type` | Bank Guarantee Type | Select | 
Receiving
Providing | ✅ |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  | ✅ | None | None |
| `reference_docname` | Reference Document Name | Dynamic Link | reference_doctype |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | None | ✅ |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `validity` | Validity in Days | Int | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  | ✅ | None | None |
| `bank_account_info` | Bank Account Info | Section Break | None |  |  |  | None | None |
| `bank` | Bank | Link | Bank |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | None |
| `account` | Account | Link | Account |  |  | ✅ | None | None |
| `bank_account_no` | Bank Account No | Data | None |  |  | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `iban` | IBAN | Data | None |  |  | ✅ | None | None |
| `branch_code` | Branch Code | Data | None |  |  | ✅ | None | None |
| `swift_number` | SWIFT number | Data | None |  |  | ✅ | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `more_information` | Clauses and Conditions | Text Editor | None |  |  |  | None | None |
| `margin_details` | Other Details | Section Break | None |  |  |  | None | None |
| `bank_guarantee_number` | Bank Guarantee Number | Data | None |  |  |  | None | None |
| `name_of_beneficiary` | Name of Beneficiary | Data | None |  |  |  | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `margin_money` | Margin Money | Currency | None |  |  |  | None | None |
| `charges` | Charges Incurred | Currency | None |  |  |  | None | None |
| `fixed_deposit_number` | Fixed Deposit Number | Data | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Bank Guarantee |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_guarantee/bank_guarantee.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

cur_frm.add_fetch("bank_account", "account", "account");
cur_frm.add_fetch("bank_account", "bank_account_no", "bank_account_no");
cur_frm.add_fetch("bank_account", "iban", "iban");
cur_frm.add_fetch("bank_account", "branch_code", "branch_code");
cur_frm.add_fetch("bank", "swift_number", "swift_number");

frappe.ui.form.on("Bank Guarantee", {
	setup: function (frm) {
		frm.set_query("bank", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
		frm.set_query("bank_account", function () {
			return {
				filters: {
					company: frm.doc.company,
					bank: frm.doc.bank,
				},
			};
		});
		frm.set_query("project", function () {
			return {
				filters: {
					customer: frm.doc.customer,
				},
			};
		});
	},

	bg_type: function (frm) {
		if (frm.doc.bg_type == "Receiving") {
			frm.set_value("reference_doctype", "Sales Order");
		} else if (frm.doc.bg_type == "Providing") {
			frm.set_value("reference_doctype", "Purchase Order");
		}
	},

	reference_docname: function (frm) {
		if (frm.doc.reference_docname && frm.doc.reference_doctype) {
			let party_field = frm.doc.reference_doctype == "Sales Order" ? "customer" : "supplier";

			frappe.call({
				method: "erpnext.accounts.doctype.bank_guarantee.bank_guarantee.get_voucher_details",
				args: {
					bank_guarantee_type: frm.doc.bg_type,
					reference_name: frm.doc.reference_docname,
				},
				callback: function (r) {
					if (r.message) {
						if (r.message[party_field]) frm.set_value(party_field, r.message[party_field]);
						if (r.message.project) frm.set_value("project", r.message.project);
						if (r.message.grand_total) frm.set_value("amount", r.message.grand_total);
					}
				},
			});
		}
	},

	start_date: function (frm) {
		var end_date = frappe.datetime.add_days(cur_frm.doc.start_date, cur_frm.doc.validity - 1);
		cur_frm.set_value("end_date", end_date);
	},
	validity: function (frm) {
		var end_date = frappe.datetime.add_days(cur_frm.doc.start_date, cur_frm.doc.validity - 1);
		cur_frm.set_value("end_date", end_date);
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
