# Master Control Plan: `Staffing Plan`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `staffing_plan_details` | Details | Section Break | None |  |  |  | None | None |
| `get_job_requisitions` | Get Job Requisitions | Button | None |  |  |  | None | None |
| `staffing_details` | Staffing Details | Table | Staffing Plan Detail | ✅ |  |  | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `total_estimated_budget` | Total Estimated Budget | Currency | Company:company:default_currency |  |  | ✅ | 0.00 | None |
| `amended_from` | Amended From | Link | Staffing Plan |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/staffing_plan/staffing_plan.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Staffing Plan", {
	setup: function (frm) {
		frm.set_query("designation", "staffing_details", function () {
			let designations = [];
			(frm.doc.staffing_details || []).forEach(function (staff_detail) {
				if (staff_detail.designation) {
					designations.push(staff_detail.designation);
				}
			});
			// Filter out designations already selected in Staffing Plan Detail
			return {
				filters: [["Designation", "name", "not in", designations]],
			};
		});

		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},

	get_job_requisitions: function (frm) {
		new frappe.ui.form.MultiSelectDialog({
			doctype: "Job Requisition",
			target: frm,
			date_field: "posting_date",
			add_filters_group: 1,
			setters: {
				designation: null,
				requested_by: null,
			},
			get_query() {
				let filters = {
					company: frm.doc.company,
					status: ["in", ["Pending", "Open & Approved"]],
				};

				if (frm.doc.department) filters.department = frm.doc.department;

				return {
					filters: filters,
				};
			},
			action(selections) {
				const plan_name = frm.doc.__newname;
				frappe
					.call({
						method: "set_job_requisitions",
						doc: frm.doc,
						args: selections,
					})
					.then(() => {
						// hack to retain prompt name that gets lost on frappe.call
						frm.doc.__newname = plan_name;
						refresh_field("staffing_details");
					});

				cur_dialog.hide();
			},
		});
	},
});

frappe.ui.form.on("Staffing Plan Detail", {
	designation: function (frm, cdt, cdn) {
		let child = locals[cdt][cdn];
		if (frm.doc.company && child.designation) {
			set_number_of_positions(frm, cdt, cdn);
		}
	},

	vacancies: function (frm, cdt, cdn) {
		let child = locals[cdt][cdn];
		if (child.vacancies < child.current_openings) {
			frappe.throw(__("Vacancies cannot be lower than the current openings"));
		}
		set_number_of_positions(frm, cdt, cdn);
	},

	current_count: function (frm, cdt, cdn) {
		set_number_of_positions(frm, cdt, cdn);
	},

	estimated_cost_per_position: function (frm, cdt, cdn) {
		set_total_estimated_cost(frm, cdt, cdn);
	},
});

var set_number_of_positions = function (frm, cdt, cdn) {
	let child = locals[cdt][cdn];
	if (!child.designation) frappe.throw(__("Please enter the designation"));
	frappe.call({
		method: "hrms.hr.doctype.staffing_plan.staffing_plan.get_designation_counts",
		args: {
			designation: child.designation,
			company: frm.doc.company,
		},
		callback: function (data) {
			if (data.message) {
				frappe.model.set_value(cdt, cdn, "current_count", data.message.employee_count);
				frappe.model.set_value(cdt, cdn, "current_openings", data.message.job_openings);
				let total_positions = cint(data.message.employee_count) + cint(child.vacancies);
				if (cint(child.number_of_positions) < total_positions) {
					frappe.model.set_value(cdt, cdn, "number_of_positions", total_positions);
				}
			} else {
				// No employees for this designation
				frappe.model.set_value(cdt, cdn, "current_count", 0);
				frappe.model.set_value(cdt, cdn, "current_openings", 0);
			}
		},
	});
	refresh_field("staffing_details");
	set_total_estimated_cost(frm, cdt, cdn);
};

// Note: Estimated Cost is calculated on number of Vacancies
var set_total_estimated_cost = function (frm, cdt, cdn) {
	let child = locals[cdt][cdn];
	if (child.vacancies > 0 && child.estimated_cost_per_position) {
		frappe.model.set_value(
			cdt,
			cdn,
			"total_estimated_cost",
			child.vacancies * child.estimated_cost_per_position,
		);
	} else {
		frappe.model.set_value(cdt, cdn, "total_estimated_cost", 0);
	}
	set_total_estimated_budget(frm);
};

var set_total_estimated_budget = function (frm) {
	let estimated_budget = 0.0;
	if (frm.doc.staffing_details) {
		(frm.doc.staffing_details || []).forEach(function (staff_detail) {
			if (staff_detail.total_estimated_cost) {
				estimated_budget += staff_detail.total_estimated_cost;
			}
		});
		frm.set_value("total_estimated_budget", estimated_budget);
	}
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Recruitment Analytics` | Script Report | HR |



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
