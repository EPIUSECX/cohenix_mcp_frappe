# Master Control Plan: `Customer Group`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:customer_group_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Master Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Customer | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_group_name` | Customer Group Name | Data | None | ✅ |  |  | None | None |
| `parent_customer_group` | Parent Customer Group | Link | Customer Group |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | Only leaf nodes are allowed in transaction |
| `cb0` | None | Column Break | None |  |  |  | None | None |
| `default_price_list` | Default Price List | Link | Price List |  |  |  | None | None |
| `payment_terms` | Default Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `lft` | lft | Int | None |  | ✅ |  | None | None |
| `rgt` | rgt | Int | None |  | ✅ |  | None | None |
| `old_parent` | old_parent | Link | Customer Group |  | ✅ |  | None | None |
| `default_receivable_account` | Default Accounts | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Party Account |  |  |  | None | Mention if non-standard receivable account applicable |
| `credit_limit_section` | Credit Limits | Section Break | None |  |  |  | None | None |
| `credit_limits` | Credit Limit | Table | Customer Credit Limit |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/customer_group/customer_group.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Customer Group", {
	setup: function (frm) {
		frm.set_query("parent_customer_group", function (doc) {
			return {
				filters: {
					is_group: 1,
					name: ["!=", cur_frm.doc.customer_group_name],
				},
			};
		});

		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			return {
				filters: {
					root_type: "Asset",
					account_type: "Receivable",
					company: locals[cdt][cdn].company,
					is_group: 0,
				},
			};
		});

		frm.set_query("advance_account", "accounts", function (doc, cdt, cdn) {
			return {
				filters: {
					root_type: "Liability",
					account_type: "Receivable",
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
		// read-only for root customer group
		if (!frm.doc.parent_customer_group && !frm.doc.__islocal) {
			frm.set_read_only();
			frm.set_intro(__("This is a root customer group and cannot be edited."));
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
