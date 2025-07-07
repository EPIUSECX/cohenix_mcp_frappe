# Master Control Plan: `Unreconcile Payment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company |  |  |  | None | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  |  | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  |  | None | None |
| `get_allocations` | Get Allocations | Button | None |  |  |  | None | None |
| `allocations` | Allocations | Table | Unreconcile Payment Entries |  |  |  | None | None |
| `amended_from` | Amended From | Link | Unreconcile Payment |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/unreconcile_payment/unreconcile_payment.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Unreconcile Payment", {
	refresh(frm) {
		frm.set_query("voucher_type", function () {
			return {
				filters: {
					name: ["in", ["Payment Entry", "Journal Entry"]],
				},
			};
		});

		frm.set_query("voucher_no", function (doc) {
			return {
				filters: {
					company: doc.company,
					docstatus: 1,
				},
			};
		});
	},
	get_allocations: function (frm) {
		frm.clear_table("allocations");
		frappe.call({
			method: "get_allocations_from_payment",
			doc: frm.doc,
			callback: function (r) {
				if (r.message) {
					r.message.forEach((x) => {
						frm.add_child("allocations", x);
					});
					frm.refresh_fields();
				}
			},
		});
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
