# Master Control Plan: `Compensatory Leave Request`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-CMP-.YY.-.MM.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `leave_type` | Leave Type | Link | Leave Type |  |  |  | None | None |
| `leave_allocation` | Leave Allocation | Link | Leave Allocation |  |  | ✅ | None | None |
| `worked_on` | Worked On Holiday | Section Break | None |  |  |  | None | None |
| `work_from_date` | Work From Date | Date | None | ✅ |  |  | None | None |
| `work_end_date` | Work End Date | Date | None | ✅ |  |  | None | None |
| `half_day` | Half Day | Check | None |  |  |  | 0 | None |
| `half_day_date` | Half Day Date | Date | None |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `reason` | Reason | Small Text | None | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Compensatory Leave Request |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/compensatory_leave_request/compensatory_leave_request.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Compensatory Leave Request", {
	refresh: function (frm) {
		frm.set_query("leave_type", function () {
			return {
				filters: {
					is_compensatory: true,
				},
			};
		});
	},
	half_day: function (frm) {
		if (frm.doc.half_day == 1) {
			frm.set_df_property("half_day_date", "reqd", true);
		} else {
			frm.set_df_property("half_day_date", "reqd", false);
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
