# Master Control Plan: `Shipping Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:label`
- **Description:** Specify conditions to calculate shipping amount

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `label` | Shipping Rule Label | Data | None | ✅ |  |  | None | example: Next Day Shipping |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule_type` | Shipping Rule Type | Select | Selling
Buying |  |  |  | None | None |
| `section_break_10` | Accounting | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `account` | Shipping Account | Link | Account | ✅ |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center | ✅ |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `shipping_amount_section` | None | Section Break | None |  |  |  | None | None |
| `calculate_based_on` | Calculate Based On | Select | Fixed
Net Total
Net Weight |  |  |  | Fixed | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `shipping_amount` | Shipping Amount | Currency | None |  |  |  | None | None |
| `rule_conditions_section` | Shipping Rule Conditions | Section Break | None |  |  |  | None | None |
| `conditions` | Shipping Rule Conditions | Table | Shipping Rule Condition |  |  |  | None | None |
| `section_break_6` | Restrict to Countries | Section Break | None |  |  |  | None | None |
| `countries` | Valid for Countries | Table | Shipping Rule Country |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/shipping_rule/shipping_rule.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Shipping Rule", {
	onload: function (frm) {
		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	refresh: function (frm) {
		frm.set_query("account", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});

		frm.trigger("toggle_reqd");
	},
	calculate_based_on: function (frm) {
		frm.trigger("toggle_reqd");
	},
	toggle_reqd: function (frm) {
		frm.toggle_reqd("shipping_amount", frm.doc.calculate_based_on === "Fixed");
		frm.toggle_reqd("conditions", frm.doc.calculate_based_on !== "Fixed");
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
