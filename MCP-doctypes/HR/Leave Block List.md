# Master Control Plan: `Leave Block List`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:leave_block_list_name`
- **Description:** Block Holidays on important days.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `leave_block_list_name` | Leave Block List Name | Data | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `applies_to_all_departments` | Applies to Company | Check | None |  |  |  | 0 | If not checked, the list will have to be added to each Department where it has to be applied. |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `leave_type` | Leave Type | Link | Leave Type |  |  |  | None | None |
| `block_days` | Block Days | Section Break | None |  |  |  | None | Stop users from making Leave Applications on following days. |
| `add_day_wise_dates` | Add Day-wise Dates | Button | None |  |  |  | None | None |
| `leave_block_list_dates` | Leave Block List Dates | Table | Leave Block List Date | ✅ |  |  | None | None |
| `allow_list` | Allow Users | Section Break | None |  |  |  | None | Allow the following users to approve Leave Applications for block days. |
| `leave_block_list_allowed` | Leave Block List Allowed | Table | Leave Block List Allow |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_block_list/leave_block_list.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Leave Block List", {
	add_day_wise_dates: function (frm) {
		let d = new frappe.ui.Dialog({
			title: "Add Leave Block Dates",
			fields: [
				{
					label: "Start Date",
					fieldname: "start_date",
					fieldtype: "Date",
					reqd: 1,
				},
				{
					fieldname: "col_break_0",
					fieldtype: "Column Break",
				},
				{
					label: "End Date",
					fieldname: "end_date",
					fieldtype: "Date",
					reqd: 1,
				},
				{
					fieldname: "sec_break_0",
					fieldtype: "Section Break",
				},
				{
					fieldname: "days",
					fieldtype: "MultiCheck",
					select_all: true,
					columns: 3,
					reqd: 1,
					options: [
						{
							label: __("Monday"),
							value: "Monday",
							checked: 0,
						},
						{
							label: __("Tuesday"),
							value: "Tuesday",
							checked: 0,
						},
						{
							label: __("Wednesday"),
							value: "Wednesday",
							checked: 0,
						},
						{
							label: __("Thursday"),
							value: "Thursday",
							checked: 0,
						},
						{
							label: __("Friday"),
							value: "Friday",
							checked: 0,
						},
						{
							label: __("Saturday"),
							value: "Saturday",
							checked: 0,
						},
						{
							label: __("Sunday"),
							value: "Sunday",
							checked: 0,
						},
					],
				},
				{
					fieldname: "sec_break_0",
					fieldtype: "Section Break",
				},
				{
					label: "Reason",
					fieldname: "reason",
					fieldtype: "Small Text",
					reqd: 1,
				},
			],
			primary_action_label: "Add",
			primary_action(values) {
				frm.call("set_weekly_off_dates", {
					start_date: d.get_value("start_date"),
					end_date: d.get_value("end_date"),
					reason: d.get_value("reason"),
					days: d.get_value("days"),
				});
				frm.dirty();
				d.hide();
			},
		});

		d.show();
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
