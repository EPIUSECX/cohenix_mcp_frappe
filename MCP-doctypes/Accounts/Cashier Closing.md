# Master Control Plan: `Cashier Closing`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | POS-CLO- |  |  | ✅ | POS-CLO- | None |
| `user` | User | Link | User | ✅ |  | ✅ | None | None |
| `date` | Date | Date | None |  |  | ✅ | Today | None |
| `from_time` | From Time | Time | None | ✅ |  |  | None | None |
| `time` | To Time | Time | None | ✅ |  |  | None | None |
| `expense` | Expense | Float | None |  |  |  | 0.00 | None |
| `custody` | Custody | Float | None |  |  |  | 0.00 | None |
| `returns` | Returns | Float | None |  |  |  | 0.00 | None |
| `outstanding_amount` | Outstanding Amount | Float | None |  |  | ✅ | 0.00 | None |
| `payments` | Payments | Table | Cashier Closing Payments |  |  |  | None | None |
| `net_amount` | Net Amount | Float | None |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Cashier Closing |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/cashier_closing/cashier_closing.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Cashier Closing", {
	setup: function (frm) {
		if (frm.doc.user == "" || frm.doc.user == null) {
			frm.doc.user = frappe.session.user;
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
