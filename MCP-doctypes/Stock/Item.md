# Master Control Plan: `Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:item_code`
- **Description:** A Product or a Service that is bought, sold or kept in stock.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Item Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Maintenance User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Manufacturing User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Desk User | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details` | Details | Tab Break | fa fa-flag |  |  |  | None | None |
| `naming_series` | Series | Select | STO-ITEM-.YYYY.- |  | ✅ |  | None | None |
| `item_code` | Item Code | Data | None | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group | ✅ |  |  | None | None |
| `is_zero_rated` | Is Zero Rated | Check | None |  |  |  | None | None |
| `stock_uom` | Default Unit of Measure | Link | UOM | ✅ |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `allow_alternative_item` | Allow Alternative Item | Check | None |  |  |  | 0 | None |
| `is_stock_item` | Maintain Stock | Check | None |  |  |  | 1 | None |
| `has_variants` | Has Variants | Check | None |  |  |  | 0 | If this item has variants, then it cannot be selected in sales orders etc. |
| `opening_stock` | Opening Stock | Float | None |  |  |  | None | None |
| `valuation_rate` | Valuation Rate | Currency | None |  |  |  | None | None |
| `standard_rate` | Standard Selling Rate | Currency | None |  |  |  | None | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  |  |  | 0 | None |
| `auto_create_assets` | Auto Create Assets on Purchase | Check | None |  |  |  | 0 | None |
| `is_grouped_asset` | Create Grouped Asset | Check | None |  |  |  | 0 | None |
| `asset_category` | Asset Category | Link | Asset Category |  |  |  | None | None |
| `asset_naming_series` | Asset Naming Series | Select | None |  |  |  | None | None |
| `over_delivery_receipt_allowance` | Over Delivery/Receipt Allowance (%) | Float | None |  |  |  | None | None |
| `over_billing_allowance` | Over Billing Allowance (%) | Float | None |  |  |  | None | None |
| `image` | Image | Attach Image | image |  | ✅ |  | None | None |
| `section_break_11` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `brand` | Brand | Link | Brand |  |  |  | None | None |
| `unit_of_measure_conversion` | Units of Measure | Section Break | None |  |  |  | None | None |
| `uoms` | UOMs | Table | UOM Conversion Detail |  |  |  | None | Will also apply for variants |
| `dashboard_tab` | Dashboard | Tab Break | None |  |  |  | None | None |
| `inventory_section` | Inventory | Tab Break | fa fa-truck |  |  |  | None | None |
| `inventory_settings_section` | Inventory Settings | Section Break | None |  |  |  | None | None |
| `shelf_life_in_days` | Shelf Life In Days | Int | None |  |  |  | None | None |
| `end_of_life` | End of Life | Date | None |  |  |  | 2099-12-31 | None |
| `default_material_request_type` | Default Material Request Type | Select | Purchase
Material Transfer
Material Issue
Manufacture
Customer Provided |  |  |  | Purchase | None |
| `valuation_method` | Valuation Method | Select | 
FIFO
Moving Average
LIFO |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `warranty_period` | Warranty Period (in days) | Data | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  |  | None | None |
| `allow_negative_stock` | Allow Negative Stock | Check | None |  |  |  | 0 | None |
| `sb_barcodes` | Barcodes | Section Break | None |  |  |  | None | None |
| `barcodes` | Barcodes | Table | Item Barcode |  |  |  | None | None |
| `reorder_section` | Auto re-order | Section Break | fa fa-rss |  |  |  | None | None |
| `reorder_levels` | Reorder level based on Warehouse | Table | Item Reorder |  |  |  | None | Will also apply for variants unless overridden |
| `serial_nos_and_batches` | Serial Nos and Batches | Section Break | None |  |  |  | None | None |
| `has_batch_no` | Has Batch No | Check | None |  |  |  | 0 | None |
| `create_new_batch` | Automatically Create New Batch | Check | None |  |  |  | 0 | None |
| `batch_number_series` | Batch Number Series | Data | None |  |  |  | None | Example: ABCD.#####. If series is set and Batch No is not mentioned in transactions, then automatic batch number will be created based on this series. If you always want to explicitly mention Batch No for this item, leave this blank. Note: this setting will take priority over the Naming Series Prefix in Stock Settings. |
| `has_expiry_date` | Has Expiry Date | Check | None |  |  |  | 0 | None |
| `retain_sample` | Retain Sample | Check | None |  |  |  | 0 | None |
| `sample_quantity` | Max Sample Quantity | Int | None |  |  |  | None | Maximum sample quantity that can be retained |
| `column_break_37` | None | Column Break | None |  |  |  | None | None |
| `has_serial_no` | Has Serial No | Check | None |  |  |  | 0 | None |
| `serial_no_series` | Serial Number Series | Data | None |  |  |  | None | Example: ABCD.#####
If series is set and Serial No is not mentioned in transactions, then automatic serial number will be created based on this series. If you always want to explicitly mention Serial Nos for this item. leave this blank. |
| `variants_section` | Variants | Tab Break | None |  |  |  | None | None |
| `variant_of` | Variant Of | Link | Item |  |  | ✅ | None | If item is a variant of another item then description, image, pricing, taxes etc will be set from the template unless explicitly specified |
| `variant_based_on` | Variant Based On | Select | Item Attribute
Manufacturer |  |  |  | Item Attribute | None |
| `attributes` | Variant Attributes | Table | Item Variant Attribute |  | ✅ |  | None | None |
| `accounting` | Accounting | Tab Break | None |  |  |  | None | None |
| `deferred_accounting_section` | Deferred Accounting | Section Break | None |  |  |  | None | None |
| `enable_deferred_expense` | Enable Deferred Expense | Check | None |  |  |  | 0 | None |
| `no_of_months_exp` | No of Months (Expense) | Int | None |  |  |  | None | None |
| `column_break_9s9o` | None | Column Break | None |  |  |  | None | None |
| `enable_deferred_revenue` | Enable Deferred Revenue | Check | None |  |  |  | 0 | None |
| `no_of_months` | No of Months (Revenue) | Int | None |  |  |  | None | None |
| `section_break_avcp` | None | Section Break | None |  |  |  | None | None |
| `item_defaults` | Item Defaults | Table | Item Default |  |  |  | None | None |
| `purchasing_tab` | Purchasing | Tab Break | None |  |  |  | None | None |
| `purchase_uom` | Default Purchase Unit of Measure | Link | UOM |  |  |  | None | None |
| `min_order_qty` | Minimum Order Qty | Float | None |  |  |  | 0.00 | Minimum quantity should be as per Stock UOM |
| `safety_stock` | Safety Stock | Float | None |  |  |  | None | None |
| `is_purchase_item` | Allow Purchase | Check | None |  |  |  | 1 | None |
| `purchase_details_cb` | None | Column Break | None |  |  |  | None | None |
| `lead_time_days` | Lead Time in days | Int | None |  |  |  | None | Average time taken by the supplier to deliver |
| `last_purchase_rate` | Last Purchase Rate | Float | None |  |  | ✅ | None | None |
| `is_customer_provided_item` | Is Customer Provided Item | Check | None |  |  |  | 0 | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier_details` | Supplier Details | Section Break | None |  |  |  | None | None |
| `delivered_by_supplier` | Delivered by Supplier (Drop Ship) | Check | None |  |  |  | 0 | None |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `supplier_items` | Supplier Items | Table | Item Supplier |  |  |  | None | None |
| `foreign_trade_details` | Foreign Trade Details | Section Break | None |  |  |  | None | None |
| `country_of_origin` | Country of Origin | Link | Country |  |  |  | None | None |
| `column_break_59` | None | Column Break | None |  |  |  | None | None |
| `customs_tariff_number` | Customs Tariff Number | Link | Customs Tariff Number |  |  |  | None | None |
| `sales_details` | Sales | Tab Break | fa fa-tag |  |  |  | None | None |
| `sales_uom` | Default Sales Unit of Measure | Link | UOM |  |  |  | None | None |
| `grant_commission` | Grant Commission | Check | None |  |  |  | 1 | None |
| `is_sales_item` | Allow Sales | Check | None |  |  |  | 1 | None |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `max_discount` | Max Discount (%) | Float | None |  |  |  | None | None |
| `customer_details` | Customer Details | Section Break | None |  |  |  | None | None |
| `customer_items` | Customer Items | Table | Item Customer Detail |  |  |  | None | None |
| `item_tax_section_break` | Tax | Tab Break | fa fa-money |  |  |  | None | None |
| `taxes` | Taxes | Table | Item Tax |  |  |  | None | Will also apply for variants |
| `quality_tab` | Quality | Tab Break | None |  |  |  | None | None |
| `inspection_required_before_purchase` | Inspection Required before Purchase | Check | None |  |  |  | 0 | None |
| `quality_inspection_template` | Quality Inspection Template | Link | Quality Inspection Template |  |  |  | None | None |
| `inspection_required_before_delivery` | Inspection Required before Delivery | Check | None |  |  |  | 0 | None |
| `manufacturing` | Manufacturing | Tab Break | fa fa-cogs |  |  |  | None | None |
| `include_item_in_manufacturing` | Include Item In Manufacturing | Check | None |  |  |  | 1 | None |
| `is_sub_contracted_item` | Supply Raw Materials for Purchase | Check | None |  |  |  | 0 | If subcontracted to a vendor |
| `default_bom` | Default BOM | Link | BOM |  |  | ✅ | None | None |
| `column_break_74` | None | Column Break | None |  |  |  | None | None |
| `customer_code` | Customer Code | Small Text | None |  | ✅ |  | None | None |
| `default_item_manufacturer` | Default Item Manufacturer | Link | Manufacturer |  |  | ✅ | None | None |
| `default_manufacturer_part_no` | Default Manufacturer Part No | Data | None |  |  | ✅ | None | None |
| `published_in_website` | Published In Website | Check | None |  |  | ✅ | 0 | None |
| `total_projected_qty` | Total Projected Qty | Float | None |  | ✅ | ✅ | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `published_in_website` | Published In Website | Check | None |  |  | ✅ | 0 | None |
| `is_zero_rated` | Is Zero Rated | Check | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 14
- **Dynamic Link Fields:** 0
- **Table Fields:** 8

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/item/item.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.item");

const SALES_DOCTYPES = ["Quotation", "Sales Order", "Delivery Note", "Sales Invoice"];
const PURCHASE_DOCTYPES = ["Purchase Order", "Purchase Receipt", "Purchase Invoice"];

frappe.ui.form.on("Item", {
	valuation_method(frm) {
		if (!frm.is_new() && frm.doc.valuation_method === "Moving Average") {
			let stock_exists = frm.doc.__onload && frm.doc.__onload.stock_exists ? 1 : 0;
			let current_valuation_method = frm.doc.__onload.current_valuation_method;

			if (stock_exists && current_valuation_method !== frm.doc.valuation_method) {
				let msg = __(
					"Changing the valuation method to Moving Average will affect new transactions. If backdated entries are added, earlier FIFO-based entries will be reposted, which may change closing balances."
				);
				msg += "<br><br>";
				msg += __(
					"Also you can't switch back to FIFO after setting the valuation method to Moving Average for this item."
				);
				msg += "<br><br>";
				msg += __("Do you want to change valuation method?");

				frappe.confirm(
					msg,
					() => {
						frm.set_value("valuation_method", "Moving Average");
					},
					() => {
						frm.set_value("valuation_method", current_valuation_method);
					}
				);
			}
		}
	},

	setup: function (frm) {
		frm.add_fetch("attribute", "numeric_values", "numeric_values");
		frm.add_fetch("attribute", "from_range", "from_range");
		frm.add_fetch("attribute", "to_range", "to_range");
		frm.add_fetch("attribute", "increment", "increment");
		frm.add_fetch("tax_type", "tax_rate", "tax_rate");

		frm.make_methods = {
			Quotation: () => {
				open_form(frm, "Quotation", "Quotation Item", "items");
			},
			"Sales Order": () => {
				open_form(frm, "Sales Order", "Sales Order Item", "items");
			},
			"Delivery Note": () => {
				open_form(frm, "Delivery Note", "Delivery Note Item", "items");
			},
			"Sales Invoice": () => {
				open_form(frm, "Sales Invoice", "Sales Invoice Item", "items");
			},
			"Purchase Order": () => {
				open_form(frm, "Purchase Order", "Purchase Order Item", "items");
			},
			"Purchase Receipt": () => {
				open_form(frm, "Purchase Receipt", "Purchase Receipt Item", "items");
			},
			"Purchase Invoice": () => {
				open_form(frm, "Purchase Invoice", "Purchase Invoice Item", "items");
			},
			"Material Request": () => {
				open_form(frm, "Material Request", "Material Request Item", "items");
			},
			"Stock Entry": () => {
				open_form(frm, "Stock Entry", "Stock Entry Detail", "items");
			},
		};
	},
	onload: function (frm) {
		erpnext.item.setup_queries(frm);
		if (frm.doc.variant_of) {
			frm.fields_dict["attributes"].grid.set_column_disp("attribute_value", true);
		}

		if (frm.doc.is_fixed_asset) {
			frm.trigger("set_asset_naming_series");
		}
	},

	refresh: function (frm) {
		if (frm.doc.is_stock_item) {
			frm.add_custom_button(
				__("Stock Balance"),
				function () {
					frappe.route_options = {
						item_code: frm.doc.name,
					};
					frappe.set_route("query-report", "Stock Balance");
				},
				__("View")
			);
			frm.add_custom_button(
				__("Stock Ledger"),
				function () {
					frappe.route_options = {
						item_code: frm.doc.name,
					};
					frappe.set_route("query-report", "Stock Ledger");
				},
				__("View")
			);
			frm.add_custom_button(
				__("Stock Projected Qty"),
				function () {
					frappe.route_options = {
						item_code: frm.doc.name,
					};
					frappe.set_route("query-report", "Stock Projected Qty");
				},
				__("View")
			);
		}

		if (frm.doc.is_fixed_asset) {
			frm.trigger("is_fixed_asset");
			frm.trigger("auto_create_assets");
		}

		// clear intro
		frm.set_intro();

		if (frm.doc.has_variants) {
			frm.set_intro(
				__(
					"This Item is a Template and cannot be used in transactions. Item attributes will be copied over into the variants unless 'No Copy' is set"
				),
				true
			);

			frm.add_custom_button(
				__("Show Variants"),
				function () {
					frappe.set_route("List", "Item", { variant_of: frm.doc.name });
				},
				__("View")
			);

			frm.add_custom_button(
				__("Item Variant Settings"),
				function () {
					frappe.set_route("Form", "Item Variant Settings");
				},
				__("View")
			);

			frm.add_custom_button(
				__("Variant Details Report"),
				function () {
					frappe.set_route("query-report", "Item Variant Details", { item: frm.doc.name });
				},
				__("View")
			);

			if (frm.doc.variant_based_on === "Item Attribute") {
				frm.add_custom_button(
					__("Single Variant"),
					function () {
						erpnext.item.show_single_variant_dialog(frm);
					},
					__("Create")
				);
				frm.add_custom_button(
					__("Multiple Variants"),
					function () {
						erpnext.item.show_multiple_variants_dialog(frm);
					},
					__("Create")
				);
			} else {
				frm.add_custom_button(
					__("Variant"),
					function () {
						erpnext.item.show_modal_for_manufacturers(frm);
					},
					__("Create")
				);
			}

			// frm.page.set_inner_btn_group_as_primary(__('Create'));
		}
		if (frm.doc.variant_of) {
			frm.set_intro(
				__("This Item is a Variant of {0} (Template).", [
					`<a href="/app/item/${frm.doc.variant_of}" onclick="location.reload()">${frm.doc.variant_of}</a>`,
				]),
				true
			);
		}

		if (frappe.defaults.get_default("item_naming_by") != "Naming Series" || frm.doc.variant_of) {
			frm.toggle_display("naming_series", false);
		} else {
			erpnext.toggle_naming_series();
		}

		erpnext.item.edit_prices_button(frm);
		erpnext.item.toggle_attributes(frm);

		if (!frm.doc.is_fixed_asset) {
			erpnext.item.make_dashboard(frm);
		}

		frm.add_custom_button(__("Duplicate"), function () {
			var new_item = frappe.model.copy_doc(frm.doc);
			// Duplicate item could have different name, causing "copy paste" error.
			if (new_item.item_name === new_item.item_code) {
				new_item.item_name = null;
			}
			if (new_item.item_code === new_item.description || new_item.item_code === new_item.description) {
				new_item.description = null;
			}
			frappe.set_route("Form", "Item", new_item.name);
		});

		const stock_exists = frm.doc.__onload && frm.doc.__onload.stock_exists ? 1 : 0;

		["is_stock_item", "has_serial_no", "has_batch_no", "has_variants"].forEach((fieldname) => {
			frm.set_df_property(fieldname, "read_only", stock_exists);
		});

		frm.toggle_reqd("customer", frm.doc.is_customer_provided_item ? 1 : 0);
	},

	validate: function (frm) {
		erpnext.item.weight_to_validate(frm);
	},

	image: function () {
		refresh_field("image_view");
	},

	is_customer_provided_item: function (frm) {
		frm.toggle_reqd("customer", frm.doc.is_customer_provided_item ? 1 : 0);
	},

	is_fixed_asset: function (frm) {
		// set serial no to false & toggles its visibility
		frm.set_value("has_serial_no", 0);
		frm.set_value("has_batch_no", 0);
		frm.toggle_enable(["has_serial_no", "serial_no_series"], !frm.doc.is_fixed_asset);

		frappe.call({
			method: "erpnext.stock.doctype.item.item.get_asset_naming_series",
			callback: function (r) {
				frm.set_value("is_stock_item", frm.doc.is_fixed_asset ? 0 : 1);
				frm.events.set_asset_naming_series(frm, r.message);
			},
		});

		frm.trigger("auto_create_assets");
	},

	set_asset_naming_series: function (frm, asset_naming_series) {
		if ((frm.doc.__onload && frm.doc.__onload.asset_naming_series) || asset_naming_series) {
			let naming_series =
				(frm.doc.__onload && frm.doc.__onload.asset_naming_series) || asset_naming_series;
			frm.set_df_property("asset_naming_series", "options", naming_series);
		}
	},

	auto_create_assets: function (frm) {
		frm.toggle_reqd(["asset_naming_series"], frm.doc.auto_create_assets);
		frm.toggle_display(["asset_naming_series"], frm.doc.auto_create_assets);
	},

	page_name: frappe.utils.warn_page_name_change,

	item_code: function (frm) {
		if (!frm.doc.item_name) frm.set_value("item_name", frm.doc.item_code);
	},

	is_stock_item: function (frm) {
		if (!frm.doc.is_stock_item) {
			frm.set_value("has_batch_no", 0);
			frm.set_value("create_new_batch", 0);
			frm.set_value("has_serial_no", 0);
		}
	},

	has_variants: function (frm) {
		erpnext.item.toggle_attributes(frm);
	},
});

frappe.ui.form.on("Item Reorder", {
	reorder_levels_add: function (frm, cdt, cdn) {
		var row = frappe.get_doc(cdt, cdn);
		var type = frm.doc.default_material_request_type;
		row.material_request_type = type == "Material Transfer" ? "Transfer" : type;
	},
});

frappe.ui.form.on("Item Customer Detail", {
	customer_items_add: function (frm, cdt, cdn) {
		frappe.model.set_value(cdt, cdn, "customer_group", "");
	},
	customer_name: function (frm, cdt, cdn) {
		set_customer_group(frm, cdt, cdn);
	},
	customer_group: function (frm, cdt, cdn) {
		if (set_customer_group(frm, cdt, cdn)) {
			frappe.msgprint(__("Changing Customer Group for the selected Customer is not allowed."));
		}
	},
});

var set_customer_group = function (frm, cdt, cdn) {
	var row = frappe.get_doc(cdt, cdn);

	if (!row.customer_name) {
		return false;
	}

	frappe.model.with_doc("Customer", row.customer_name, function () {
		var customer = frappe.model.get_doc("Customer", row.customer_name);
		row.customer_group = customer.customer_group;
		refresh_field("customer_group", cdn, "customer_items");
	});
	return true;
};

$.extend(erpnext.item, {
	setup_queries: function (frm) {
		frm.fields_dict["item_defaults"].grid.get_field("expense_account").get_query = function (
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

		frm.fields_dict["item_defaults"].grid.get_field("income_account").get_query = function (
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

		frm.fields_dict["item_defaults"].grid.get_field("default_discount_account").get_query = function (
			doc,
			cdt,
			cdn
		) {
			const row = locals[cdt][cdn];
			return {
				filters: {
					report_type: "Profit and Loss",
					company: row.company,
					is_group: 0,
				},
			};
		};

		frm.fields_dict["item_defaults"].grid.get_field("buying_cost_center").get_query = function (
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

		frm.fields_dict["item_defaults"].grid.get_field("selling_cost_center").get_query = function (
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

		frm.fields_dict["taxes"].grid.get_field("tax_type").get_query = function (doc, cdt, cdn) {
			return {
				filters: [
					["Account", "account_type", "in", "Tax, Chargeable, Income Account, Expense Account"],
					["Account", "docstatus", "!=", 2],
				],
			};
		};

		frm.fields_dict["item_group"].get_query = function (doc, cdt, cdn) {
			return {
				filters: [["Item Group", "docstatus", "!=", 2]],
			};
		};

		frm.fields_dict["item_defaults"].grid.get_field("deferred_revenue_account").get_query = function (
			doc,
			cdt,
			cdn
		) {
			return {
				filters: {
					company: locals[cdt][cdn].company,
					root_type: "Liability",
					is_group: 0,
				},
			};
		};

		frm.fields_dict["item_defaults"].grid.get_field("deferred_expense_account").get_query = function (
			doc,
			cdt,
			cdn
		) {
			return {
				filters: {
					company: locals[cdt][cdn].company,
					root_type: "Asset",
					is_group: 0,
				},
			};
		};

		frm.fields_dict["item_defaults"].grid.get_field("default_warehouse").get_query = function (
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

		frm.fields_dict.reorder_levels.grid.get_field("warehouse_group").get_query = function (
			doc,
			cdt,
			cdn
		) {
			return {
				filters: { is_group: 1 },
			};
		};

		frm.fields_dict.reorder_levels.grid.get_field("warehouse").get_query = function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];

			var filters = {
				is_group: 0,
			};

			if (d.parent_warehouse) {
				filters.extend({ parent_warehouse: d.warehouse_group });
			}

			return {
				filters: filters,
			};
		};

		frm.set_query("default_provisional_account", "item_defaults", (doc, cdt, cdn) => {
			let row = locals[cdt][cdn];
			return {
				filters: {
					company: row.company,
					root_type: ["in", ["Liability", "Asset"]],
					is_group: 0,
				},
			};
		});
	},

	make_dashboard: function (frm) {
		if (frm.doc.__islocal) return;

		// Show Stock Levels only if is_stock_item
		if (frm.doc.is_stock_item) {
			frappe.require("item-dashboard.bundle.js", function () {
				const section = frm.dashboard.add_section("", __("Stock Levels"));
				erpnext.item.item_dashboard = new erpnext.stock.ItemDashboard({
					parent: section,
					item_code: frm.doc.name,
					page_length: 20,
					method: "erpnext.stock.dashboard.item_dashboard.get_data",
					template: "item_dashboard_list",
				});
				erpnext.item.item_dashboard.refresh();
			});
		}
	},

	edit_prices_button: function (frm) {
		frm.add_custom_button(
			__("Add / Edit Prices"),
			function () {
				frappe.set_route("List", "Item Price", { item_code: frm.doc.name });
			},
			__("Actions")
		);
	},

	weight_to_validate: function (frm) {
		if (frm.doc.weight_per_unit && !frm.doc.weight_uom) {
			frappe.msgprint({
				message: __("Please mention 'Weight UOM' along with Weight."),
				title: __("Note"),
			});
		}
	},

	show_modal_for_manufacturers: function (frm) {
		var dialog = new frappe.ui.Dialog({
			fields: [
				{
					fieldtype: "Link",
					fieldname: "manufacturer",
					options: "Manufacturer",
					label: "Manufacturer",
					reqd: 1,
				},
				{
					fieldtype: "Data",
					label: "Manufacturer Part Number",
					fieldname: "manufacturer_part_no",
				},
			],
		});

		dialog.set_primary_action(__("Create"), function () {
			var data = dialog.get_values();
			if (!data) return;

			// call the server to make the variant
			data.template = frm.doc.name;
			frappe.call({
				method: "erpnext.controllers.item_variant.get_variant",
				args: data,
				callback: function (r) {
					var doclist = frappe.model.sync(r.message);
					dialog.hide();
					frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				},
			});
		});

		dialog.show();
	},

	show_multiple_variants_dialog: function (frm) {
		var me = this;

		let promises = [];
		let attr_val_fields = {};

		function make_fields_from_attribute_values(attr_dict) {
			let fields = [];
			let att_key = frm.doc.attributes.map((idx) => idx.attribute);
			att_key.forEach((name, i) => {
				if (i % 3 === 0) {
					fields.push({ fieldtype: "Section Break" });
				}
				fields.push({ fieldtype: "Column Break", label: name });
				fields.push({
					fieldtype: "Data",
					placeholder: "Search",
					fieldname: `search_${frappe.scrub(name)}`,
					onchange: function (e) {
						let value = e.target.value;
						let result = attr_dict[name].filter((attr_value) =>
							attr_value.toString().toLowerCase().includes(value.toLowerCase())
						);
						attr_dict[name].forEach((attr_value) => {
							if (result.includes(attr_value)) {
								me.multiple_variant_dialog.set_df_property(attr_value, "hidden", 0);
							} else {
								me.multiple_variant_dialog.set_df_property(attr_value, "hidden", 1);
							}
						});
					},
				});
				attr_dict[name].forEach((value) => {
					fields.push({
						fieldtype: "Check",
						label: value,
						fieldname: value,
						default: 0,
						onchange: function () {
							let selected_attributes = get_selected_attributes();
							let lengths = [];
							Object.keys(selected_attributes).map((key) => {
								lengths.push(selected_attributes[key].length);
							});
							if (lengths.includes(0)) {
								me.multiple_variant_dialog.get_primary_btn().html(__("Create Variants"));
								me.multiple_variant_dialog.disable_primary_action();
							} else {
								let no_of_combinations = lengths.reduce((a, b) => a * b, 1);
								let msg;
								if (no_of_combinations === 1) {
									msg = __("Make {0} Variant", [no_of_combinations]);
								} else {
									msg = __("Make {0} Variants", [no_of_combinations]);
								}
								me.multiple_variant_dialog.get_primary_btn().html(msg);
								me.multiple_variant_dialog.enable_primary_action();
							}
						},
					});
				});
			});
			return fields;
		}

		function make_and_show_dialog(fields) {
			me.multiple_variant_dialog = new frappe.ui.Dialog({
				title: __("Select Attribute Values"),
				fields: [
					frm.doc.image
						? {
								fieldtype: "Check",
								label: __("Create a variant with the template image."),
								fieldname: "use_template_image",
								default: 0,
						  }
						: null,
					{
						fieldtype: "HTML",
						fieldname: "help",
						options: `<label class="control-label">
							${__("Select at least one value from each of the attributes.")}
						</label>`,
					},
				]
					.concat(fields)
					.filter(Boolean),
			});

			me.multiple_variant_dialog.set_primary_action(__("Create Variants"), () => {
				let selected_attributes = get_selected_attributes();
				let use_template_image = me.multiple_variant_dialog.get_value("use_template_image");

				me.multiple_variant_dialog.hide();
				frappe.call({
					method: "erpnext.controllers.item_variant.enqueue_multiple_variant_creation",
					args: {
						item: frm.doc.name,
						args: selected_attributes,
						use_template_image: use_template_image,
					},
					callback: function (r) {
						if (r.message === "queued") {
							frappe.show_alert({
								message: __("Variant creation has been queued."),
								indicator: "orange",
							});
						} else {
							frappe.show_alert({
								message: __("{0} variants created.", [r.message]),
								indicator: "green",
							});
						}
					},
				});
			});

			$($(me.multiple_variant_dialog.$wrapper.find(".form-column")).find(".frappe-control")).css(
				"margin-bottom",
				"0px"
			);

			me.multiple_variant_dialog.disable_primary_action();
			me.multiple_variant_dialog.clear();
			me.multiple_variant_dialog.show();
			me.multiple_variant_dialog.$wrapper
				.find("div[data-fieldname^='search_']")
				.find(".clearfix")
				.hide();
		}

		function get_selected_attributes() {
			let selected_attributes = {};
			me.multiple_variant_dialog.$wrapper.find(".form-column").each((i, col) => {
				if (i === 0) return;
				let attribute_name = $(col).find(".column-label").html().trim();
				selected_attributes[attribute_name] = [];
				let checked_opts = $(col).find(".checkbox input");
				checked_opts.each((i, opt) => {
					if ($(opt).is(":checked")) {
						selected_attributes[attribute_name].push($(opt).attr("data-fieldname"));
					}
				});
			});

			return selected_attributes;
		}

		frm.doc.attributes.forEach(function (d) {
			if (!d.disabled) {
				let p = new Promise((resolve) => {
					if (!d.numeric_values) {
						frappe
							.call({
								method: "frappe.client.get_list",
								args: {
									doctype: "Item Attribute Value",
									filters: [["parent", "=", d.attribute]],
									fields: ["attribute_value"],
									limit_page_length: 0,
									parent: "Item Attribute",
									order_by: "idx",
								},
							})
							.then((r) => {
								if (r.message) {
									attr_val_fields[d.attribute] = r.message.map(function (d) {
										return d.attribute_value;
									});
									resolve();
								}
							});
					} else {
						let values = [];
						for (var i = d.from_range; i <= d.to_range; i = flt(i + d.increment, 6)) {
							values.push(i);
						}
						attr_val_fields[d.attribute] = values;
						resolve();
					}
				});

				promises.push(p);
			}
		}, this);

		Promise.all(promises).then(() => {
			let fields = make_fields_from_attribute_values(attr_val_fields);
			make_and_show_dialog(fields);
		});
	},

	show_single_variant_dialog: function (frm) {
		var fields = [];

		for (var i = 0; i < frm.doc.attributes.length; i++) {
			var fieldtype, desc;
			var row = frm.doc.attributes[i];

			if (!row.disabled) {
				if (row.numeric_values) {
					fieldtype = "Float";
					desc =
						"Min Value: " +
						row.from_range +
						" , Max Value: " +
						row.to_range +
						", in Increments of: " +
						row.increment;
				} else {
					fieldtype = "Data";
					desc = "";
				}
				fields = fields.concat({
					label: row.attribute,
					fieldname: row.attribute,
					fieldtype: fieldtype,
					reqd: 0,
					description: desc,
				});
			}
		}

		if (frm.doc.image) {
			fields.push({
				fieldtype: "Check",
				label: __("Create a variant with the template image."),
				fieldname: "use_template_image",
				default: 0,
			});
		}

		var d = new frappe.ui.Dialog({
			title: __("Create Variant"),
			fields: fields,
		});

		d.set_primary_action(__("Create"), function () {
			var args = d.get_values();
			if (!args) return;
			frappe.call({
				method: "erpnext.controllers.item_variant.get_variant",
				btn: d.get_primary_btn(),
				args: {
					template: frm.doc.name,
					args: d.get_values(),
				},
				callback: function (r) {
					// returns variant item
					if (r.message) {
						var variant = r.message;
						frappe.msgprint_dialog = frappe.msgprint(
							__("Item Variant {0} already exists with same attributes", [
								repl(
									'<a href="/app/item/%(item_encoded)s" class="strong variant-click">%(item)s</a>',
									{
										item_encoded: encodeURIComponent(variant),
										item: variant,
									}
								),
							])
						);
						frappe.msgprint_dialog.hide_on_page_refresh = true;
						frappe.msgprint_dialog.$wrapper.find(".variant-click").on("click", function () {
							d.hide();
						});
					} else {
						d.hide();
						frappe.call({
							method: "erpnext.controllers.item_variant.create_variant",
							args: {
								item: frm.doc.name,
								args: d.get_values(),
								use_template_image: args.use_template_image,
							},
							callback: function (r) {
								var doclist = frappe.model.sync(r.message);
								frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
							},
						});
					}
				},
			});
		});

		d.show();

		$.each(d.fields_dict, function (i, field) {
			if (field.df.fieldtype !== "Data") {
				return;
			}

			$(field.input_area).addClass("ui-front");

			var input = field.$input.get(0);
			input.awesomplete = new Awesomplete(input, {
				minChars: 0,
				maxItems: 99,
				autoFirst: true,
				list: [],
			});
			input.field = field;

			field.$input
				.on("input", function (e) {
					var term = e.target.value;
					frappe.call({
						method: "erpnext.stock.doctype.item.item.get_item_attribute",
						args: {
							parent: i,
							attribute_value: term,
						},
						callback: function (r) {
							if (r.message) {
								e.target.awesomplete.list = r.message.map(function (d) {
									return d.attribute_value;
								});
							}
						},
					});
				})
				.on("focus", function (e) {
					$(e.target).val("").trigger("input");
				})
				.on("awesomplete-open", () => {
					let modal = field.$input.parents(".modal-dialog")[0];
					if (modal) {
						$(modal).removeClass("modal-dialog-scrollable");
					}
				});
		});
	},

	toggle_attributes: function (frm) {
		if ((frm.doc.has_variants || frm.doc.variant_of) && frm.doc.variant_based_on === "Item Attribute") {
			frm.toggle_display("attributes", true);

			var grid = frm.fields_dict.attributes.grid;

			if (frm.doc.variant_of) {
				// variant

				// value column is displayed but not editable
				grid.set_column_disp("attribute_value", true);
				grid.toggle_enable("attribute_value", false);

				grid.toggle_enable("attribute", false);

				// can't change attributes since they are
				// saved when the variant was created
				frm.toggle_enable("attributes", false);
			} else {
				// template - values not required!

				// make the grid editable
				frm.toggle_enable("attributes", true);

				// value column is hidden
				grid.set_column_disp("attribute_value", false);

				// enable the grid so you can add more attributes
				grid.toggle_enable("attribute", true);
			}
		} else {
			// nothing to do with attributes, hide it
			frm.toggle_display("attributes", false);
		}
		frm.layout.refresh_sections();
	},
});

frappe.ui.form.on("UOM Conversion Detail", {
	uom: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (row.uom) {
			frappe.call({
				method: "erpnext.stock.doctype.item.item.get_uom_conv_factor",
				args: {
					uom: row.uom,
					stock_uom: frm.doc.stock_uom,
				},
				callback: function (r) {
					if (!r.exc && r.message) {
						frappe.model.set_value(cdt, cdn, "conversion_factor", r.message);
					}
				},
			});
		}
	},
});

frappe.tour["Item"] = [
	{
		fieldname: "item_code",
		title: "Item Code",
		description: __(
			"Enter an Item Code, the name will be auto-filled the same as Item Code on clicking inside the Item Name field."
		),
	},
	{
		fieldname: "item_group",
		title: "Item Group",
		description: __("Select an Item Group."),
	},
	{
		fieldname: "is_stock_item",
		title: "Maintain Stock",
		description: __(
			"If you are maintaining stock of this Item in your Inventory, ERPNext will make a stock ledger entry for each transaction of this item."
		),
	},
	{
		fieldname: "include_item_in_manufacturing",
		title: "Include Item in Manufacturing",
		description: __(
			"This is for raw material Items that'll be used to create finished goods. If the Item is an additional service like 'washing' that'll be used in the BOM, keep this unchecked."
		),
	},
	{
		fieldname: "opening_stock",
		title: "Opening Stock",
		description: __("Enter the opening stock units."),
	},
	{
		fieldname: "valuation_rate",
		title: "Valuation Rate",
		description: __(
			"There are two options to maintain valuation of stock. FIFO (first in - first out) and Moving Average. To understand this topic in detail please visit <a href='https://docs.erpnext.com/docs/v13/user/manual/en/stock/articles/item-valuation-fifo-and-moving-average' target='_blank'>Item Valuation, FIFO and Moving Average.</a>"
		),
	},
	{
		fieldname: "standard_rate",
		title: "Standard Selling Rate",
		description: __(
			"When creating an Item, entering a value for this field will automatically create an Item Price at the backend."
		),
	},
	{
		fieldname: "item_defaults",
		title: "Item Defaults",
		description: __(
			"In this section, you can define Company-wide transaction-related defaults for this Item. Eg. Default Warehouse, Default Price List, Supplier, etc."
		),
	},
];

function open_form(frm, doctype, child_doctype, parentfield) {
	frappe.model.with_doctype(doctype, () => {
		let new_doc = frappe.model.get_new_doc(doctype);

		let new_child_doc = frappe.model.add_child(new_doc, child_doctype, parentfield);
		new_child_doc.item_code = frm.doc.name;
		new_child_doc.item_name = frm.doc.item_name;
		if (in_list(SALES_DOCTYPES, doctype) && frm.doc.sales_uom) {
			new_child_doc.uom = frm.doc.sales_uom;
		} else if (in_list(PURCHASE_DOCTYPES, doctype) && frm.doc.purchase_uom) {
			new_child_doc.uom = frm.doc.purchase_uom;
		} else {
			new_child_doc.uom = frm.doc.stock_uom;
		}
		new_child_doc.description = frm.doc.description;
		if (!new_child_doc.qty) {
			new_child_doc.qty = 1.0;
		}

		frappe.run_serially([
			() => frappe.ui.form.make_quick_entry(doctype, null, null, new_doc),
			() => {
				frappe.flags.ignore_company_party_validation = true;
				frappe.model.trigger("item_code", frm.doc.name, new_child_doc);
			},
		]);
	});
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Stock Qty vs Serial No Count` | Script Report | Stock |
| `Item Price Stock` | Script Report | Stock |
| `Item Variant Details` | Script Report | Stock |
| `Stock Projected Qty` | Script Report | Stock |
| `Stock Ageing` | Script Report | Stock |
| `Itemwise Recommended Reorder Level` | Script Report | Stock |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Active Items` | Total Active Items | Count | Stock |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
