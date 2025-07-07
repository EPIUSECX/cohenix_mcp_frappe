# Master Control Plan: `Employee Promotion`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-EMP-PRO-.YYYY.-.#####`
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
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `salary_currency` | Salary Currency | Link | Currency |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `promotion_date` | Promotion Date | Date | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `details_section` | Employee Promotion Details | Section Break | None |  |  |  | None | Set the properties that should be updated in the Employee master on promotion submission |
| `promotion_details` | None | Table | Employee Property History |  |  |  | None | None |
| `salary_details_section` | Salary Details | Section Break | None |  |  |  | None | None |
| `current_ctc` | Current CTC | Currency | salary_currency |  |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `revised_ctc` | Revised CTC | Currency | salary_currency |  |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Promotion |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_promotion/employee_promotion.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

{% include 'hrms/hr/employee_property_update.js' %}

frappe.ui.form.on('Employee Promotion', {
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
| `Y-O-Y Promotions` | Y-O-Y Promotions | Count | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Promotions (This Month)` | Promotions (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
