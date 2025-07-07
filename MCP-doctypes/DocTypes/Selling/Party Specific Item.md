# Master Control Plan: `Party Specific Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
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
| `party_type` | Party Type | Select | Customer
Supplier | ✅ |  |  | None | None |
| `party` | Party Name | Dynamic Link | party_type | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `restrict_based_on` | Restrict Items Based On | Select | Item
Item Group
Brand | ✅ |  |  | None | None |
| `based_on_value` | Based On Value | Dynamic Link | restrict_based_on | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 2
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/party_specific_item/party_specific_item.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Party Specific Item", {
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
