# Master Control Plan: `Stock Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Default settings for your stock-related transactions

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `defaults_tab` | Defaults | Tab Break | None |  |  |  | None | None |
| `item_defaults_section` | Item Defaults | Section Break | None |  |  |  | None | None |
| `item_naming_by` | Item Naming By | Select | Item Code
Naming Series |  |  |  | Item Code | None |
| `valuation_method` | Default Valuation Method | Select | FIFO
Moving Average
LIFO |  |  |  | None | None |
| `item_group` | Default Item Group | Link | Item Group |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `default_warehouse` | Default Warehouse | Link | Warehouse |  |  |  | None | None |
| `sample_retention_warehouse` | Sample Retention Warehouse | Link | Warehouse |  |  |  | None | None |
| `stock_uom` | Default Stock UOM | Link | UOM |  |  |  | None | None |
| `price_list_defaults_section` | Price List Defaults | Section Break | None |  |  |  | None | None |
| `auto_insert_price_list_rate_if_missing` | Auto Insert Item Price If Missing | Check | None |  |  |  | 0 | None |
| `update_price_list_based_on` | Update Price List Based On | Select | Rate
Price List Rate |  |  |  | Rate | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `update_existing_price_list_rate` | Update Existing Price List Rate | Check | None |  |  |  | 0 | None |
| `conversion_factor_section` | Stock UOM Quantity | Section Break | None |  |  |  | None | None |
| `allow_to_edit_stock_uom_qty_for_sales` | Allow to Edit Stock UOM Qty for Sales Documents | Check | None |  |  |  | 0 | None |
| `column_break_lznj` | None | Column Break | None |  |  |  | None | None |
| `allow_to_edit_stock_uom_qty_for_purchase` | Allow to Edit Stock UOM Qty for Purchase Documents | Check | None |  |  |  | 0 | None |
| `section_break_ylhd` | None | Section Break | None |  |  |  | None | None |
| `allow_uom_with_conversion_rate_defined_in_item` | Allow UOM with Conversion Rate Defined in Item | Check | None |  |  |  | 0 | If enabled, the system will allow selecting UOMs in sales and purchase transactions only if the conversion rate is set in the item master. |
| `stock_validations_tab` | Stock Validations | Tab Break | None |  |  |  | None | None |
| `section_break_9` | Stock Transactions Settings | Section Break | None |  |  |  | None | None |
| `over_delivery_receipt_allowance` | Over Delivery/Receipt Allowance (%) | Float | None |  |  |  | None | The percentage you are allowed to receive or deliver more against the quantity ordered. For example, if you have ordered 100 units, and your Allowance is 10%, then you are allowed to receive 110 units. |
| `mr_qty_allowance` | Over Transfer Allowance | Float | None |  |  |  | None | The percentage you are allowed to transfer more against the quantity ordered. For example, if you have ordered 100 units, and your Allowance is 10%, then you are allowed transfer 110 units. |
| `over_picking_allowance` | Over Picking Allowance | Percent | None |  |  |  | None | The percentage you are allowed to pick more items in the pick list than the ordered quantity. |
| `column_break_121` | None | Column Break | None |  |  |  | None | None |
| `role_allowed_to_over_deliver_receive` | Role Allowed to Over Deliver/Receive | Link | Role |  |  |  | None | Users with this role are allowed to over deliver/receive against orders above the allowance percentage |
| `allow_negative_stock` | Allow Negative Stock | Check | None |  |  |  | 0 | None |
| `show_barcode_field` | Show Barcode Field in Stock Transactions | Check | None |  |  |  | 1 | None |
| `clean_description_html` | Convert Item Description to Clean HTML in Transactions | Check | None |  |  |  | 1 | None |
| `allow_internal_transfer_at_arms_length_price` | Allow Internal Transfers at Arm's Length Price | Check | None |  |  |  | 0 | If enabled, the item rate won't adjust to the valuation rate during internal transfers, but accounting will still use the valuation rate. |
| `serial_and_batch_item_settings_tab` | Serial & Batch Item | Tab Break | None |  |  |  | None | None |
| `section_break_7` | Serial & Batch Item Settings | Section Break | None |  |  |  | None | None |
| `allow_existing_serial_no` | Allow existing Serial No to be Manufactured/Received again | Check | None |  |  |  | 1 | None |
| `do_not_use_batchwise_valuation` | Do Not Use Batch-wise Valuation | Check | None |  |  |  | 0 | If enabled, the system will use the moving average valuation method to calculate the valuation rate for the batched items and will not consider the individual batch-wise incoming rate. |
| `auto_create_serial_and_batch_bundle_for_outward` | Auto Create Serial and Batch Bundle For Outward | Check | None |  |  |  | 1 | None |
| `pick_serial_and_batch_based_on` | Pick Serial / Batch Based On | Select | FIFO
LIFO
Expiry |  |  |  | FIFO | None |
| `column_break_mhzc` | None | Column Break | None |  |  |  | None | None |
| `disable_serial_no_and_batch_selector` | Disable Serial No And Batch Selector | Check | None |  |  |  | 0 | None |
| `use_serial_batch_fields` | Use Serial / Batch Fields | Check | None |  |  |  | 1 | On submission of the stock transaction, system will auto create the Serial and Batch Bundle based on the Serial No / Batch fields. |
| `do_not_update_serial_batch_on_creation_of_auto_bundle` | Do Not Update Serial / Batch on Creation of Auto Bundle | Check | None |  |  |  | 1 | If enabled, do not update serial / batch values in the stock transactions on creation of auto Serial 
 / Batch Bundle.  |
| `serial_and_batch_bundle_section` | Serial and Batch Bundle | Section Break | None |  |  |  | None | None |
| `set_serial_and_batch_bundle_naming_based_on_naming_series` | Set Serial and Batch Bundle Naming Based on Naming Series | Check | None |  |  |  | 0 | None |
| `section_break_gnhq` | None | Section Break | None |  |  |  | None | None |
| `use_naming_series` | Have Default Naming Series for Batch ID? | Check | None |  |  |  | 0 | None |
| `column_break_wslv` | None | Column Break | None |  |  |  | None | None |
| `naming_series_prefix` | Naming Series Prefix | Data | None |  |  |  | BATCH- | None |
| `stock_reservation_tab` | Stock Reservation | Tab Break | None |  |  |  | None | None |
| `enable_stock_reservation` | Enable Stock Reservation | Check | None |  |  |  | 0 | Allows to keep aside a specific quantity of inventory for a particular order. |
| `auto_reserve_stock` | Auto Reserve Stock | Check | None |  |  |  | 0 | Upon submission of the Sales Order, Work Order, or Production Plan, the system will automatically reserve the stock. |
| `column_break_rx3e` | None | Column Break | None |  |  |  | None | None |
| `allow_partial_reservation` | Allow Partial Reservation | Check | None |  |  |  | 1 | Partial stock can be reserved. For example, If you have a Sales Order of 100 units and the Available Stock is 90 units then a Stock Reservation Entry will be created for 90 units.  |
| `auto_reserve_stock_for_sales_order_on_purchase` | Auto Reserve Stock for Sales Order on Purchase | Check | None |  |  |  | 0 | Stock will be reserved on submission of <b>Purchase Receipt</b> created against Material Request for Sales Order. |
| `serial_and_batch_reservation_section` | Serial and Batch Reservation | Section Break | None |  |  |  | None | None |
| `auto_reserve_serial_and_batch` | Auto Reserve Serial and Batch Nos | Check | None |  |  |  | 1 | Serial and Batch Nos will be auto-reserved based on <b>Pick Serial / Batch Based On</b> |
| `quality_tab` | Quality | Tab Break | None |  |  |  | None | None |
| `quality_inspection_settings_section` | Quality Inspection Settings | Section Break | None |  |  |  | None | None |
| `action_if_quality_inspection_is_not_submitted` | Action If Quality Inspection Is Not Submitted | Select | Stop
Warn |  |  |  | Stop | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `action_if_quality_inspection_is_rejected` | Action If Quality Inspection Is Rejected | Select | Stop
Warn |  |  |  | Stop | None |
| `section_break_uiau` | None | Section Break | None |  |  |  | None | None |
| `allow_to_make_quality_inspection_after_purchase_or_delivery` | Allow to Make Quality Inspection after Purchase / Delivery | Check | None |  |  |  | 0 | None |
| `stock_planning_tab` | Stock Planning | Tab Break | None |  |  |  | None | None |
| `auto_material_request` | Auto Material Request | Section Break | None |  |  |  | None | None |
| `auto_indent` | Raise Material Request When Stock Reaches Re-order Level | Check | None |  |  |  | 0 | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `reorder_email_notify` | Notify by Email on Creation of Automatic Material Request | Check | None |  |  |  | 0 | None |
| `inter_warehouse_transfer_settings_section` | Inter Warehouse Transfer Settings | Section Break | None |  |  |  | None | None |
| `allow_from_dn` | Allow Material Transfer from Delivery Note to Sales Invoice | Check | None |  |  |  | 0 | None |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `allow_from_pr` | Allow Material Transfer from Purchase Receipt to Purchase Invoice | Check | None |  |  |  | 0 | None |
| `stock_closing_tab` | Stock Closing | Tab Break | None |  |  |  | None | None |
| `control_historical_stock_transactions_section` | Control Historical Stock Transactions | Section Break | None |  |  |  | None | None |
| `stock_frozen_upto` | Stock Frozen Up To | Date | None |  |  |  | None | No stock transactions can be created or modified before this date. |
| `stock_frozen_upto_days` | Freeze Stocks Older Than (Days) | Int | None |  |  |  | None | Stock transactions that are older than the mentioned days cannot be modified. |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `role_allowed_to_create_edit_back_dated_transactions` | Role Allowed to Create/Edit Back-dated Transactions | Link | Role |  |  |  | None | If mentioned, the system will allow only the users with this Role to create or modify any stock transaction earlier than the latest stock transaction for a specific item and warehouse. If set as blank, it allows all users to create/edit back-dated transactions. |
| `stock_auth_role` | Role Allowed to Edit Frozen Stock | Link | Role |  |  |  | None | The users with this Role are allowed to create/modify a stock transaction, even though the transaction is frozen. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_settings/stock_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Stock Settings", {
	refresh: function (frm) {
		let filters = function () {
			return {
				filters: {
					is_group: 0,
				},
			};
		};

		frm.set_query("default_warehouse", filters);
		frm.set_query("sample_retention_warehouse", filters);
	},

	use_serial_batch_fields(frm) {
		if (frm.doc.use_serial_batch_fields && !frm.doc.disable_serial_no_and_batch_selector) {
			frm.set_value("disable_serial_no_and_batch_selector", 1);
		}
	},

	disable_serial_no_and_batch_selector(frm) {
		if (!frm.doc.disable_serial_no_and_batch_selector && frm.doc.use_serial_batch_fields) {
			frm.set_value("disable_serial_no_and_batch_selector", 1);
			frappe.msgprint(
				__("Serial No and Batch Selector cannot be use when Use Serial / Batch Fields is enabled.")
			);
		}
	},

	allow_negative_stock: function (frm) {
		if (!frm.doc.allow_negative_stock) {
			return;
		}

		let msg = __(
			"Using negative stock disables FIFO/Moving average valuation when inventory is negative."
		);
		msg += " ";
		msg += __("This is considered dangerous from accounting point of view.");
		msg += "<br>";
		msg += __("Do you still want to enable negative inventory?");

		frappe.confirm(
			msg,
			() => {},
			() => {
				frm.set_value("allow_negative_stock", 0);
			}
		);
	},
	auto_insert_price_list_rate_if_missing(frm) {
		if (!frm.doc.auto_insert_price_list_rate_if_missing) return;

		frm.set_value(
			"update_price_list_based_on",
			cint(frappe.defaults.get_default("editable_price_list_rate")) ? "Price List Rate" : "Rate"
		);
	},
	update_price_list_based_on(frm) {
		if (
			frm.doc.update_price_list_based_on === "Price List Rate" &&
			!cint(frappe.defaults.get_default("editable_price_list_rate"))
		) {
			const dialog = frappe.warn(
				__("Incompatible Setting Detected"),
				__(
					"<p>Price List Rate has not been set as editable in Selling Settings. In this scenario, setting <strong>Update Price List Based On</strong> to <strong>Price List Rate</strong> will prevent auto-updation of Item Price.</p>Are you sure you want to continue?"
				)
			);
			dialog.set_secondary_action(() => {
				frm.set_value("update_price_list_based_on", "Rate");
				dialog.hide();
			});
			return;
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
