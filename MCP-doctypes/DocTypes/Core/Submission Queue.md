# Master Control Plan: `Submission Queue`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `status` | Status | Select | Queued
Finished
Failed |  | ✅ | ✅ | None | None |
| `created_at` | Created At | Datetime | None |  |  | ✅ | None | None |
| `enqueued_by` | Enqueued By | Data | None |  |  | ✅ | None | None |
| `job_id` | Job Id | Link | RQ Job |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `ended_at` | Ended At | Datetime | None |  |  | ✅ | None | None |
| `ref_doctype` | Reference DocType | Link | DocType |  |  | ✅ | None | None |
| `ref_docname` | Reference Docname | Dynamic Link | ref_doctype |  |  | ✅ | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `exception` | Exception | Long Text | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/submission_queue/submission_queue.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Submission Queue", {
	refresh: function (frm) {
		if (frm.doc.status === "Queued" && frappe.boot.user.roles.includes("System Manager")) {
			frm.add_custom_button(__("Unlock Reference Document"), () => {
				frappe.confirm(
					`
					Are you sure you want to go ahead with this action?
					Doing this could unlock other submissions of this document which are in queue (if present)
					and could lead to non-ideal conditions.`,
					() => {
						frm.call("unlock_doc");
					}
				);
			});
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
