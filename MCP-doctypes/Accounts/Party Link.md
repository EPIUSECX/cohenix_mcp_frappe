# Master Control Plan: `Party Link`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `ACC-PT-LNK-.###.`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `primary_role` | Primary Role | Link | DocType | ✅ |  |  | None | None |
| `secondary_role` | Secondary Role | Link | DocType |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `primary_party` | Primary Party | Dynamic Link | primary_role |  |  |  | None | None |
| `secondary_party` | Secondary Party | Dynamic Link | secondary_role |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 2
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/party_link/party_link.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Party Link", {
	refresh: function (frm) {
		frm.set_query("primary_role", () => {
			return {
				filters: {
					name: ["in", ["Customer", "Supplier"]],
				},
			};
		});

		frm.set_query("secondary_role", () => {
			let party_types = Object.keys(frappe.boot.party_account_types).filter(
				(p) => p != frm.doc.primary_role
			);
			return {
				filters: {
					name: ["in", party_types],
				},
			};
		});
	},

	primary_role(frm) {
		frm.set_value("primary_party", "");
		frm.set_value("secondary_role", "");
	},

	secondary_role(frm) {
		frm.set_value("secondary_party", "");
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
