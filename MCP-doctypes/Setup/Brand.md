# Master Control Plan: `Brand`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:brand`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Item Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `brand` | Brand Name | Data | None | ✅ |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `description` | Description | Text | None |  |  |  | None | None |
| `defaults` | Defaults | Section Break | None |  |  |  | None | None |
| `brand_defaults` | Brand Defaults | Table | Item Default |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/brand/brand.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Brand", {
	setup: (frm) => {
		frm.set_query("default_warehouse", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: { company: row.company },
			};
		});

		frm.set_query("default_discount_account", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					report_type: "Profit and Loss",
					company: row.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("buying_cost_center", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					is_group: 0,
					company: row.company,
				},
			};
		});

		frm.set_query("expense_account", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: row.company },
			};
		});

		frm.set_query("default_provisional_account", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					company: row.company,
					root_type: ["in", ["Liability", "Asset"]],
					is_group: 0,
				},
			};
		});

		frm.set_query("selling_cost_center", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					is_group: 0,
					company: row.company,
				},
			};
		});

		frm.set_query("income_account", "brand_defaults", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				query: "erpnext.controllers.queries.get_income_account",
				filters: { company: row.company },
			};
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
