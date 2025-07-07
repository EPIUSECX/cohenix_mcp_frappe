# Master Control Plan: `Payment Ledger Entry`

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
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `posting_date` | Posting Date | Date | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `account_type` | Account Type | Select | Receivable
Payable |  |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `due_date` | Due Date | Date | None |  |  |  | None | None |
| `voucher_detail_no` | Voucher Detail No | Data | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  |  | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  |  | None | None |
| `against_voucher_type` | Against Voucher Type | Link | DocType |  |  |  | None | None |
| `against_voucher_no` | Against Voucher No | Dynamic Link | against_voucher_type |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `account_currency` | Currency | Link | Currency |  |  |  | None | None |
| `amount_in_account_currency` | Amount in Account Currency | Currency | account_currency |  |  |  | None | None |
| `delinked` | DeLinked | Check | None |  |  |  | 0 | None |
| `remarks` | Remarks | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 3
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_ledger_entry/payment_ledger_entry.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Payment Ledger Entry", {
	// refresh: function(frm) {
	// }
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Payment Ledger` | Script Report | Accounts |



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
