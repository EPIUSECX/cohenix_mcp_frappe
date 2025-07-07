# Master Control Plan: `Activity Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Keep track of all update feeds

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject` | Subject | Small Text | None | ✅ |  |  | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `content` | Message | Text Editor | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `additional_info` | More Information | Section Break | None |  |  |  | None | None |
| `communication_date` | Date | Datetime | None |  |  |  | Now | None |
| `ip_address` | IP Address | Data | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `operation` | Operation | Select | 
Login
Logout
Impersonate |  |  |  | None | None |
| `status` | Status | Select | 
Success
Failed
Linked
Closed |  |  |  | None | None |
| `reference_section` | Reference | Section Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_doctype |  |  |  | None | None |
| `reference_owner` | Reference Owner | Read Only | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `timeline_doctype` | Timeline DocType | Link | DocType |  |  |  | None | None |
| `timeline_name` | Timeline Name | Dynamic Link | timeline_doctype |  |  |  | None | None |
| `link_doctype` | Link DocType | Link | DocType |  |  | ✅ | None | None |
| `link_name` | Link Name | Dynamic Link | link_doctype |  |  | ✅ | None | None |
| `user` | User | Link | User |  |  | ✅ | __user | None |
| `full_name` | Full Name | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 3
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/activity_log/activity_log.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Activity Log", {
	refresh: function (frm) {
		// Nothing in this form is supposed to be editable.
		frm.disable_form();
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
