# Master Control Plan: `GL Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `ACC-GLE-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `dates_section` | Dates | Section Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  |  | None | None |
| `transaction_date` | Transaction Date | Date | None |  |  |  | None | None |
| `column_break_avko` | None | Column Break | None |  |  |  | None | None |
| `fiscal_year` | Fiscal Year | Link | Fiscal Year |  |  |  | None | None |
| `due_date` | Due Date | Date | None |  |  |  | None | None |
| `account_details_section` | Account Details | Section Break | None |  |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `account_currency` | Account Currency | Link | Currency |  |  |  | None | None |
| `column_break_ifvf` | None | Column Break | None |  |  |  | None | None |
| `against` | Against | Text | None |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `transaction_details_section` | Transaction Details | Section Break | None |  |  |  | None | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  |  | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  |  | None | None |
| `voucher_subtype` | Voucher Subtype | Small Text | None |  |  |  | None | None |
| `transaction_currency` | Transaction Currency | Link | Currency |  |  |  | None | None |
| `column_break_dpsx` | None | Column Break | None |  |  |  | None | None |
| `against_voucher_type` | Against Voucher Type | Link | DocType |  |  |  | None | None |
| `against_voucher` | Against Voucher | Dynamic Link | against_voucher_type |  |  |  | None | None |
| `voucher_detail_no` | Voucher Detail No | Data | None |  |  | ✅ | None | None |
| `transaction_exchange_rate` | Transaction Exchange Rate | Float | None |  |  |  | None | None |
| `amounts_section` | Amounts | Section Break | None |  |  |  | None | None |
| `debit_in_account_currency` | Debit Amount in Account Currency | Currency | account_currency |  |  |  | None | None |
| `debit` | Debit Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `debit_in_transaction_currency` | Debit Amount in Transaction Currency | Currency | transaction_currency |  |  |  | None | None |
| `column_break_bm1w` | None | Column Break | None |  |  |  | None | None |
| `credit_in_account_currency` | Credit Amount in Account Currency | Currency | account_currency |  |  |  | None | None |
| `credit` | Credit Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `credit_in_transaction_currency` | Credit Amount in Transaction Currency | Currency | transaction_currency |  |  |  | None | None |
| `dimensions_section` | Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `column_break_lmnm` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `more_info_section` | More Info | Section Break | None |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `is_opening` | Is Opening | Select | No
Yes |  |  |  | None | None |
| `is_advance` | Is Advance | Select | No
Yes |  |  |  | None | None |
| `column_break_8abq` | None | Column Break | None |  |  |  | None | None |
| `to_rename` | To Rename | Check | None |  | ✅ |  | 1 | None |
| `is_cancelled` | Is Cancelled | Check | None |  |  |  | 0 | None |
| `remarks` | Remarks | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 11
- **Dynamic Link Fields:** 3
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/gl_entry/gl_entry.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("GL Entry", {
	refresh: function (frm) {
		frm.page.btn_secondary.hide();
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Invalid Ledger Entries` | Script Report | Accounts |
| `General and Payment Ledger Comparison` | Script Report | Accounts |
| `Voucher-wise Balance` | Script Report | Accounts |
| `Deferred Revenue and Expense` | Script Report | Accounts |
| `VAT Audit Report` | Script Report | Regional |
| `COGS By Item Group` | Script Report | Stock |
| `Dimension-wise Accounts Balance Report` | Script Report | Accounts |
| `UAE VAT 201` | Script Report | Regional |
| `Gross and Net Profit Report` | Script Report | Accounts |
| `Trial Balance (Simple)` | Query Report | Accounts |
| `Profitability Analysis` | Script Report | Accounts |
| `Cash Flow` | Script Report | Accounts |
| `Trial Balance for Party` | Script Report | Accounts |
| `Trial Balance` | Script Report | Accounts |
| `Profit and Loss Statement` | Script Report | Accounts |
| `Balance Sheet` | Script Report | Accounts |
| `General Ledger` | Script Report | Accounts |



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
