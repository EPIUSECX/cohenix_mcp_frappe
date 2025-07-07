# Master Control Plan: `Territory`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:territory_name`
- **Description:** Classification of Customers by region

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Maintenance User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Customer | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `territory_name` | Territory Name | Data | None | ✅ |  |  | None | None |
| `parent_territory` | Parent Territory | Link | Territory |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `cb0` | None | Column Break | None |  |  |  | None | None |
| `territory_manager` | Territory Manager | Link | Sales Person |  |  |  | None | For reference |
| `lft` | lft | Int | None |  | ✅ |  | None | None |
| `rgt` | rgt | Int | None |  | ✅ |  | None | None |
| `old_parent` | old_parent | Link | Territory |  | ✅ |  | None | None |
| `target_details_section_break` | Territory Targets | Section Break | None |  |  |  | None | Set Item Group-wise budgets on this Territory. You can also include seasonality by setting the Distribution. |
| `targets` | Targets | Table | Target Detail |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/territory/territory.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Territory", {
	setup: function (frm) {
		frm.fields_dict["targets"].grid.get_field("distribution_id").get_query = function (doc, cdt, cdn) {
			var row = locals[cdt][cdn];
			return {
				filters: {
					fiscal_year: row.fiscal_year,
				},
			};
		};
	},
	refresh: function (frm) {
		frm.trigger("set_root_readonly");
	},
	set_root_readonly: function (frm) {
		// read-only for root territory
		if (!frm.doc.parent_territory && !frm.doc.__islocal) {
			frm.set_read_only();
			frm.set_intro(__("This is a root territory and cannot be edited."));
		} else {
			frm.set_intro(null);
		}
	},
});

//get query select territory
cur_frm.fields_dict["parent_territory"].get_query = function (doc, cdt, cdn) {
	return {
		filters: [
			["Territory", "is_group", "=", 1],
			["Territory", "name", "!=", doc.territory_name],
		],
	};
};

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
