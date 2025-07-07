# Master Control Plan: `ToDo`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| All | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `description_and_status` | None | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Open
Closed
Cancelled |  |  |  | Open | None |
| `priority` | Priority | Select | High
Medium
Low |  |  |  | Medium | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |
| `date` | Due Date | Date | None |  |  |  | Today | None |
| `allocated_to` | Allocated To | Link | User |  |  |  | None | None |
| `description_section` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None | ✅ |  |  | None | None |
| `section_break_6` | Reference | Section Break | None |  |  |  | None | None |
| `reference_type` | Reference Type | Link | DocType |  |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_type |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `role` | Role | Link | Role |  |  |  | None | None |
| `assigned_by` | Assigned By | Link | User |  |  |  | None | None |
| `assigned_by_full_name` | Assigned By Full Name | Read Only | None |  |  |  | None | None |
| `sender` | Sender | Data | Email |  | ✅ |  | None | None |
| `assignment_rule` | Assignment Rule | Link | Assignment Rule |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/todo/todo.js`
```javascript
// bind events

frappe.ui.form.on("ToDo", {
	onload: function (frm) {
		frm.set_query("reference_type", function (txt) {
			return {
				filters: {
					issingle: 0,
				},
			};
		});
	},
	refresh: function (frm) {
		if (frm.doc.reference_type && frm.doc.reference_name) {
			frm.add_custom_button(__(frm.doc.reference_name), function () {
				frappe.set_route("Form", frm.doc.reference_type, frm.doc.reference_name);
			});
		}

		if (!frm.doc.__islocal) {
			if (frm.doc.status !== "Closed") {
				frm.add_custom_button(
					__("Close"),
					function () {
						frm.set_value("status", "Closed");
						frm.save(null, function () {
							// back to list
							frappe.set_route("List", "ToDo");
						});
					},
					"fa fa-check",
					"btn-success"
				);
			} else {
				frm.add_custom_button(
					__("Reopen"),
					function () {
						frm.set_value("status", "Open");
						frm.save();
					},
					null,
					"btn-default"
				);
			}
			frm.add_custom_button(
				__("New"),
				function () {
					frappe.new_doc("ToDo");
				},
				null,
				"btn-default"
			);
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `ToDo` | Script Report | Desk |



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
