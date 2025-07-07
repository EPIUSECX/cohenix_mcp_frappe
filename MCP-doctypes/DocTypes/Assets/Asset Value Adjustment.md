# Master Control Plan: `Asset Value Adjustment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company |  |  |  | None | None |
| `asset` | Asset | Link | Asset | ✅ |  |  | None | None |
| `asset_category` | Asset Category | Read Only | None |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `date` | Date | Date | None | ✅ |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `amended_from` | Amended From | Link | Asset Value Adjustment |  |  | ✅ | None | None |
| `value_details_section` | Value Details | Section Break | None |  |  |  | None | None |
| `current_asset_value` | Current Asset Value | Currency | None | ✅ |  | ✅ | None | None |
| `new_asset_value` | New Asset Value | Currency | None | ✅ |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `difference_amount` | Difference Amount | Currency | None |  |  | ✅ | None | None |
| `difference_account` | Difference Account | Link | Account | ✅ |  |  | None | None |
| `journal_entry` | Journal Entry | Link | Journal Entry |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_value_adjustment/asset_value_adjustment.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Asset Value Adjustment", {
	setup: function (frm) {
		frm.set_query("cost_center", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
		frm.set_query("asset", function () {
			return {
				filters: {
					calculate_depreciation: 1,
					docstatus: 1,
				},
			};
		});
		frm.set_query("difference_account", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
	},

	onload: function (frm) {
		if (frm.is_new() && frm.doc.asset) {
			frm.trigger("set_current_asset_value");
		}

		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	asset: function (frm) {
		frm.trigger("set_acc_dimension");
		if (frm.doc.asset) {
			frm.trigger("set_current_asset_value");
		}
	},

	finance_book: function (frm) {
		frm.trigger("set_current_asset_value");
	},

	set_current_asset_value: function (frm) {
		if (frm.doc.asset) {
			frm.call({
				method: "erpnext.assets.doctype.asset.asset.get_asset_value_after_depreciation",
				args: {
					asset_name: frm.doc.asset,
					finance_book: frm.doc.finance_book,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("current_asset_value", r.message);
					}
				},
			});
		}
	},

	set_acc_dimension: function (frm) {
		if (frm.doc.asset) {
			frm.call({
				method: "erpnext.assets.doctype.asset_value_adjustment.asset_value_adjustment.get_value_of_accounting_dimensions",
				args: {
					asset_name: frm.doc.asset,
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
