# Master Control Plan: `Subcontracting Receipt`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Subcontracting`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | MAT-SCR-.YYYY.-
MAT-SCR-RET-.YYYY.- | ✅ |  |  | None | None |
| `supplier` | Job Worker | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Job Worker Name | Data | None |  |  | ✅ | None | None |
| `supplier_delivery_note` | Job Worker Delivery Note | Data | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None | ✅ |  |  | None | Time at which materials were received |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `is_return` | Is Return | Check | None |  |  | ✅ | 0 | None |
| `return_against` | Return Against Subcontracting Receipt | Link | Subcontracting Receipt |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions  | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `sec_warehouse` | None | Section Break | None |  |  |  | None | None |
| `set_warehouse` | Accepted Warehouse | Link | Warehouse |  |  |  | None | Sets 'Accepted Warehouse' in each row of the Items table. |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | Sets 'Rejected Warehouse' in each row of the Items table. |
| `col_break_warehouse` | None | Column Break | None |  |  |  | None | None |
| `supplier_warehouse` | Job Worker Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `get_scrap_items` | Get Scrap Items | Button | get_scrap_items |  |  |  | None | None |
| `items` | Items | Table | Subcontracting Receipt Item | ✅ |  |  | None | None |
| `section_break0` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `raw_materials_consumed_section` | Raw Materials Actions | Section Break | None |  |  |  | None | None |
| `reset_raw_materials_table` | Reset Raw Materials Table | Button | None |  |  |  | None | None |
| `column_break_uinr` | None | Column Break | None |  |  |  | None | None |
| `get_current_stock` | Get Current Stock | Button | get_current_stock |  |  |  | None | None |
| `raw_material_details` | Raw Materials Consumed | Section Break | fa fa-table |  |  | ✅ | None | None |
| `supplied_items` | Consumed Items | Table | Subcontracting Receipt Supplied Item |  |  |  | None | None |
| `section_break_46` | None | Section Break | None |  |  |  | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `bill_no` | Bill No | Data | None |  | ✅ |  | None | None |
| `bill_date` | Bill Date | Date | None |  | ✅ |  | None | None |
| `tab_addresses` | Address and Contact | Tab Break | None |  |  |  | None | None |
| `supplier_address` | Select Job Worker Address | Link | Address |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Small Text | Email |  |  | ✅ | None | None |
| `col_break_address` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Select Shipping Address | Link | Address |  |  |  | None | None |
| `shipping_address_display` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `billing_address` | Select Billing Address | Link | Address |  |  |  | None | None |
| `billing_address_display` | Billing Address | Text Editor | None |  |  | ✅ | None | None |
| `tab_additional_costs` | Additional Costs | Tab Break | None |  |  |  | None | None |
| `distribute_additional_costs_based_on` | Distribute Additional Costs Based On  | Select | Qty
Amount |  |  |  | Qty | None |
| `additional_costs` | Additional Costs | Table | Landed Cost Taxes and Charges |  |  |  | None | None |
| `total_additional_costs` | Total Additional Costs | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `tab_other_info` | Other Info | Tab Break | None |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `amended_from` | Amended From | Link | Subcontracting Receipt |  | ✅ | ✅ | None | None |
| `range` | Range | Data | None |  | ✅ |  | None | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | None |
| `order_status_section` | Order Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Completed
Return
Return Issued
Cancelled
Closed | ✅ |  | ✅ | Draft | None |
| `column_break_39` | None | Column Break | None |  |  |  | None | None |
| `per_returned` | % Returned | Percent | None |  |  | ✅ | None | None |
| `subscription_detail` | Auto Repeat Detail | Section Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `printing_settings` | Printing Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `language` | Print Language | Data | None |  |  | ✅ | None | None |
| `instructions` | Instructions | Small Text | None |  |  |  | None | None |
| `column_break_97` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `other_details` | Other Details | HTML | <div class="columnHeading">Other Details</div> |  | ✅ |  | None | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `transporter_info` | Transporter Details | Section Break | fa fa-truck |  |  |  | None | None |
| `transporter_name` | Transporter Name | Data | None |  |  |  | None | None |
| `column_break5` | None | Column Break | None |  |  |  | None | None |
| `lr_no` | Vehicle Number | Data | None |  |  |  | None | None |
| `lr_date` | Vehicle Date | Date | None |  |  |  | None | None |
| `tab_connections` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 17
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_receipt/subcontracting_receipt.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.buying");

erpnext.landed_cost_taxes_and_charges.setup_triggers("Subcontracting Receipt");

frappe.ui.form.on("Subcontracting Receipt", {
	setup: (frm) => {
		frm.ignore_doctypes_on_cancel_all = ["Serial and Batch Bundle"];
		frm.get_field("supplied_items").grid.cannot_add_rows = true;
		frm.get_field("supplied_items").grid.only_sortable();
		frm.trigger("set_queries");

		frm.custom_make_buttons = {
			"Purchase Receipt": "Purchase Receipt",
		};
	},

	on_submit(frm) {
		frm.events.refresh_serial_batch_bundle_field(frm);
	},

	refresh_serial_batch_bundle_field(frm) {
		frappe.route_hooks.after_submit = (frm_obj) => {
			frm_obj.reload_doc();
		};
	},

	refresh: (frm) => {
		frappe.dynamic_link = { doc: frm.doc, fieldname: "supplier", doctype: "Supplier" };

		if (frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Stock Ledger"),
				() => {
					frappe.route_options = {
						voucher_no: frm.doc.name,
						from_date: frm.doc.posting_date,
						to_date: moment(frm.doc.modified).format("YYYY-MM-DD"),
						company: frm.doc.company,
						show_cancelled_entries: frm.doc.docstatus === 2,
					};
					frappe.set_route("query-report", "Stock Ledger");
				},
				__("View")
			);

			frm.add_custom_button(
				__("Accounting Ledger"),
				() => {
					frappe.route_options = {
						voucher_no: frm.doc.name,
						from_date: frm.doc.posting_date,
						to_date: moment(frm.doc.modified).format("YYYY-MM-DD"),
						company: frm.doc.company,
						categorize_by: "Categorize by Voucher (Consolidated)",
						show_cancelled_entries: frm.doc.docstatus === 2,
					};
					frappe.set_route("query-report", "General Ledger");
				},
				__("View")
			);

			if (frm.doc.is_return === 0) {
				frm.add_custom_button(
					__("Purchase Receipt"),
					() => {
						frappe.model.open_mapped_doc({
							method: "erpnext.subcontracting.doctype.subcontracting_receipt.subcontracting_receipt.make_purchase_receipt",
							frm: frm,
							freeze: true,
							freeze_message: __("Creating Purchase Receipt ..."),
						});
					},
					__("Create")
				);
			}
		}

		if (!frm.doc.is_return && frm.doc.docstatus === 1 && frm.doc.per_returned < 100) {
			frm.add_custom_button(
				__("Subcontract Return"),
				() => {
					frappe.model.open_mapped_doc({
						method: "erpnext.subcontracting.doctype.subcontracting_receipt.subcontracting_receipt.make_subcontract_return",
						frm: frm,
					});
				},
				__("Create")
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (frm.doc.docstatus === 0) {
			frm.add_custom_button(
				__("Subcontracting Order"),
				() => {
					if (!frm.doc.supplier) {
						frappe.throw({
							title: __("Mandatory"),
							message: __("Please Select a Supplier"),
						});
					}

					erpnext.utils.map_current_doc({
						method: "erpnext.subcontracting.doctype.subcontracting_order.subcontracting_order.make_subcontracting_receipt",
						source_doctype: "Subcontracting Order",
						target: frm,
						setters: {
							supplier: frm.doc.supplier,
						},
						get_query_filters: {
							docstatus: 1,
							per_received: ["<", 100],
							company: frm.doc.company,
							status: ["!=", "Closed"],
						},
					});
				},
				__("Get Items From")
			);

			frm.fields_dict.supplied_items.grid.update_docfield_property(
				"consumed_qty",
				"read_only",
				frm.doc.__onload && frm.doc.__onload.backflush_based_on === "BOM"
			);
		}

		frm.trigger("setup_quality_inspection");
		frm.trigger("set_route_options_for_new_doc");
	},

	set_warehouse: (frm) => {
		set_warehouse_in_children(frm.doc.items, "warehouse", frm.doc.set_warehouse);
	},

	rejected_warehouse: (frm) => {
		set_warehouse_in_children(frm.doc.items, "rejected_warehouse", frm.doc.rejected_warehouse);
	},

	get_scrap_items: (frm) => {
		frappe.call({
			doc: frm.doc,
			method: "get_scrap_items",
			args: {
				recalculate_rate: true,
			},
			freeze: true,
			freeze_message: __("Getting Scrap Items"),
			callback: (r) => {
				if (!r.exc) {
					frm.refresh();
				}
			},
		});
	},

	set_queries: (frm) => {
		frm.set_query("set_warehouse", () => {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("supplier_address", erpnext.queries.address_query);

		frm.set_query("billing_address", erpnext.queries.company_address_query);

		frm.set_query("shipping_address", () => {
			return erpnext.queries.company_address_query(frm.doc);
		});

		frm.set_query("rejected_warehouse", () => {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("cost_center", (doc) => {
			return {
				filters: {
					company: doc.company,
				},
			};
		});

		frm.set_query("cost_center", "items", (doc) => {
			return {
				filters: {
					company: doc.company,
				},
			};
		});

		frm.set_query("supplier_warehouse", () => {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("warehouse", "items", () => ({
			filters: {
				company: frm.doc.company,
				is_group: 0,
			},
		}));

		frm.set_query("rejected_warehouse", "items", () => ({
			filters: {
				company: frm.doc.company,
				is_group: 0,
			},
		}));

		frm.set_query("expense_account", "items", () => {
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: frm.doc.company },
			};
		});

		frm.set_query("batch_no", "items", (doc, cdt, cdn) => {
			var row = locals[cdt][cdn];
			return {
				filters: {
					item: row.item_code,
				},
			};
		});

		frm.set_query("serial_and_batch_bundle", "items", (doc, cdt, cdn) => {
			return frm.events.get_serial_and_batch_bundle_filters(doc, cdt, cdn);
		});

		frm.set_query("rejected_serial_and_batch_bundle", "items", (doc, cdt, cdn) => {
			return frm.events.get_serial_and_batch_bundle_filters(doc, cdt, cdn);
		});

		frm.set_query("batch_no", "supplied_items", (doc, cdt, cdn) => {
			let row = locals[cdt][cdn];
			let filters = {
				item_code: row.rm_item_code,
				warehouse: doc.supplier_warehouse,
			};

			return {
				query: "erpnext.controllers.queries.get_batch_no",
				filters: filters,
			};
		});

		frm.set_query("serial_and_batch_bundle", "supplied_items", (doc, cdt, cdn) => {
			let row = locals[cdt][cdn];
			return {
				filters: {
					item_code: row.rm_item_code,
					voucher_type: doc.doctype,
					voucher_no: ["in", [doc.name, ""]],
					is_cancelled: 0,
				},
			};
		});
	},

	get_serial_and_batch_bundle_filters: (doc, cdt, cdn) => {
		let row = locals[cdt][cdn];
		return {
			filters: {
				item_code: row.item_code,
				voucher_type: doc.doctype,
				voucher_no: ["in", [doc.name, ""]],
				is_cancelled: 0,
			},
		};
	},

	setup_quality_inspection: (frm) => {
		if (!frm.is_new() && frm.doc.docstatus === 0 && !frm.doc.is_return) {
			let transaction_controller = new erpnext.TransactionController({ frm: frm });
			transaction_controller.setup_quality_inspection();
		}
	},

	set_route_options_for_new_doc: (frm) => {
		let batch_no_field = frm.get_docfield("items", "batch_no");
		if (batch_no_field) {
			batch_no_field.get_route_options_for_new_doc = (row) => {
				return {
					item: row.doc.item_code,
				};
			};
		}

		let item_sbb_field = frm.get_docfield("items", "serial_and_batch_bundle");
		if (item_sbb_field) {
			item_sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.item_code,
					voucher_type: frm.doc.doctype,
				};
			};
		}

		let rejected_item_sbb_field = frm.get_docfield("items", "rejected_serial_and_batch_bundle");
		if (rejected_item_sbb_field) {
			rejected_item_sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.item_code,
					voucher_type: frm.doc.doctype,
				};
			};
		}

		let rm_sbb_field = frm.get_docfield("supplied_items", "serial_and_batch_bundle");
		if (rm_sbb_field) {
			rm_sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.rm_item_code,
					voucher_type: frm.doc.doctype,
				};
			};
		}
	},

	reset_raw_materials_table: (frm) => {
		frm.clear_table("supplied_items");

		frm.call({
			method: "reset_raw_materials",
			doc: frm.doc,
			freeze: true,
			callback: (r) => {
				if (!r.exc) {
					frm.save();
				}
			},
		});
	},
});

frappe.ui.form.on("Landed Cost Taxes and Charges", {
	amount: (frm, cdt, cdn) => {
		set_missing_values(frm);
		frm.events.set_base_amount(frm, cdt, cdn);
	},

	expense_account: (frm, cdt, cdn) => {
		frm.events.set_account_currency(frm, cdt, cdn);
	},

	additional_costs_remove: (frm) => {
		set_missing_values(frm);
	},
});

frappe.ui.form.on("Subcontracting Receipt Item", {
	item_code(frm) {
		set_missing_values(frm);
	},

	qty(frm) {
		set_missing_values(frm);
	},

	rate(frm) {
		set_missing_values(frm);
	},

	items_delete: (frm) => {
		set_missing_values(frm);
	},

	add_serial_batch_bundle(frm, cdt, cdn) {
		let item = locals[cdt][cdn];

		frappe.db.get_value("Item", item.item_code, ["has_batch_no", "has_serial_no"]).then((r) => {
			if (r.message && (r.message.has_batch_no || r.message.has_serial_no)) {
				item.has_serial_no = r.message.has_serial_no;
				item.has_batch_no = r.message.has_batch_no;
				item.type_of_transaction = item.qty > 0 ? "Inward" : "Outward";
				item.is_rejected = false;

				new erpnext.SerialBatchPackageSelector(frm, item, (r) => {
					if (r) {
						let qty = Math.abs(r.total_qty);
						if (frm.doc.is_return) {
							qty = qty * -1;
						}

						let update_values = {
							serial_and_batch_bundle: r.name,
							use_serial_batch_fields: 0,
							qty: qty / flt(item.conversion_factor || 1, precision("conversion_factor", item)),
						};

						if (r.warehouse) {
							update_values["warehouse"] = r.warehouse;
						}

						frappe.model.set_value(item.doctype, item.name, update_values);
					}
				});
			}
		});
	},

	add_serial_batch_for_rejected_qty(frm, cdt, cdn) {
		let item = locals[cdt][cdn];

		frappe.db.get_value("Item", item.item_code, ["has_batch_no", "has_serial_no"]).then((r) => {
			if (r.message && (r.message.has_batch_no || r.message.has_serial_no)) {
				item.has_serial_no = r.message.has_serial_no;
				item.has_batch_no = r.message.has_batch_no;
				item.type_of_transaction = item.rejected_qty > 0 ? "Inward" : "Outward";
				item.is_rejected = true;

				new erpnext.SerialBatchPackageSelector(frm, item, (r) => {
					if (r) {
						let qty = Math.abs(r.total_qty);
						if (frm.doc.is_return) {
							qty = qty * -1;
						}

						let update_values = {
							serial_and_batch_bundle: r.name,
							use_serial_batch_fields: 0,
							rejected_qty:
								qty / flt(item.conversion_factor || 1, precision("conversion_factor", item)),
						};

						if (r.warehouse) {
							update_values["rejected_warehouse"] = r.warehouse;
						}

						frappe.model.set_value(item.doctype, item.name, update_values);
					}
				});
			}
		});
	},
});

frappe.ui.form.on("Subcontracting Receipt Supplied Item", {
	consumed_qty(frm) {
		set_missing_values(frm);
	},

	add_serial_batch_bundle(frm, cdt, cdn) {
		let item = locals[cdt][cdn];

		item.item_code = item.rm_item_code;
		item.qty = item.consumed_qty;
		item.warehouse = frm.doc.supplier_warehouse;
		frappe.db.get_value("Item", item.item_code, ["has_batch_no", "has_serial_no"]).then((r) => {
			if (r.message && (r.message.has_batch_no || r.message.has_serial_no)) {
				item.has_serial_no = r.message.has_serial_no;
				item.has_batch_no = r.message.has_batch_no;
				item.type_of_transaction = item.qty > 0 ? "Outward" : "Inward";
				item.is_rejected = false;

				new erpnext.SerialBatchPackageSelector(frm, item, (r) => {
					if (r) {
						let qty = Math.abs(r.total_qty);
						if (frm.doc.is_return) {
							qty = qty * -1;
						}

						let update_values = {
							serial_and_batch_bundle: r.name,
							use_serial_batch_fields: 0,
							consumed_qty:
								qty / flt(item.conversion_factor || 1, precision("conversion_factor", item)),
						};

						frappe.model.set_value(item.doctype, item.name, update_values);
					}
				});
			}
		});
	},
});

let set_warehouse_in_children = (child_table, warehouse_field, warehouse) => {
	let transaction_controller = new erpnext.TransactionController();
	transaction_controller.autofill_warehouse(child_table, warehouse_field, warehouse);
};

let set_missing_values = (frm) => {
	frappe.call({
		doc: frm.doc,
		method: "set_missing_values",
		callback: (r) => {
			if (!r.exc) frm.refresh();
		},
	});
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
