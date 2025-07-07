# Master Control Plan: `Employee Grievance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-GRIEV-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject` | Subject | Data | None | ✅ |  |  | None | None |
| `raised_by` | Raised By | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `date` | Date  | Date | None | ✅ |  |  | None | None |
| `status` | Status | Select | Open
Investigated
Resolved
Invalid | ✅ |  |  | Open | None |
| `reports_to` | Reports To | Link | Employee |  |  | ✅ | None | None |
| `grievance_details_section` | Grievance Details | Section Break | None |  |  |  | None | None |
| `grievance_against_party` | Grievance Against Party | Link | DocType | ✅ |  |  | None | None |
| `grievance_against` | Grievance Against | Dynamic Link | grievance_against_party | ✅ |  |  | None | None |
| `grievance_type` | Grievance Type | Link | Grievance Type | ✅ |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `associated_document_type` | Associated Document Type | Link | DocType |  |  |  | None | None |
| `associated_document` | Associated Document | Dynamic Link | associated_document_type |  |  |  | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text | None | ✅ |  |  | None | None |
| `investigation_details_section` | Investigation Details | Section Break | None |  |  |  | None | None |
| `cause_of_grievance` | Cause of Grievance | Text | None |  |  |  | None | None |
| `resolution_details_section` | Resolution Details | Section Break | None |  |  |  | None | None |
| `resolved_by` | Resolved By | Link | User |  |  |  | None | None |
| `resolution_date` | Resolution Date | Date | None |  |  |  | None | None |
| `employee_responsible` | Employee Responsible  | Link | Employee |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `resolution_detail` | Resolution Details | Small Text | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Grievance |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
- **Dynamic Link Fields:** 2
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_grievance/employee_grievance.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Grievance", {
	setup: function (frm) {
		frm.set_query("grievance_against_party", function () {
			return {
				filters: {
					name: [
						"in",
						["Company", "Department", "Employee Group", "Employee Grade", "Employee"],
					],
				},
			};
		});
		frm.set_query("associated_document_type", function () {
			let ignore_modules = [
				"Setup",
				"Core",
				"Integrations",
				"Automation",
				"Website",
				"Utilities",
				"Event Streaming",
				"Social",
				"Chat",
				"Data Migration",
				"Printing",
				"Desk",
				"Custom",
			];
			return {
				filters: {
					istable: 0,
					issingle: 0,
					module: ["Not In", ignore_modules],
				},
			};
		});
	},

	grievance_against_party: function (frm) {
		let filters = {};
		if (frm.doc.grievance_against_party == "Employee" && frm.doc.raised_by) {
			filters.name = ["!=", frm.doc.raised_by];
		}
		frm.set_query("grievance_against", function () {
			return {
				filters: filters,
			};
		});
	},
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
| `Grievance Type` | Grievance Type | Group By | HR |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
