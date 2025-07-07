# Master Control Plan: `Item Group`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:item_group_name`
- **Description:** An Item Group is a way to classify items based on types.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Item Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Desk User | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `gs` | General Settings | Section Break | None |  |  |  | None | None |
| `item_group_name` | Item Group Name | Data | None | ✅ |  |  | None | None |
| `parent_item_group` | Parent Item Group | Link | Item Group |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | Only leaf nodes are allowed in transaction |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `defaults` | Defaults | Section Break | None |  |  |  | None | None |
| `item_group_defaults` | Item Group Defaults | Table | Item Default |  |  |  | None | None |
| `sec_break_taxes` | Item Tax | Section Break | None |  |  |  | None | None |
| `taxes` | Taxes | Table | Item Tax |  |  |  | None | None |
| `lft` | lft | Int | None |  | ✅ |  | None | None |
| `old_parent` | old_parent | Link | Item Group |  | ✅ |  | None | None |
| `rgt` | rgt | Int | None |  | ✅ |  | None | None |
| `custom_website_settings` | Website Settings | Section Break | None |  |  |  | None | None |
| `show_in_website` | Show in Website | Check | None |  |  |  | 0 | Make Item Group visible in website |
| `route` | Route | Data | None |  |  |  | None | None |
| `website_title` | Title | Data | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | HTML / Banner that will show on the top of product list. |
| `website_specifications` | Website Specifications | Table | Item Website Specification |  |  |  | None | None |
| `website_filters_section` | Website Filters | Section Break | None |  |  |  | None | None |
| `filter_fields` | Item Fields | Table | Website Filter Field |  |  |  | None | None |
| `filter_attributes` | Attributes | Table | Website Attribute |  |  |  | None | None |
| `include_descendants` | Include Descendants | Check | None |  |  |  | 0 | Include Website Items belonging to child Item Groups |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `weightage` | Weightage | Int | None |  |  |  | None | None |
| `slideshow` | Slideshow | Link | Website Slideshow |  |  |  | None | Show this slideshow at the top of the page |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `filter_attributes` | Attributes | Table | Website Attribute |  |  |  | None | None |
| `filter_fields` | Item Fields | Table | Website Filter Field |  |  |  | None | None |
| `website_filters_section` | Website Filters | Section Break | None |  |  |  | None | None |
| `website_specifications` | Website Specifications | Table | Item Website Specification |  |  |  | None | None |
| `slideshow` | Slideshow | Link | Website Slideshow |  |  |  | None | Show this slideshow at the top of the page |
| `weightage` | Weightage | Int | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `include_descendants` | Include Descendants | Check | None |  |  |  | 0 | Include Website Items belonging to child Item Groups |
| `description` | Description | Text Editor | None |  |  |  | None | HTML / Banner that will show on the top of product list. |
| `website_title` | Title | Data | None |  |  |  | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `show_in_website` | Show in Website | Check | None |  |  |  | 0 | Make Item Group visible in website |
| `custom_website_settings` | Website Settings | Section Break | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 8

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/item_group/item_group.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Item Group", {
	onload: function (frm) {
		frm.list_route = "Tree/Item Group";

		//get query select item group
		frm.fields_dict["parent_item_group"].get_query = function (doc, cdt, cdn) {
			return {
				filters: [
					["Item Group", "is_group", "=", 1],
					["Item Group", "name", "!=", doc.item_group_name],
				],
			};
		};
		frm.fields_dict["item_group_defaults"].grid.get_field("default_discount_account").get_query =
			function (doc, cdt, cdn) {
				const row = locals[cdt][cdn];
				return {
					filters: {
						report_type: "Profit and Loss",
						company: row.company,
						is_group: 0,
					},
				};
			};
		frm.fields_dict["item_group_defaults"].grid.get_field("expense_account").get_query = function (
			doc,
			cdt,
			cdn
		) {
			const row = locals[cdt][cdn];
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: row.company },
			};
		};
		frm.fields_dict["item_group_defaults"].grid.get_field("income_account").get_query = function (
			doc,
			cdt,
			cdn
		) {
			const row = locals[cdt][cdn];
			return {
				query: "erpnext.controllers.queries.get_income_account",
				filters: { company: row.company },
			};
		};

		frm.fields_dict["item_group_defaults"].grid.get_field("buying_cost_center").get_query = function (
			doc,
			cdt,
			cdn
		) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					is_group: 0,
					company: row.company,
				},
			};
		};

		frm.fields_dict["item_group_defaults"].grid.get_field("selling_cost_center").get_query = function (
			doc,
			cdt,
			cdn
		) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					is_group: 0,
					company: row.company,
				},
			};
		};
	},

	refresh: function (frm) {
		frm.trigger("set_root_readonly");
		frm.add_custom_button(__("Item Group Tree"), function () {
			frappe.set_route("Tree", "Item Group");
		});

		if (!frm.is_new()) {
			frm.add_custom_button(__("Items"), function () {
				frappe.set_route("List", "Item", { item_group: frm.doc.name });
			});
		}
	},

	set_root_readonly: function (frm) {
		// read-only for root item group
		frm.set_intro("");
		if (!frm.doc.parent_item_group && !frm.doc.__islocal) {
			frm.set_read_only();
			frm.set_intro(__("This is a root item group and cannot be edited."), true);
		}
	},

	page_name: frappe.utils.warn_page_name_change,
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
