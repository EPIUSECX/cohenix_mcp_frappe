# Master Control Plan: `Appraisal Cycle`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:cycle_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `overview_tab` | Overview | Tab Break | None |  |  |  | None | None |
| `cycle_name` | Cycle Name | Data | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `status` | Status | Select | Not Started
In Progress
Completed |  |  | ✅ | Not Started | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None | ✅ |  |  | None | None |
| `section_break_4` | Description | Section Break | None |  |  |  | None | None |
| `description` | None | Text Editor | None |  |  |  | None | None |
| `settings_section` | Settings | Section Break | None |  |  |  | None | None |
| `column_break_vhzx` | None | Column Break | None |  |  |  | None | None |
| `kra_evaluation_method` | KRA Evaluation Method | Select | Automated Based on Goal Progress
Manual Rating |  |  |  | Automated Based on Goal Progress | None |
| `section_break_zykh` | None | Section Break | None |  |  |  | None | None |
| `calculate_final_score_based_on_formula` | Calculate Final Score based on Formula | Check | None |  |  |  | 0 | By default, the Final Score is calculated as the average of Goal Score, Feedback Score, and Self Appraisal Score. Enable this to set a different formula |
| `final_score_formula` | Final Score Formula | Code | PythonExpression |  |  |  | None | None |
| `applicable_for_tab` | Applicable For | Tab Break | None |  |  |  | None | None |
| `filters_section` | Filters | Section Break | None |  |  |  | None | Set optional filters to fetch employees in the appraisee list |
| `branch` | Branch | Link | Branch |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `employees_section` | Employees | Section Break | None |  |  |  | None | None |
| `get_employees` | Get Employees | Button | None |  |  |  | None | None |
| `appraisees` | None | Table | Appraisee |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/appraisal_cycle/appraisal_cycle.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Appraisal Cycle", {
	refresh(frm) {
		frm.set_query("department", () => {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});

		frm.trigger("show_custom_buttons");
		frm.trigger("show_appraisal_summary");
		frm.trigger("set_autocompletions_for_final_score_formula");
	},

	show_custom_buttons(frm) {
		if (frm.doc.__islocal) return;

		frm.add_custom_button(__("View Goals"), () => {
			frappe.route_options = {
				company: frm.doc.company,
				appraisal_cycle: frm.doc.name,
			};
			frappe.set_route("Tree", "Goal");
		});

		let appraisals_created = frm.doc.__onload?.appraisals_created;

		if (frm.doc.status !== "Completed") {
			if (appraisals_created) {
				frm.add_custom_button(__("Create Appraisals"), () => {
					frm.trigger("create_appraisals");
				});
			} else {
				frm.page.set_primary_action(__("Create Appraisals"), () => {
					frm.trigger("create_appraisals");
				});
			}
		}

		if (frm.doc.status === "Not Started") {
			if (appraisals_created) {
				frm.page.set_primary_action(__("Start"), () => {
					frm.set_value("status", "In Progress");
					frm.save();
				});
			} else {
				frm.add_custom_button(__("Start"), () => {
					frm.set_value("status", "In Progress");
					frm.save();
				});
			}
		} else if (frm.doc.status === "In Progress") {
			if (appraisals_created) {
				frm.page.set_primary_action(__("Mark as Completed"), () => {
					frm.trigger("complete_cycle");
				});
			} else {
				frm.add_custom_button(__("Mark as Completed"), () => {
					frm.trigger("complete_cycle");
				});
			}
		} else if (frm.doc.status === "Completed") {
			frm.add_custom_button(__("Mark as In Progress"), () => {
				frm.set_value("status", "In Progress");
				frm.save();
			});
		}
	},

	set_autocompletions_for_final_score_formula: async (frm) => {
		const autocompletions = [
			{
				value: "goal_score",
				score: 10,
				meta: __("Total Goal Score"),
			},
			{
				value: "average_feedback_score",
				score: 10,
				meta: __("Average Feedback Score"),
			},
			{
				value: "self_appraisal_score",
				score: 10,
				meta: __("Self Appraisal Score"),
			},
		];

		await Promise.all(
			["Employee", "Appraisal Cycle", "Appraisal"].map((doctype) =>
				frappe.model.with_doctype(doctype, () => {
					autocompletions.push(...hrms.get_doctype_fields_for_autocompletion(doctype));
				}),
			),
		);

		frm.set_df_property("final_score_formula", "autocompletions", autocompletions);
	},

	get_employees(frm) {
		frappe.call({
			method: "set_employees",
			doc: frm.doc,
			freeze: true,
			freeze_message: __("Fetching Employees"),
			callback: function () {
				refresh_field("appraisees");
				frm.dirty();
			},
		});
	},

	create_appraisals(frm) {
		frm.call({
			method: "create_appraisals",
			doc: frm.doc,
			freeze: true,
		}).then((r) => {
			if (!r.exc) {
				frm.reload_doc();
			}
		});
	},

	complete_cycle(frm) {
		let msg = __(
			"This action will prevent making changes to the linked appraisal feedback/goals.",
		);
		msg += "<br>";
		msg += __("Are you sure you want to proceed?");

		frappe.confirm(msg, () => {
			frm.call({
				method: "complete_cycle",
				doc: frm.doc,
				freeze: true,
			}).then((r) => {
				if (!r.exc) {
					frm.reload_doc();
				}
			});
		});
	},

	show_appraisal_summary(frm) {
		if (frm.doc.__islocal) return;

		frappe
			.call("hrms.hr.doctype.appraisal_cycle.appraisal_cycle.get_appraisal_cycle_summary", {
				cycle_name: frm.doc.name,
			})
			.then((r) => {
				if (r.message) {
					frm.dashboard.add_indicator(
						__("Appraisees: {0}", [r.message.appraisees]),
						"blue",
					);
					frm.dashboard.add_indicator(
						__("Self Appraisal Pending: {0}", [r.message.self_appraisal_pending]),
						"orange",
					);
					frm.dashboard.add_indicator(
						__("Employees without Feedback: {0}", [r.message.feedback_missing]),
						"orange",
					);
					frm.dashboard.add_indicator(
						__("Employees without Goals: {0}", [r.message.goals_missing]),
						"orange",
					);
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
