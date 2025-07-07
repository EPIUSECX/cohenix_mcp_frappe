# Master Control Plan: `Tax Withholding Category`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `category_details_section` | Category Details | Section Break | None |  |  |  | None | None |
| `category_name` | Category Name | Data | None |  |  |  | None | None |
| `round_off_tax_amount` | Round Off Tax Amount | Check | None |  |  |  | 0 | Checking this will round off the tax amount to the nearest integer |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `consider_party_ledger_amount` | Consider Entire Party Ledger Amount | Check | None |  |  |  | 0 | Even invoices with apply tax withholding unchecked will be considered for checking cumulative threshold breach |
| `tax_on_excess_amount` | Only Deduct Tax On Excess Amount  | Check | None |  |  |  | 0 | Tax will be withheld only for amount exceeding the cumulative threshold |
| `section_break_8` | Tax Withholding Rates | Section Break | None |  |  |  | None | None |
| `rates` | Rates | Table | Tax Withholding Rate | ✅ |  |  | None | None |
| `section_break_7` | Account Details | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Tax Withholding Account | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/tax_withholding_category/tax_withholding_category.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Tax Withholding Category", {
	setup: function (frm) {
		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			var child = locals[cdt][cdn];
			if (child.company) {
				return {
					filters: {
						company: child.company,
						root_type: ["in", ["Asset", "Liability"]],
						is_group: 0,
					},
				};
			}
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
