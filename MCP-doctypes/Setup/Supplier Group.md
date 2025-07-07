# Master Control Plan: `Supplier Group`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:supplier_group_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Purchase Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier_group_name` | Supplier Group Name | Data | None | ✅ |  |  | None | None |
| `parent_supplier_group` | Parent Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `section_credit_limit` | Credit Limit | Section Break | None |  |  |  | None | None |
| `payment_terms` | Default Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `default_payable_account` | Default Payable Account | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Party Account |  |  |  | None | Mention if non-standard receivable account applicable |
| `lft` | lft | Int | None |  | ✅ |  | None | None |
| `rgt` | rgt | Int | None |  | ✅ |  | None | None |
| `old_parent` | Old Parent | Link | Supplier Group |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/supplier_group/supplier_group.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Supplier Group", {
	setup: function (frm) {
		frm.set_query("parent_supplier_group", function (doc) {
			return {
				filters: {
					is_group: 1,
					name: ["!=", cur_frm.doc.supplier_group_name],
				},
			};
		});

		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			return {
				filters: {
					root_type: "Liability",
					account_type: "Payable",
					company: locals[cdt][cdn].company,
					is_group: 0,
				},
			};
		});

		frm.set_query("advance_account", "accounts", function (doc, cdt, cdn) {
			return {
				filters: {
					root_type: "Asset",
					account_type: "Payable",
					company: locals[cdt][cdn].company,
					is_group: 0,
				},
			};
		});
	},
	refresh: function (frm) {
		frm.trigger("set_root_readonly");
	},
	set_root_readonly: function (frm) {
		if (!frm.doc.parent_supplier_group && !frm.is_new()) {
			frm.set_read_only();
			frm.set_intro(__("This is a root supplier group and cannot be edited."));
		} else {
			frm.set_intro(null);
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
