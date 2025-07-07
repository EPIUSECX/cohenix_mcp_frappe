# Master Control Plan: `Share Transfer`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `ACC-SHT-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `transfer_type` | Transfer Type | Select | 
Issue
Purchase
Transfer | ✅ |  |  | None | None |
| `column_break_1` | None | Column Break | None |  |  |  | None | None |
| `date` | Date | Date | None | ✅ |  |  | None | None |
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `from_shareholder` | From Shareholder | Link | Shareholder |  |  |  | None | None |
| `from_folio_no` | From Folio No | Data | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `to_shareholder` | To Shareholder | Link | Shareholder |  |  |  | None | None |
| `to_folio_no` | To Folio No | Data | None |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `equity_or_liability_account` | Equity/Liability Account | Link | Account | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `asset_account` | Asset Account | Link | Account |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `share_type` | Share Type | Link | Share Type | ✅ |  |  | None | None |
| `from_no` | From No | Int | None | ✅ |  |  | None | (including) |
| `rate` | Rate | Currency | Company:company:default_currency | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `no_of_shares` | No of Shares | Int | None | ✅ |  |  | None | None |
| `to_no` | To No | Int | None | ✅ |  |  | None | (including) |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `remarks` | Remarks | Long Text | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Share Transfer |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/share_transfer/share_transfer.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.share_transfer");

frappe.ui.form.on("Share Transfer", {
	refresh: function (frm) {
		// Don't show Parties which are a Company
		let shareholders = ["from_shareholder", "to_shareholder"];
		shareholders.forEach((shareholder) => {
			frm.fields_dict[shareholder].get_query = function () {
				return {
					filters: [["Shareholder", "is_company", "=", 0]],
				};
			};
		});
		if (frm.doc.docstatus == 1 && frm.doc.equity_or_liability_account && frm.doc.asset_account) {
			frm.add_custom_button(__("Create Journal Entry"), function () {
				erpnext.share_transfer.make_jv(frm);
			});
		}

		frm.toggle_reqd("asset_account", frm.doc.transfer_type != "Transfer");
	},
	no_of_shares: (frm) => {
		if (frm.doc.rate != undefined || frm.doc.rate != null) {
			erpnext.share_transfer.update_amount(frm);
		}
	},
	rate: (frm) => {
		if (frm.doc.no_of_shares != undefined || frm.doc.no_of_shares != null) {
			erpnext.share_transfer.update_amount(frm);
		}
	},
	company: async function (frm) {
		if (frm.doc.company) {
			let currency = (await frappe.db.get_value("Company", frm.doc.company, "default_currency")).message
				.default_currency;
			frm.set_query("equity_or_liability_account", function () {
				return {
					filters: {
						is_group: 0,
						root_type: ["in", ["Equity", "Liability"]],
						company: frm.doc.company,
						account_currency: currency,
					},
				};
			});
			frm.set_query("asset_account", function () {
				return {
					filters: {
						is_group: 0,
						root_type: "Asset",
						company: frm.doc.company,
						account_currency: currency,
					},
				};
			});
		}
	},

	transfer_type: function (frm) {
		frm.toggle_reqd("asset_account", frm.doc.transfer_type != "Transfer");
	},
});

erpnext.share_transfer.update_amount = function (frm) {
	frm.doc.amount = frm.doc.no_of_shares * frm.doc.rate;
	frm.refresh_field("amount");
};

erpnext.share_transfer.make_jv = function (frm) {
	var account,
		payment_account,
		credit_applicant_type,
		credit_applicant,
		debit_applicant_type,
		debit_applicant;

	if (frm.doc.transfer_type == "Transfer") {
		account = frm.doc.equity_or_liability_account;
		payment_account = frm.doc.equity_or_liability_account;
		credit_applicant_type = "Shareholder";
		credit_applicant = frm.doc.to_shareholder;
		debit_applicant_type = "Shareholder";
		debit_applicant = frm.doc.from_shareholder;
	} else if (frm.doc.transfer_type == "Issue") {
		account = frm.doc.asset_account;
		payment_account = frm.doc.equity_or_liability_account;
		credit_applicant_type = "Shareholder";
		credit_applicant = frm.doc.to_shareholder;
		debit_applicant_type = "";
		debit_applicant = "";
	} else {
		account = frm.doc.equity_or_liability_account;
		payment_account = frm.doc.asset_account;
		credit_applicant_type = "";
		credit_applicant = "";
		debit_applicant_type = "Shareholder";
		debit_applicant = frm.doc.from_shareholder;
	}
	frappe.call({
		args: {
			company: frm.doc.company,
			account: account,
			amount: frm.doc.amount,
			payment_account: payment_account,
			credit_applicant_type: credit_applicant_type,
			credit_applicant: credit_applicant,
			debit_applicant_type: debit_applicant_type,
			debit_applicant: debit_applicant,
		},
		method: "erpnext.accounts.doctype.share_transfer.share_transfer.make_jv_entry",
		callback: function (r) {
			var doc = frappe.model.sync(r.message)[0];
			frappe.set_route("Form", doc.doctype, doc.name);
		},
	});
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Share Balance` | Script Report | Accounts |
| `Share Ledger` | Script Report | Accounts |



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
