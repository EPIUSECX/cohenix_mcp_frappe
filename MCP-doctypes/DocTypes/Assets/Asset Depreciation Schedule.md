# Master Control Plan: `Asset Depreciation Schedule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `asset` | Asset | Link | Asset | ✅ |  |  | None | None |
| `naming_series` | Naming Series | Select | ACC-ADS-.YYYY.- |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `gross_purchase_amount` | Gross Purchase Amount | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `opening_accumulated_depreciation` | Opening Accumulated Depreciation | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `opening_number_of_booked_depreciations` | Opening Number of Booked Depreciations | Int | None |  | ✅ | ✅ | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `finance_book_id` | Finance Book Id | Int | None |  | ✅ | ✅ | None | None |
| `depreciation_details_section` | Depreciation Details | Section Break | None |  |  |  | None | None |
| `depreciation_method` | Depreciation Method | Select | 
Straight Line
Double Declining Balance
Written Down Value
Manual |  |  | ✅ | None | None |
| `total_number_of_depreciations` | Total Number of Depreciations | Int | None |  |  | ✅ | None | None |
| `rate_of_depreciation` | Rate of Depreciation | Percent | None |  |  | ✅ | None | In Percentage |
| `daily_prorata_based` | Depreciate based on daily pro-rata | Check | None |  |  | ✅ | 0 | None |
| `shift_based` | Depreciate based on shifts | Check | None |  |  | ✅ | 0 | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `frequency_of_depreciation` | Frequency of Depreciation (Months) | Int | None |  |  | ✅ | None | None |
| `expected_value_after_useful_life` | Expected Value After Useful Life | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `value_after_depreciation` | Value After Depreciation | Currency | None |  |  | ✅ | None | None |
| `depreciation_schedule_section` | Depreciation Schedule | Section Break | None |  |  |  | None | None |
| `depreciation_schedule` | Depreciation Schedule | Table | Depreciation Schedule |  |  |  | None | None |
| `details_section` | Details | Section Break | None |  |  |  | None | None |
| `notes` | Notes | Small Text | None |  |  | ✅ | None | None |
| `status` | Status | Select | Draft
Active
Cancelled |  | ✅ | ✅ | None | None |
| `amended_from` | Amended From | Link | Asset Depreciation Schedule |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_depreciation_schedule/asset_depreciation_schedule.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.provide("erpnext.asset");

frappe.ui.form.on("Asset Depreciation Schedule", {
	onload: function (frm) {
		frm.events.make_schedules_editable(frm);
	},

	make_schedules_editable: function (frm) {
		var is_manual_hence_editable = frm.doc.depreciation_method === "Manual" ? true : false;
		var is_shift_hence_editable = frm.doc.shift_based ? true : false;

		frm.toggle_enable("depreciation_schedule", is_manual_hence_editable || is_shift_hence_editable);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable(
			"schedule_date",
			is_manual_hence_editable
		);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable(
			"depreciation_amount",
			is_manual_hence_editable
		);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable("shift", is_shift_hence_editable);
	},
});

frappe.ui.form.on("Depreciation Schedule", {
	make_depreciation_entry: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (!row.journal_entry) {
			frappe.call({
				method: "erpnext.assets.doctype.asset.depreciation.make_depreciation_entry",
				args: {
					depr_schedule_name: frm.doc.name,
					date: row.schedule_date,
				},
				debounce: 1000,
				callback: function (r) {
					frappe.model.sync(r.message);
					frm.refresh();
				},
			});
		}
	},

	depreciation_amount: function (frm, cdt, cdn) {
		erpnext.asset.set_accumulated_depreciation(frm);
	},
});

erpnext.asset.set_accumulated_depreciation = function (frm) {
	if (frm.doc.depreciation_method != "Manual") return;

	var accumulated_depreciation = flt(frm.doc.opening_accumulated_depreciation);

	$.each(frm.doc.depreciation_schedule || [], function (i, row) {
		accumulated_depreciation += flt(row.depreciation_amount);
		frappe.model.set_value(
			row.doctype,
			row.name,
			"accumulated_depreciation_amount",
			accumulated_depreciation
		);
	});
};

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
