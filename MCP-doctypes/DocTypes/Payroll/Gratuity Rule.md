# Master Control Plan: `Gratuity Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `gratuity_details_tab` | Gratuity | Section Break | None |  |  |  | None | None |
| `disable` | Disable | Check | None |  |  |  | 0 | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `calculate_gratuity_amount_based_on` | Calculate Gratuity Amount Based On | Select | Current Slab
Sum of all previous slabs | ✅ |  |  | None | None |
| `total_working_days_per_year` | Total working Days Per Year | Int | None |  |  |  | 365 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `work_experience_calculation_function` | Work Experience Calculation Method | Select | Round off Work Experience
Take Exact Completed Years
Manual |  |  |  | Round off Work Experience | None |
| `minimum_year_for_gratuity` | Minimum Year for Gratuity | Int | None |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `applicable_earnings_component` | Applicable Earnings Component | Table MultiSelect | Gratuity Applicable Component | ✅ |  |  | None | Salary components should be part of the Salary Structure. |
| `gratuity_rules_section` | Rules | Section Break | None |  |  |  | None | None |
| `gratuity_rule_slabs` | Current Work Experience | Table | Gratuity Rule Slab | ✅ |  |  | None | Set "From(Year)" and "To(Year)" to 0 for no upper and lower limit. |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/gratuity_rule/gratuity_rule.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Gratuity Rule", {
	// refresh: function(frm) {
	// }
});

frappe.ui.form.on("Gratuity Rule Slab", {
	/*
		Slabs should be in order like

		from | to | fraction
		0    | 4  | 0.5
		4    | 6  | 0.7

		So, on row addition setting current_row.from = previous row.to.
		On to_year insert we have to check that it is not less than from_year

		Wrong order may lead to Wrong Calculation
	*/

	gratuity_rule_slabs_add(frm, cdt, cdn) {
		let row = locals[cdt][cdn];
		let array_idx = row.idx - 1;
		if (array_idx > 0) {
			row.from_year = cur_frm.doc.gratuity_rule_slabs[array_idx - 1].to_year;
			frm.refresh();
		}
	},

	to_year(frm, cdt, cdn) {
		let row = locals[cdt][cdn];
		if (row.to_year <= row.from_year && row.to_year === 0) {
			frappe.throw(__("To(Year) year can not be less than From(year)"));
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
