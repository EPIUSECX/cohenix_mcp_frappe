# Master Control Plan: `Currency Exchange`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Specify Exchange Rate to convert one currency into another

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `date` | Date | Date | None | ✅ |  |  | None | None |
| `from_currency` | From Currency | Link | Currency | ✅ |  |  | None | None |
| `to_currency` | To Currency | Link | Currency | ✅ |  |  | None | None |
| `exchange_rate` | Exchange Rate | Float | None | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `for_buying` | For Buying | Check | None |  |  |  | 1 | None |
| `for_selling` | For Selling | Check | None |  |  |  | 1 | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/currency_exchange/currency_exchange.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Currency Exchange", {
	onload: function (frm) {
		if (frm.doc.__islocal) {
			frm.set_value("to_currency", frappe.defaults.get_global_default("currency"));
		}
	},

	refresh: function (frm) {
		// Don't trigger on Quick Entry form
		if (typeof frm.is_dialog === "undefined") {
			frm.trigger("set_exchange_rate_label");
		}
	},

	from_currency: function (frm) {
		frm.trigger("set_exchange_rate_label");
	},

	to_currency: function (frm) {
		frm.trigger("set_exchange_rate_label");
	},
	set_exchange_rate_label: function (frm) {
		if (frm.doc.from_currency && frm.doc.to_currency) {
			var default_label = __(frappe.meta.docfield_map[frm.doctype]["exchange_rate"].label);
			frm.fields_dict.exchange_rate.set_label(
				default_label + repl(" (1 %(from_currency)s = [?] %(to_currency)s)", frm.doc)
			);
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
