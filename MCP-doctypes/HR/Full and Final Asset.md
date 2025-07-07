# Master Control Plan: `Full and Final Asset`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `reference` | Reference | Link | Asset Movement | ✅ |  | ✅ | None | None |
| `asset_name` | Asset Name | Data | None |  |  | ✅ | None | None |
| `date` | Date | Datetime | None |  |  | ✅ | None | None |
| `actual_cost` | Actual Cost | Currency | None |  |  | ✅ | None | None |
| `cost` | Cost | Currency | None |  |  |  | None | None |
| `column_break_xezj` | None | Column Break | None |  |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `action` | Action | Select | Return
Recover Cost | ✅ |  |  | Return | None |
| `status` | Status | Select | Owned
Returned | ✅ |  |  | None | None |
| `section_break_hudu` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/full_and_final_asset/full_and_final_asset.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Full and Final Asset", {
	// refresh: function(frm) {
	// }
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
