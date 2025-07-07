# Master Control Plan: `Asset Category`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:asset_category_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `asset_category_name` | Asset Category Name | Data | None | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `depreciation_options` | Depreciation Options | Section Break | None |  |  |  | None | None |
| `enable_cwip_accounting` | Enable Capital Work in Progress Accounting | Check | None |  |  |  | 0 | None |
| `non_depreciable_category` | Non Depreciable Category | Check | None |  |  |  | 0 | None |
| `finance_book_detail` | Finance Book Detail | Section Break | None |  |  |  | None | None |
| `finance_books` | Finance Books | Table | Asset Finance Book |  |  |  | None | None |
| `section_break_2` | Accounts | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Asset Category Account | ✅ |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_category/asset_category.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Asset Category", {
	onload: function (frm) {
		frm.add_fetch("company_name", "accumulated_depreciation_account", "accumulated_depreciation_account");
		frm.add_fetch("company_name", "depreciation_expense_account", "depreciation_expense_account");

		frm.set_query("fixed_asset_account", "accounts", function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Fixed Asset",
					root_type: "Asset",
					is_group: 0,
					company: d.company_name,
				},
			};
		});

		frm.set_query("accumulated_depreciation_account", "accounts", function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Accumulated Depreciation",
					is_group: 0,
					company: d.company_name,
				},
			};
		});

		frm.set_query("depreciation_expense_account", "accounts", function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Depreciation",
					root_type: ["in", ["Expense", "Income"]],
					is_group: 0,
					company: d.company_name,
				},
			};
		});

		frm.set_query("capital_work_in_progress_account", "accounts", function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Capital Work in Progress",
					is_group: 0,
					company: d.company_name,
				},
			};
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
