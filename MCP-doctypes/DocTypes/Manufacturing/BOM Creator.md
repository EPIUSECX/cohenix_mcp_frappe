# Master Control Plan: `BOM Creator`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `tab_2_tab` | BOM Tree | Tab Break | None |  |  |  | None | None |
| `bom_creator` | None | HTML | None |  |  |  | None | None |
| `details_tab` | Final Product | Tab Break | None |  |  |  | None | None |
| `section_break_ylsl` | None | Section Break | None |  |  |  | None | None |
| `item_code` | Finished Good | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `column_break_ikj7` | None | Column Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  |  | None | None |
| `section_break_xvld` | Operations Routing | Section Break | None |  |  |  | None | None |
| `routing` | Routing | Link | Routing |  |  |  | None | None |
| `raw_materials_tab` | Sub Assemblies & Raw Materials | Tab Break | None |  |  |  | None | None |
| `currency_detail` | Costing | Section Break | None |  |  |  | None | None |
| `rm_cost_as_per` | Rate Of Materials Based On | Select | Valuation Rate
Last Purchase Rate
Price List | ✅ |  |  | Valuation Rate | None |
| `set_rate_based_on_warehouse` | Set Valuation Rate Based on Source Warehouse | Check | None |  |  |  | 0 | None |
| `buying_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency |  |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None |  |  |  | None | None |
| `column_break_ivyw` | None | Column Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Conversion Rate | Float | None |  |  |  | 1 | None |
| `section_break_zcfg` | Warehouse | Section Break | None |  |  |  | None | None |
| `default_warehouse` | Default Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `column_break_tzot` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `materials_section` | None | Section Break | None |  |  |  | None | None |
| `items` | Items | Table | BOM Creator Item |  |  |  | None | None |
| `costing_detail` | Costing Details | Section Break | None |  |  |  | None | None |
| `raw_material_cost` | Total Cost | Currency | currency |  |  | ✅ | None | None |
| `remarks_tab` | Remarks | Tab Break | None |  |  |  | None | None |
| `remarks` | Remarks | Text Editor | None |  |  |  | None | None |
| `section_break_yixm` | None | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Submitted
In Progress
Completed
Failed
Cancelled |  |  | ✅ | Draft | None |
| `column_break_irab` | None | Column Break | None |  |  |  | None | None |
| `error_log` | Error Log | Text | None |  |  | ✅ | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | BOM Creator |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 11
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_creator/bom_creator.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.provide("erpnext.bom");

frappe.ui.form.on("BOM Creator", {
	setup(frm) {
		frm.trigger("set_queries");
	},

	setup_bom_creator(frm) {
		frm.dashboard.clear_comment();

		if (!frm.is_new()) {
			if (!frappe.bom_configurator || frappe.bom_configurator.bom_configurator !== frm.doc.name) {
				frm.trigger("build_tree");
			}
		} else if (!frm.doc.items?.length) {
			let $parent = $(frm.fields_dict["bom_creator"].wrapper);
			$parent.empty();
			frm.trigger("make_new_entry");
		}
	},

	build_tree(frm) {
		let $parent = $(frm.fields_dict["bom_creator"].wrapper);
		$parent.empty();
		frm.toggle_enable("item_code", false);

		frappe.require("bom_configurator.bundle.js").then(() => {
			frappe.bom_configurator = new frappe.ui.BOMConfigurator({
				wrapper: $parent,
				page: $parent,
				frm: frm,
				bom_configurator: frm.doc.name,
			});
		});
	},

	make_new_entry(frm) {
		let dialog = new frappe.ui.Dialog({
			title: __("Multi-level BOM Creator"),
			fields: [
				{
					label: __("Name"),
					fieldtype: "Data",
					fieldname: "name",
					reqd: 1,
				},
				{ fieldtype: "Column Break" },
				{
					label: __("Company"),
					fieldtype: "Link",
					fieldname: "company",
					options: "Company",
					reqd: 1,
					default: frappe.defaults.get_user_default("Company"),
				},
				{ fieldtype: "Section Break" },
				{
					label: __("Item Code (Final Product)"),
					fieldtype: "Link",
					fieldname: "item_code",
					options: "Item",
					reqd: 1,
				},
				{ fieldtype: "Column Break" },
				{
					label: __("Quantity"),
					fieldtype: "Float",
					fieldname: "qty",
					reqd: 1,
					default: 1.0,
				},
				{ fieldtype: "Section Break" },
				{
					label: __("Currency"),
					fieldtype: "Link",
					fieldname: "currency",
					options: "Currency",
					reqd: 1,
					default: frappe.defaults.get_global_default("currency"),
				},
				{ fieldtype: "Column Break" },
				{
					label: __("Conversion Rate"),
					fieldtype: "Float",
					fieldname: "conversion_rate",
					reqd: 1,
					default: 1.0,
				},
				{ fieldtype: "Section Break" },
				{
					label: __("Routing"),
					fieldtype: "Link",
					fieldname: "routing",
					options: "Routing",
				},
			],
			primary_action_label: __("Create"),
			primary_action: (values) => {
				values.doctype = frm.doc.doctype;
				frappe.db.insert(values).then((doc) => {
					frappe.set_route("Form", doc.doctype, doc.name);
				});
			},
		});

		dialog.fields_dict.item_code.get_query = "erpnext.controllers.queries.item_query";
		dialog.show();
	},

	set_queries(frm) {
		frm.set_query("bom_no", "items", function (doc, cdt, cdn) {
			let item = frappe.get_doc(cdt, cdn);
			return {
				filters: {
					item: item.item_code,
				},
			};
		});
		frm.set_query("item_code", "items", function () {
			return {
				query: "erpnext.controllers.queries.item_query",
			};
		});
		frm.set_query("fg_item", "items", function () {
			return {
				query: "erpnext.controllers.queries.item_query",
			};
		});

		frm.set_query("workstation", (doc) => {
			if (doc.workstation_type) {
				return {
					filters: {
						workstation_type: doc.workstation_type,
					},
				};
			}
		});
	},

	refresh(frm) {
		frm.trigger("setup_bom_creator");
		frm.trigger("set_root_item");
		frm.trigger("add_custom_buttons");
	},

	set_root_item(frm) {
		if (frm.is_new() && frm.doc.items?.length) {
			frappe.model.set_value(frm.doc.items[0].doctype, frm.doc.items[0].name, "is_root", 1);
		}
	},

	add_custom_buttons(frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(__("Rebuild Tree"), () => {
				frm.trigger("build_tree");
			});
		}

		if (frm.doc.docstatus === 1 && frm.doc.status !== "Completed") {
			frm.add_custom_button(__("Create Multi-level BOM"), () => {
				frm.trigger("create_multi_level_bom");
			});
		}
	},

	create_multi_level_bom(frm) {
		frm.call({
			method: "enqueue_create_boms",
			doc: frm.doc,
		});
	},
});

frappe.ui.form.on("BOM Creator Item", {
	item_code(frm, cdt, cdn) {
		let item = frappe.get_doc(cdt, cdn);
		if (item.item_code && item.is_root) {
			frappe.model.set_value(cdt, cdn, "fg_item", item.item_code);
		}
	},

	do_not_explode(frm, cdt, cdn) {
		let item = frappe.get_doc(cdt, cdn);
		if (!item.do_not_explode) {
			frm.call({
				method: "get_default_bom",
				doc: frm.doc,
				args: {
					item_code: item.item_code,
				},
				callback(r) {
					if (r.message) {
						frappe.model.set_value(cdt, cdn, "bom_no", r.message);
					}
				},
			});
		} else {
			frappe.model.set_value(cdt, cdn, "bom_no", "");
		}
	},
});

erpnext.bom.BomConfigurator = class BomConfigurator extends erpnext.TransactionController {
	conversion_rate(doc) {
		if (this.frm.doc.currency === this.get_company_currency()) {
			this.frm.set_value("conversion_rate", 1.0);
		} else {
			erpnext.bom.update_cost(doc);
		}
	}

	buying_price_list(doc) {
		this.apply_price_list();
	}

	plc_conversion_rate(doc) {
		if (!this.in_apply_price_list) {
			this.apply_price_list(null, true);
		}
	}

	conversion_factor(doc, cdt, cdn) {
		if (frappe.meta.get_docfield(cdt, "stock_qty", cdn)) {
			var item = frappe.get_doc(cdt, cdn);
			frappe.model.round_floats_in(item, ["qty", "conversion_factor"]);
			item.stock_qty = flt(item.qty * item.conversion_factor, precision("stock_qty", item));
			refresh_field("stock_qty", item.name, item.parentfield);
			this.toggle_conversion_factor(item);
		}
	}
};

extend_cscript(cur_frm.cscript, new erpnext.bom.BomConfigurator({ frm: cur_frm }));

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
