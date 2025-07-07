# Master Control Plan: `Global Defaults`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `default_company` | Default Company | Link | Company |  |  |  | None | None |
| `country` | Country | Link | Country |  |  |  | None | None |
| `default_distance_unit` | Default Distance Unit | Link | UOM |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `default_currency` | Default Currency | Link | Currency | ✅ |  |  | INR | None |
| `hide_currency_symbol` | Hide Currency Symbol | Select | 
No
Yes |  |  |  | None | Do not show any symbol like $ etc next to currencies. |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | If disable, 'Rounded Total' field will not be visible in any transaction |
| `disable_in_words` | Disable In Words | Check | None |  |  |  | 0 | If disable, 'In Words' field will not be visible in any transaction |
| `demo_company` | Demo Company | Link | Company |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/global_defaults/global_defaults.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Global Defaults", {
	onload: function (frm) {
		frm.trigger("get_distance_uoms");
	},
	validate: function (frm) {
		frm.call("get_defaults", null, (r) => {
			frappe.sys_defaults = r.message;
		});
	},
	get_distance_uoms: function (frm) {
		let units = [];

		frappe.call({
			method: "frappe.client.get_list",
			args: {
				doctype: "UOM Conversion Factor",
				filters: { category: __("Length") },
				fields: ["to_uom"],
				limit_page_length: 500,
			},
			callback: function (r) {
				r.message.forEach((row) => units.push(row.to_uom));
			},
		});
		frm.set_query("default_distance_unit", function () {
			return { filters: { name: ["IN", units] } };
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
