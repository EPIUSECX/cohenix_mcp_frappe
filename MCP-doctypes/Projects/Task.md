# Master Control Plan: `Task`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `TASK-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Projects User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject` | Subject | Data | None | ✅ |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `issue` | Issue | Link | Issue |  |  |  | None | None |
| `type` | Type | Link | Task Type |  |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `is_template` | Is Template | Check | None |  |  |  | 0 | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Open
Working
Pending Review
Overdue
Template
Completed
Cancelled |  |  |  | None | None |
| `priority` | Priority | Select | Low
Medium
High
Urgent |  |  |  | None | None |
| `task_weight` | Weight | Float | None |  |  |  | None | None |
| `parent_task` | Parent Task | Link | Task |  |  |  | None | None |
| `completed_by` | Completed By | Link | User |  |  |  | None | None |
| `completed_on` | Completed On | Date | None |  |  |  | None | None |
| `sb_timeline` | Timeline | Section Break | None |  |  |  | None | None |
| `exp_start_date` | Expected Start Date | Datetime | None |  |  |  | None | None |
| `expected_time` | Expected Time (in hours) | Float | None |  |  |  | 0 | None |
| `start` | Begin On (Days) | Int | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `exp_end_date` | Expected End Date | Datetime | None |  |  |  | None | None |
| `progress` | % Progress | Percent | None |  |  |  | None | None |
| `duration` | Duration (Days) | Int | None |  |  |  | None | None |
| `is_milestone` | Is Milestone | Check | None |  |  |  | 0 | None |
| `sb_details` | Details | Section Break | None |  |  |  | None | None |
| `description` | Task Description | Text Editor | None |  |  |  | None | None |
| `sb_depends_on` | Dependencies | Section Break | None |  |  |  | None | None |
| `depends_on` | Dependent Tasks | Table | Task Depends On |  |  |  | None | None |
| `depends_on_tasks` | Depends on Tasks | Code | None |  | ✅ | ✅ | None | None |
| `sb_actual` | None | Section Break | None |  |  |  | None | None |
| `act_start_date` | Actual Start Date (via Timesheet) | Date | None |  |  | ✅ | None | None |
| `actual_time` | Actual Time in Hours (via Timesheet) | Float | None |  |  | ✅ | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `act_end_date` | Actual End Date (via Timesheet) | Date | None |  |  | ✅ | None | None |
| `sb_costing` | Costing | Section Break | None |  |  |  | None | None |
| `total_costing_amount` | Total Costing Amount (via Timesheet) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_expense_claim` | Total Expense Claim (via Expense Claim) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `total_billing_amount` | Total Billable Amount (via Timesheet) | Currency | None |  |  | ✅ | None | None |
| `sb_more_info` | More Info | Section Break | None |  |  |  | None | None |
| `review_date` | Review Date | Date | None |  |  |  | None | None |
| `closing_date` | Closing Date | Date | None |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `lft` | lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Data | None |  | ✅ | ✅ | None | None |
| `template_task` | Template Task | Data | None |  | ✅ |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `total_expense_claim` | Total Expense Claim (via Expense Claim) | Currency | Company:company:default_currency |  |  | ✅ | None | None |



### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/task/task.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.projects");

frappe.ui.form.on("Task", {
	setup: function (frm) {
		frm.make_methods = {
			Timesheet: () =>
				frappe.model.open_mapped_doc({
					method: "erpnext.projects.doctype.task.task.make_timesheet",
					frm: frm,
				}),
		};
	},
	onload: function (frm) {
		frm.set_query("task", "depends_on", function () {
			let filters = {
				name: ["!=", frm.doc.name],
			};
			if (frm.doc.project) filters["project"] = frm.doc.project;
			return {
				filters: filters,
			};
		});

		frm.set_query("parent_task", function () {
			let filters = {
				is_group: 1,
				name: ["!=", frm.doc.name],
			};
			if (frm.doc.project) filters["project"] = frm.doc.project;
			return {
				filters: filters,
			};
		});
	},

	is_group: function (frm) {
		frappe.call({
			method: "erpnext.projects.doctype.task.task.check_if_child_exists",
			args: {
				name: frm.doc.name,
			},
			callback: function (r) {
				if (r.message.length > 0) {
					let message = __(
						"Cannot convert Task to non-group because the following child Tasks exist: {0}.",
						[r.message.join(", ")]
					);
					frappe.msgprint(message);
					frm.reload_doc();
				}
			},
		});
	},

	validate: function (frm) {
		frm.doc.project && frappe.model.remove_from_locals("Project", frm.doc.project);
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Delayed Tasks Summary` | Script Report | Projects |



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
