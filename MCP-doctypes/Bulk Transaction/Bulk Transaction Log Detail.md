# Master Control Plan: `Bulk Transaction Log Detail`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Bulk Transaction`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `from_doctype` | From Doctype | Link | DocType |  |  | ✅ | None | None |
| `transaction_name` | Name | Dynamic Link | from_doctype |  |  | ✅ | None | None |
| `date` | Date  | Date | None |  |  | ✅ | None | None |
| `time` | Time | Time | None |  |  | ✅ | None | None |
| `transaction_status` | Status | Data | None |  |  | ✅ | None | None |
| `error_description` | Error Description | Long Text | None |  |  | ✅ | None | None |
| `to_doctype` | To Doctype | Link | DocType |  |  | ✅ | None | None |
| `retried` | Retried | Int | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/bulk_transaction/doctype/bulk_transaction_log_detail/bulk_transaction_log_detail.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Bulk Transaction Log Detail", {
// 	refresh(frm) {

// 	},
// });

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
