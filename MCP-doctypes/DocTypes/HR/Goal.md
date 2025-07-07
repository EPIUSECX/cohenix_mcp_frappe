# Master Control Plan: `Goal`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:HR-GOAL-{YYYY}-{####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `goal_name` | Goal | Data | None | ✅ |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `parent_goal` | Parent Goal | Link | Goal |  |  |  | None | None |
| `column_break_tyox` | None | Column Break | None |  |  |  | None | None |
| `progress` | Progress | Percent | None |  |  |  | None | None |
| `status` | Status | Select | 
Pending
In Progress
Completed
Archived
Closed |  |  | ✅ | Pending | None |
| `section_break_nf0j` | None | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `user` | User | Data | None |  |  | ✅ | None | None |
| `column_break_ahxr` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `section_break_cycle` | Appraisal Linking | Section Break | None |  |  |  | None | Link the cycle and tag KRA to your goal to update the appraisal's goal score based on the goal progress |
| `appraisal_cycle` | Appraisal Cycle | Link | Appraisal Cycle |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `kra` | KRA | Link | KRA |  |  |  | None | None |
| `section_break_12` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `lft` | Left | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | Right | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Link | Goal |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/goal/goal.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Goal", {
	refresh(frm) {
		frm.trigger("set_filters");
		frm.trigger("add_custom_buttons");

		if (frm.doc.is_group) {
			frm.set_df_property(
				"progress",
				"description",
				__("Group goal's progress is auto-calculated based on the child goals."),
			);
		}
	},

	set_filters(frm) {
		frm.set_query("parent_goal", () => {
			return {
				filters: {
					is_group: 1,
					name: ["!=", frm.doc.name],
					employee: frm.doc.employee,
				},
			};
		});

		frm.set_query("kra", () => {
			return {
				query: "hrms.hr.doctype.appraisal.appraisal.get_kras_for_employee",
				filters: {
					employee: frm.doc.employee,
					appraisal_cycle: frm.doc.appraisal_cycle,
				},
			};
		});

		frm.set_query("appraisal_cycle", () => {
			return {
				filters: {
					status: ["!=", "Completed"],
					company: frm.doc.company,
				},
			};
		});
	},

	add_custom_buttons(frm) {
		if (frm.doc.__islocal || frm.doc.status === "Completed") return;
		const doc_status = frm.doc.status;

		if (doc_status === "Archived") {
			frm.add_custom_button(
				__("Unarchive"),
				() => {
					frm.set_value("status", "");
					frm.save();
				},
				__("Status"),
			);
		}

		if (doc_status === "Closed") {
			frm.add_custom_button(
				__("Reopen"),
				() => {
					frm.set_value("status", "");
					frm.save();
				},
				__("Status"),
			);
		}

		if (doc_status !== "Archived") {
			frm.add_custom_button(
				__("Archive"),
				() => {
					frm.set_value("status", "Archived");
					frm.save();
				},
				__("Status"),
			);
		}

		if (doc_status !== "Closed") {
			frm.add_custom_button(
				__("Close"),
				() => {
					frm.set_value("status", "Closed");
					frm.save();
				},
				__("Status"),
			);
		}
	},

	kra(frm) {
		if (!frm.doc.appraisal_cycle) {
			frm.set_value("kra", "");

			frappe.msgprint({
				message: __("Please select the Appraisal Cycle first."),
				title: __("Mandatory"),
			});

			return;
		}

		if (frm.doc.__islocal || !frm.doc.is_group) return;

		let msg = __(
			"Changing KRA in this parent goal will align all the child goals to the same KRA, if any.",
		);
		msg += "<br>";
		msg += __("Do you still want to proceed?");

		frappe.confirm(
			msg,
			() => {},
			() => {
				frappe.db.get_value("Goal", frm.doc.name, "kra", (r) =>
					frm.set_value("kra", r.kra),
				);
			},
		);
	},

	is_group(frm) {
		if (frm.doc.__islocal && frm.doc.is_group) {
			frm.set_value("progress", 0);
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
