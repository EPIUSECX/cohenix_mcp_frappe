# Master Control Plan: `Projects Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `timesheet_sb` | Timesheets | Section Break | None |  |  |  | None | None |
| `ignore_workstation_time_overlap` | Ignore Workstation Time Overlap | Check | None |  |  |  | 0 | None |
| `ignore_user_time_overlap` | Ignore User Time Overlap | Check | None |  |  |  | 0 | None |
| `ignore_employee_time_overlap` | Ignore Employee Time Overlap | Check | None |  |  |  | 0 | None |
| `fetch_timesheet_in_sales_invoice` | Fetch Timesheet in Sales Invoice | Check | None |  |  |  | 0 | Enabling the check box will fetch timesheet on select of a Project in Sales Invoice |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/projects_settings/projects_settings.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Projects Settings", {
	refresh: function (frm) {},
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
