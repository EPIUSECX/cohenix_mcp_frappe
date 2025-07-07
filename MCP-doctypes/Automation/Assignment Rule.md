# Master Control Plan: `Assignment Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Automation`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** Automatically Assign Documents to Users

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `due_date_based_on` | Due Date Based On | Select | None |  |  |  | None | Value from this field will be set as the due date in the ToDo |
| `priority` | Priority | Int | None |  |  |  | None | Higher priority rule will be applied first |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None | ✅ |  |  | Automatic Assignment | Example: {{ subject }} |
| `assignment_rules_section` | Assignment Rules | Section Break | None |  |  |  | None | None |
| `assign_condition` | Assign Condition | Code | PythonExpression | ✅ |  |  | None | Simple Python Expression, Example: status == 'Open' and type == 'Bug' |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `unassign_condition` | Unassign Condition | Code | PythonExpression |  |  |  | None | Simple Python Expression, Example: Status in ("Closed", "Cancelled") |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `close_condition` | Close Condition | Code | PythonExpression |  |  |  | None | Simple Python Expression, Example: Status in ("Invalid") |
| `sb` | Assignment Days | Section Break | None |  |  |  | None | None |
| `assignment_days` | Assignment Days | Table | Assignment Rule Day | ✅ |  |  | None | None |
| `assign_to_users_section` | Assign To Users | Section Break | None |  |  |  | None | None |
| `rule` | Rule | Select | Round Robin
Load Balancing
Based on Field | ✅ |  |  | None | None |
| `field` | Field | Select | None |  |  |  | None | None |
| `users` | Users | Table MultiSelect | Assignment Rule User |  |  |  | None | None |
| `last_user` | Last User | Link | User |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/assignment_rule/assignment_rule.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Assignment Rule", {
	refresh: function (frm) {
		frm.trigger("setup_assignment_days_buttons");
		frm.trigger("set_options");
		// refresh description
		frm.events.rule(frm);
	},

	setup: function (frm) {
		frm.set_query("document_type", () => {
			return {
				filters: {
					name: ["!=", "ToDo"],
				},
			};
		});
	},

	document_type: function (frm) {
		frm.trigger("set_options");
	},

	setup_assignment_days_buttons: function (frm) {
		const labels = ["Weekends", "Weekdays", "All Days"];
		let get_days = (label) => {
			const weekdays = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"];
			const weekends = ["Saturday", "Sunday"];
			return {
				"All Days": weekdays.concat(weekends),
				Weekdays: weekdays,
				Weekends: weekends,
			}[label];
		};

		let set_days = (e) => {
			frm.clear_table("assignment_days");
			const label = $(e.currentTarget).text();
			get_days(label).forEach((day) => frm.add_child("assignment_days", { day: day }));
			frm.refresh_field("assignment_days");
		};

		labels.forEach((label) =>
			frm.fields_dict["assignment_days"].grid.add_custom_button(label, set_days, "top")
		);
	},

	rule: function (frm) {
		const description_map = {
			"Round Robin": __("Assign one by one, in sequence"),
			"Load Balancing": __("Assign to the one who has the least assignments"),
			"Based on Field": __("Assign to the user set in this field"),
		};
		frm.get_field("rule").set_description(description_map[frm.doc.rule]);
	},

	set_options(frm) {
		const doctype = frm.doc.document_type;
		frm.set_fields_as_options(
			"field",
			doctype,
			(df) =>
				["Dynamic Link", "Data"].includes(df.fieldtype) ||
				(df.fieldtype == "Link" && df.options == "User"),
			[{ label: "Owner", value: "owner" }]
		);
		if (doctype) {
			frm.set_fields_as_options("due_date_based_on", doctype, (df) =>
				["Date", "Datetime"].includes(df.fieldtype)
			).then((options) =>
				frm.set_df_property("due_date_based_on", "hidden", !options.length)
			);
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
