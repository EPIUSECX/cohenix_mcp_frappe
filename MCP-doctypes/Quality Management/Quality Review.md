# Master Control Plan: `Quality Review`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Quality Management`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:QA-REV-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `goal` | Goal | Link | Quality Goal | ✅ |  |  | None | None |
| `date` | Date | Date | None |  |  | ✅ | Today | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `procedure` | Procedure | Link | Quality Procedure |  |  | ✅ | None | None |
| `status` | Status | Select | Open
Passed
Failed |  |  | ✅ | Open | None |
| `sb_00` | Review | Section Break | None |  |  |  | None | None |
| `reviews` | Reviews | Table | Quality Review Objective |  |  |  | None | None |
| `sb_01` | Notes | Section Break | None |  |  |  | None | None |
| `additional_information` | Additional Information | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/quality_management/doctype/quality_review/quality_review.js`
```javascript
// Copyright (c) 2018, Frappe and contributors
// For license information, please see license.txt

frappe.ui.form.on("Quality Review", {
	goal: function (frm) {
		frappe.call({
			method: "frappe.client.get",
			args: {
				doctype: "Quality Goal",
				name: frm.doc.goal,
			},
			callback: function (data) {
				frm.fields_dict.reviews.grid.remove_all();
				let objectives = data.message.objectives;
				for (var i in objectives) {
					frm.add_child("reviews");
					frm.fields_dict.reviews.get_value()[i].objective = objectives[i].objective;
					frm.fields_dict.reviews.get_value()[i].target = objectives[i].target;
					frm.fields_dict.reviews.get_value()[i].uom = objectives[i].uom;
				}
				frm.refresh();
			},
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
