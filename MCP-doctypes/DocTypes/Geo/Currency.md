# Master Control Plan: `Currency`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Geo`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:currency_name`
- **Description:** Currency list stores the currency value, its symbol and fraction unit

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `currency_name` | Currency Name | Data | None | ✅ |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 0 | None |
| `fraction` | Fraction | Data | None |  |  |  | None | Sub-currency. For e.g. "Cent" |
| `fraction_units` | Fraction Units | Int | None |  |  |  | None | 1 Currency = [?] Fraction
For e.g. 1 USD = 100 Cent |
| `smallest_currency_fraction_value` | Smallest Currency Fraction Value | Currency | None |  |  |  | None | Smallest circulating fraction unit (coin). For e.g. 1 cent for USD and it should be entered as 0.01 |
| `symbol` | Symbol | Data | None |  |  |  | None | A symbol for this currency. For e.g. $ |
| `symbol_on_right` | Show Currency Symbol on Right Side | Check | None |  |  |  | 0 | None |
| `number_format` | Number Format | Select | 
#,###.##
#.###,##
# ###.##
# ###,##
#'###.##
#, ###.##
#,##,###.##
#,###.###
#.###
#,### |  |  |  | None | How should this currency be formatted? If not set, will use system defaults |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/geo/doctype/currency/currency.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: See license.txt

frappe.ui.form.on("Currency", {
	refresh(frm) {
		frm.set_intro("");
		if (!frm.doc.enabled) {
			frm.set_intro(__("This Currency is disabled. Enable to use in transactions"));
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
