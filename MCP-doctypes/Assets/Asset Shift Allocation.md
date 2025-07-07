# Master Control Plan: `Asset Shift Allocation`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_esaa` | None | Section Break | None |  |  |  | None | None |
| `asset` | Asset | Link | Asset | ✅ |  |  | None | None |
| `naming_series` | Naming Series | Select | ACC-ASA-.YYYY.- | ✅ |  |  | None | None |
| `column_break_tdae` | None | Column Break | None |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `amended_from` | Amended From | Link | Asset Shift Allocation |  |  | ✅ | None | None |
| `depreciation_schedule_section` | Depreciation Schedule | Section Break | None |  |  |  | None | None |
| `column_break_jomc` | None | Column Break | None |  |  |  | None | None |
| `depreciation_schedule` | Depreciation Schedule | Table | Depreciation Schedule |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_shift_allocation/asset_shift_allocation.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.ui.form.on("Asset Shift Allocation", {
	onload: function (frm) {
		frm.set_query("asset", function () {
			return {
				filters: {
					company: frm.doc.company,
					docstatus: 1,
				},
			};
		});

		frm.events.make_schedules_editable(frm);
	},

	make_schedules_editable: function (frm) {
		frm.toggle_enable("depreciation_schedule", true);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable("schedule_date", false);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable("depreciation_amount", false);
		frm.fields_dict["depreciation_schedule"].grid.toggle_enable("shift", true);
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
