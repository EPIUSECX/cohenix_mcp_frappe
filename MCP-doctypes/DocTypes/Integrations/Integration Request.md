# Master Control Plan: `Integration Request`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `request_id` | Request ID | Data | None |  |  | ✅ | None | None |
| `integration_request_service` | Service | Data | None |  |  | ✅ | None | None |
| `is_remote_request` | Is Remote Request? | Check | None |  |  | ✅ | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `request_description` | Request Description | Data | None |  |  | ✅ | None | None |
| `status` | Status | Select | 
Queued
Authorized
Completed
Cancelled
Failed |  |  | ✅ | Queued | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `url` | URL | Small Text | None |  |  | ✅ | None | None |
| `request_headers` | Request Headers | Code | None |  |  | ✅ | None | None |
| `data` | Request Data | Code | None |  |  | ✅ | None | None |
| `response_section` | Response | Section Break | None |  |  |  | None | None |
| `output` | Output | Code | None |  |  | ✅ | None | None |
| `error` | Error | Code | None |  |  | ✅ | None | None |
| `reference_section` | Reference | Section Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  | ✅ | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `reference_docname` | Reference Document Name | Dynamic Link | reference_doctype |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/integration_request/integration_request.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Integration Request", {
	refresh: function (frm) {},
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
