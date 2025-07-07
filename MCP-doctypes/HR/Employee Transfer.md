# Master Control Plan: `Employee Transfer`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-EMP-TRN-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `transfer_date` | Transfer Date | Date | None | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `new_company` | New Company | Link | Company |  |  |  | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `details_section` | Employee Transfer Details | Section Break | None |  |  |  | None | None |
| `transfer_details` | Employee Transfer Detail | Table | Employee Property History | ✅ |  |  | None | None |
| `reallocate_leaves` | Re-allocate Leaves | Check | None |  | ✅ |  | 0 | None |
| `create_new_employee_id` | Create New Employee Id | Check | None |  |  |  | 0 | None |
| `new_employee_id` | New Employee ID | Link | Employee |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Employee Transfer |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_transfer/employee_transfer.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

{% include 'hrms/hr/employee_property_update.js' %}

frappe.ui.form.on('Employee Transfer', {
	refresh: function(frm) {

	}
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Y-O-Y Transfers` | Y-O-Y Transfers | Count | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Transfers (This Month)` | Transfers (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
