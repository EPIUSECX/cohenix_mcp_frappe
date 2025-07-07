# Master Control Plan: `Shift Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `start_time` | Start Time | Time | None | ✅ |  |  | None | None |
| `end_time` | End Time | Time | None | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List |  |  |  | None | None |
| `color` | Roster Color | Select | Blue
Cyan
Fuchsia
Green
Lime
Orange
Pink
Red
Violet
Yellow |  |  |  | Blue | None |
| `enable_auto_attendance` | Enable Auto Attendance | Check | None |  |  |  | 0 | Mark attendance based on 'Employee Checkin' for Employees assigned to this shift. |
| `auto_attendance_settings_section` | Auto Attendance Settings | Section Break | None |  |  |  | None | None |
| `determine_check_in_and_check_out` | Determine Check-in and Check-out | Select | Alternating entries as IN and OUT during the same shift
Strictly based on Log Type in Employee Checkin |  |  |  | None | None |
| `working_hours_calculation_based_on` | Working Hours Calculation Based On | Select | First Check-in and Last Check-out
Every Valid Check-in and Check-out |  |  |  | None | None |
| `begin_check_in_before_shift_start_time` | Begin check-in before shift start time (in minutes) | Int | None |  |  |  | 60 | The time before the shift start time during which Employee Check-in is considered for attendance. |
| `allow_check_out_after_shift_end_time` | Allow check-out after shift end time (in minutes) | Int | None |  |  |  | 60 | Time after the end of shift during which check-out is considered for attendance. |
| `mark_auto_attendance_on_holidays` | Mark Auto Attendance on Holidays | Check | None |  |  |  | 0 | If enabled, auto attendance will be marked on holidays if Employee Checkins exist |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `working_hours_threshold_for_half_day` | Working Hours Threshold for Half Day | Float | None |  |  |  | None | Working hours below which Half Day is marked. (Zero to disable) |
| `working_hours_threshold_for_absent` | Working Hours Threshold for Absent | Float | None |  |  |  | None | Working hours below which Absent is marked. (Zero to disable) |
| `process_attendance_after` | Process Attendance After | Date | None |  |  |  | Today | Attendance will be marked automatically only after this date. |
| `last_sync_of_checkin` | Last Sync of Checkin | Datetime | None |  |  |  | None | Last Known Successful Sync of Employee Checkin. Reset this only if you are sure that all Logs are synced from all the locations. Please don't modify this if you are unsure. |
| `auto_update_last_sync` | Automatically update Last Sync of Checkin | Check | None |  |  |  | 0 | Recommended for a single biometric device / checkins via mobile app |
| `grace_period_settings_auto_attendance_section` | Late Entry & Early Exit Settings for Auto Attendance | Section Break | None |  |  |  | None | None |
| `enable_late_entry_marking` | Enable Late Entry Marking | Check | None |  |  |  | 0 | None |
| `late_entry_grace_period` | Late Entry Grace Period | Int | None |  |  |  | None | The time after the shift start time when check-in is considered as late (in minutes). |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `enable_early_exit_marking` | Enable Early Exit Marking | Check | None |  |  |  | 0 | None |
| `early_exit_grace_period` | Early Exit Grace Period | Int | None |  |  |  | None | The time before the shift end time when check-out is considered as early (in minutes). |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_type/shift_type.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Shift Type", {
	refresh: function (frm) {
		if (frm.doc.__islocal) return;

		hrms.add_shift_tools_button_to_form(frm, {
			action: "Assign Shift",
			shift_type: frm.doc.name,
		});

		frm.add_custom_button(__("Mark Attendance"), () => {
			if (!frm.doc.enable_auto_attendance) {
				frm.scroll_to_field("enable_auto_attendance");
				frappe.throw(__("Please Enable Auto Attendance and complete the setup first."));
			}

			if (!frm.doc.process_attendance_after) {
				frm.scroll_to_field("process_attendance_after");
				frappe.throw(__("Please set {0}.", [__("Process Attendance After").bold()]));
			}

			if (!frm.doc.last_sync_of_checkin) {
				frm.scroll_to_field("last_sync_of_checkin");
				frappe.throw(__("Please set {0}.", [__("Last Sync of Checkin").bold()]));
			}

			frm.call({
				doc: frm.doc,
				method: "process_auto_attendance",
				freeze: true,
				callback: () => {
					frappe.msgprint(__("Attendance has been marked as per employee check-ins"));
				},
			});
		});
	},

	auto_update_last_sync: function (frm) {
		if (frm.doc.auto_update_last_sync) {
			frm.set_value("last_sync_of_checkin", "");
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
