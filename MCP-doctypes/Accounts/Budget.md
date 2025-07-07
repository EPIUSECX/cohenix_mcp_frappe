# Master Control Plan: `Budget`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | BUDGET-.YYYY.- | ✅ |  |  | None | None |
| `budget_against` | Budget Against | Select | 
Cost Center
Project | ✅ |  |  | Cost Center | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `fiscal_year` | Fiscal Year | Link | Fiscal Year | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `monthly_distribution` | Monthly Distribution | Link | Monthly Distribution |  |  |  | None | None |
| `amended_from` | Amended From | Link | Budget |  |  | ✅ | None | None |
| `section_break_6` | Control Action | Section Break | None |  |  |  | None | None |
| `applicable_on_material_request` | Applicable on Material Request | Check | None |  |  |  | 0 | None |
| `action_if_annual_budget_exceeded_on_mr` | Action if Annual Budget Exceeded on MR | Select | 
Stop
Warn
Ignore |  |  |  | Stop | None |
| `action_if_accumulated_monthly_budget_exceeded_on_mr` | Action if Accumulated Monthly Budget Exceeded on MR | Select | 
Stop
Warn
Ignore |  |  |  | Warn | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `applicable_on_purchase_order` | Applicable on Purchase Order | Check | None |  |  |  | 0 | None |
| `action_if_annual_budget_exceeded_on_po` | Action if Annual Budget Exceeded on PO | Select | 
Stop
Warn
Ignore |  |  |  | Stop | None |
| `action_if_accumulated_monthly_budget_exceeded_on_po` | Action if Accumulated Monthly Budget Exceeded on PO | Select | 
Stop
Warn
Ignore |  |  |  | Warn | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `applicable_on_booking_actual_expenses` | Applicable on booking actual expenses | Check | None |  |  |  | 0 | None |
| `action_if_annual_budget_exceeded` | Action if Annual Budget Exceeded on Actual | Select | 
Stop
Warn
Ignore |  |  |  | Stop | None |
| `action_if_accumulated_monthly_budget_exceeded` | Action if Accumulated Monthly Budget Exceeded on Actual | Select | 
Stop
Warn
Ignore |  |  |  | Warn | None |
| `control_action_for_cumulative_expense_section` | Control Action for Cumulative Expense | Section Break | None |  |  |  | None | None |
| `applicable_on_cumulative_expense` | Applicable on Cumulative Expense | Check | None |  |  |  | 0 | (Purchase Order + Material Request + Actual Expense) |
| `action_if_annual_exceeded_on_cumulative_expense` | Action if Anual Budget Exceeded on Cumulative Expense | Select | 
Stop
Warn
Ignore |  |  |  | None | None |
| `action_if_accumulated_monthly_exceeded_on_cumulative_expense` | Action if Accumulative Monthly Budget Exceeded on Cumulative Expense | Select | 
Stop
Warn
Ignore |  |  |  | None | None |
| `section_break_21` | None | Section Break | None |  |  |  | None | None |
| `accounts` | Budget Accounts | Table | Budget Account | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/budget/budget.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Budget", {
	onload: function (frm) {
		frm.set_query("account", "accounts", function () {
			return {
				filters: {
					company: frm.doc.company,
					report_type: "Profit and Loss",
					is_group: 0,
				},
			};
		});

		frm.set_query("monthly_distribution", function () {
			return {
				filters: {
					fiscal_year: frm.doc.fiscal_year,
				},
			};
		});

		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
		frappe.db.get_single_value("Accounts Settings", "use_new_budget_controller").then((value) => {
			if (!value) {
				frm.get_field("control_action_for_cumulative_expense_section").hide();
			}
		});
	},

	refresh: function (frm) {
		frm.trigger("toggle_reqd_fields");
	},

	budget_against: function (frm) {
		frm.trigger("set_null_value");
		frm.trigger("toggle_reqd_fields");
	},

	set_null_value: function (frm) {
		if (frm.doc.budget_against == "Cost Center") {
			frm.set_value("project", null);
		} else {
			frm.set_value("cost_center", null);
		}
	},

	toggle_reqd_fields: function (frm) {
		frm.toggle_reqd("cost_center", frm.doc.budget_against == "Cost Center");
		frm.toggle_reqd("project", frm.doc.budget_against == "Project");
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
