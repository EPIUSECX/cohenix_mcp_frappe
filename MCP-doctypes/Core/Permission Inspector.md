# Master Control Plan: `Permission Inspector`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `ref_doctype` | DocType | Link | DocType | ✅ |  |  | None | None |
| `column_break_mcqo` | None | Column Break | None |  |  |  | None | None |
| `docname` | Document | Dynamic Link | ref_doctype |  |  |  | None | None |
| `column_break_xbrd` | None | Column Break | None |  |  |  | None | None |
| `user` | User | Link | User | ✅ |  |  | None | None |
| `column_break_nvaa` | None | Column Break | None |  |  |  | None | None |
| `permission_type` | Permission Type | Select | read
write
create
delete
submit
cancel
select
amend
print
email
report
import
export
share |  |  |  | None | None |
| `section_break_hkjp` | None | Section Break | None |  |  |  | None | None |
| `output` | Output | Code | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/permission_inspector/permission_inspector.js`
```javascript
// Copyright (c) 2024, Frappe Technologies and contributors
// For license information, please see license.txt

const call_debug = (frm) => {
	frm.trigger("debug");
};

frappe.ui.form.on("Permission Inspector", {
	refresh(frm) {
		frm.disable_save();
	},
	docname: call_debug,
	ref_doctype(frm) {
		frm.doc.docname = ""; // Usually doctype change invalidates docname
		call_debug(frm);
	},
	user: call_debug,
	permission_type: call_debug,
	debug(frm) {
		if (frm.doc.ref_doctype && frm.doc.user) {
			frm.call("debug");
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
