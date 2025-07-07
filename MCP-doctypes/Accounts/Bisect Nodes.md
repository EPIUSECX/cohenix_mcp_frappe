# Master Control Plan: `Bisect Nodes`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `autoincrement`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `root` | Root | Link | Bisect Nodes |  |  |  | None | None |
| `left_child` | Left Child | Link | Bisect Nodes |  |  |  | None | None |
| `right_child` | Right Child | Link | Bisect Nodes |  |  |  | None | None |
| `period_from_date` | Period_from_date | Datetime | None |  |  |  | None | None |
| `period_to_date` | Period To Date | Datetime | None |  |  |  | None | None |
| `difference` | Difference | Float | None |  |  |  | None | None |
| `balance_sheet_summary` | Balance Sheet Summary | Float | None |  |  |  | None | None |
| `profit_loss_summary` | Profit and Loss Summary | Float | None |  |  |  | None | None |
| `generated` | Generated | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bisect_nodes/bisect_nodes.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Bisect Nodes", {
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
