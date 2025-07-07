# Master Control Plan: `Cost Center Allocation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `CC-ALLOC-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `main_cost_center` | Main Cost Center | Link | Cost Center | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None | ✅ |  |  | Today | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `allocation_percentages` | Cost Center Allocation Percentages | Table | Cost Center Allocation Percentage | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Cost Center Allocation |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/cost_center_allocation/cost_center_allocation.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Cost Center Allocation", {
	setup: function (frm) {
		frm.set_query("main_cost_center", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("cost_center", "allocation_percentages", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
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
