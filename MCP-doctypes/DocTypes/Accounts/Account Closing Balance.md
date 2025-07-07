# Master Control Plan: `Account Closing Balance`

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
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `closing_date` | Closing Date | Date | None |  |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `debit` | Debit Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `credit` | Credit Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `account_currency` | Account Currency | Link | Currency |  |  |  | None | None |
| `debit_in_account_currency` | Debit Amount in Account Currency | Currency | account_currency |  |  |  | None | None |
| `credit_in_account_currency` | Credit Amount in Account Currency | Currency | account_currency |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `period_closing_voucher` | Period Closing Voucher | Link | Period Closing Voucher |  |  |  | None | None |
| `is_period_closing_voucher_entry` | Is Period Closing Voucher Entry | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/account_closing_balance/account_closing_balance.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Account Closing Balance", {
// 	refresh(frm) {

// 	},
// });

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
