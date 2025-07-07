# Master Control Plan: `Access Log`

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
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `log_data_section` | Log Data | Section Break | None |  |  |  | None | None |
| `export_from` | Export From | Data | None |  |  | ✅ | None | None |
| `user` | User  | Link | User |  |  | ✅ | None | None |
| `show_document` | Show Document | Button | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `reference_document` | Reference Document | Data | None |  |  | ✅ | None | None |
| `timestamp` | Timestamp | Datetime | None |  |  | ✅ | Now | None |
| `private_file_section` | File Information | Section Break | None |  |  |  | None | None |
| `file_type` | File Type | Data | None |  |  | ✅ | None | None |
| `method` | Method | Data | None |  |  | ✅ | None | None |
| `report_information_section` | Report Information | Section Break | None |  |  |  | None | None |
| `report_name` | Report Name | Data | None |  |  | ✅ | None | None |
| `filters` | Filters | Code | None |  |  | ✅ | None | None |
| `show_report` | Show Report | Button | None |  |  |  | None | None |
| `raw_information_log_section` | RAW Information Log | Section Break | None |  |  |  | None | None |
| `page` | HTML Page | HTML Editor | None |  |  | ✅ | None | None |
| `columns` | Columns / Fields | HTML Editor | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/access_log/access_log.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Access Log", {
	show_document: function (frm) {
		frappe.set_route("Form", frm.doc.export_from, frm.doc.reference_document);
	},

	show_report: function (frm) {
		if (frm.doc.report_name.includes("/")) {
			frappe.set_route(frm.doc.report_name);
		} else {
			let filters = frm.doc.filters ? JSON.parse(frm.doc.filters) : {};
			frappe.set_route("query-report", frm.doc.report_name, filters);
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
