# Master Control Plan: `Shift Schedule Assignment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `HR-SHSA-.YY.-.MM.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `shift_details_section` | Employee Details | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `column_break_toss` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `schedule_settings_section` | Shift Details | Section Break | None |  |  |  | None | None |
| `shift_schedule` | Shift Schedule | Link | Shift Schedule | ✅ |  |  | None | None |
| `shift_location` | Shift Location | Link | Shift Location |  |  |  | None | None |
| `shift_status` | Shift Status | Select | Active
Inactive |  |  |  | Active | None |
| `column_break_iprq` | None | Column Break | None |  |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 1 | Select this if you want shift assignments to be automatically created indefinitely. |
| `create_shifts_after` | Create Shifts After | Date | None |  |  |  | Today | New shift assignments will be created after this date. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_schedule_assignment/shift_schedule_assignment.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Shift Schedule Assignment", {
// 	refresh(frm) {

// 	},
// });

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
