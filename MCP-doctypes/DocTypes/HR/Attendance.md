# Master Control Plan: `Attendance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `attendance_details` | None | Section Break | Simple |  |  |  | None | None |
| `naming_series` | Series | Select | HR-ATT-.YYYY.- | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `working_hours` | Working Hours | Float | None |  |  | ✅ | None | None |
| `status` | Status | Select | 
Present
Absent
On Leave
Half Day
Work From Home | ✅ |  |  | Present | None |
| `leave_type` | Leave Type | Link | Leave Type |  |  |  | None | None |
| `leave_application` | Leave Application | Link | Leave Application |  |  | ✅ | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `attendance_date` | Attendance Date | Date | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `attendance_request` | Attendance Request | Link | Attendance Request |  |  | ✅ | None | None |
| `half_day_status` | Status for Other Half | Select | 
Present
Absent |  |  |  | None | None |
| `details_section` | Details | Section Break | None |  |  |  | None | None |
| `shift` | Shift | Link | Shift Type |  |  |  | None | None |
| `in_time` | In Time | Datetime | None |  |  | ✅ | None | None |
| `out_time` | Out Time | Datetime | None |  |  | ✅ | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `late_entry` | Late Entry | Check | None |  |  |  | 0 | None |
| `early_exit` | Early Exit | Check | None |  |  |  | 0 | None |
| `amended_from` | Amended From | Link | Attendance |  |  | ✅ | None | None |
| `modify_half_day_status` | modify_half_day_status | Check | None |  | ✅ |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/attendance/attendance.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Attendance", {
	refresh(frm) {
		if (frm.doc.__islocal && !frm.doc.attendance_date) {
			frm.set_value("attendance_date", frappe.datetime.get_today());
		}

		frm.set_query("employee", () => {
			return {
				query: "erpnext.controllers.queries.employee_query",
			};
		});
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Shift Attendance` | Script Report | HR |
| `Employees working on a holiday` | Script Report | HR |
| `Monthly Attendance Sheet` | Script Report | HR |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Early Exit (This Month)` | Early Exit (This Month) | Count | HR |
| `Late Entry (This Month)` | Late Entry (This Month) | Count | HR |
| `Total Absent (This Month)` | Total Absent (This Month) | Count | HR |
| `Total Present (This Month)` | Total Present (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
