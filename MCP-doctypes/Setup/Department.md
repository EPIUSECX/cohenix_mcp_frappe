# Master Control Plan: `Department`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Academics User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `department_name` | Department | Data | None | ✅ |  |  | None | None |
| `parent_department` | Parent Department | Link | Department |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `lft` | lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Data | None |  | ✅ |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `payroll_cost_center` | Payroll Cost Center | Link | Cost Center |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `leave_block_list` | Leave Block List | Link | Leave Block List |  |  |  | None | Days for which Holidays are blocked for this department. |
| `approvers` | Approvers | Section Break | None |  |  |  | None | The first Approver in the list will be set as the default Approver. |
| `shift_request_approver` | Shift Request Approver | Table | Department Approver |  |  |  | None | None |
| `leave_approvers` | Leave Approver | Table | Department Approver |  |  |  | None | None |
| `expense_approvers` | Expense Approver | Table | Department Approver |  |  |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `expense_approvers` | Expense Approver | Table | Department Approver |  |  |  | None | None |
| `leave_approvers` | Leave Approver | Table | Department Approver |  |  |  | None | None |
| `shift_request_approver` | Shift Request Approver | Table | Department Approver |  |  |  | None | None |
| `approvers` | Approvers | Section Break | None |  |  |  | None | The first Approver in the list will be set as the default Approver. |
| `leave_block_list` | Leave Block List | Link | Leave Block List |  |  |  | None | Days for which Holidays are blocked for this department. |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `payroll_cost_center` | Payroll Cost Center | Link | Cost Center |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 6

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/department/department.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Department", {
	onload: function (frm) {
		frm.set_query("parent_department", function () {
			return { filters: [["Department", "is_group", "=", 1]] };
		});
	},
	refresh: function (frm) {
		// read-only for root department
		if (!frm.doc.parent_department && !frm.is_new()) {
			frm.set_read_only();
			frm.set_intro(__("This is a root department and cannot be edited."));
		}
	},
	validate: function (frm) {
		if (frm.doc.name == "All Departments") {
			frappe.throw(__("You cannot edit root node."));
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
