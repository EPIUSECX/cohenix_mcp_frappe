# Master Control Plan: `Subcontracting Order`

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
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | SC-ORD-.YYYY.- | ✅ |  |  | None | None |
| `purchase_order` | Subcontracting Purchase Order | Link | Purchase Order | ✅ |  |  | None | None |
| `supplier` | Job Worker | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Job Worker Name | Data | None | ✅ |  | ✅ | None | None |
| `supplier_warehouse` | Job Worker Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `schedule_date` | Required By | Date | None |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Subcontracting Order |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `section_break_24` | None | Section Break | None |  |  |  | None | None |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Set Target Warehouse | Link | Warehouse |  |  |  | None | Sets 'Warehouse' in each row of the Items table. |
| `items` | Items | Table | Subcontracting Order Item | ✅ |  |  | None | None |
| `section_break_32` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `column_break_29` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `service_items_section` | Service Items | Section Break | None |  |  |  | None | None |
| `service_items` | Service Items | Table | Subcontracting Order Service Item | ✅ |  | ✅ | None | None |
| `raw_materials_supplied_section` | Raw Materials Supplied | Section Break | None |  |  |  | None | None |
| `set_reserve_warehouse` | Set Reserve Warehouse | Link | Warehouse |  |  |  | None | Sets 'Reserve Warehouse' in each row of the Supplied Items table. |
| `supplied_items` | Supplied Items | Table | Subcontracting Order Supplied Item |  |  | ✅ | None | None |
| `tab_address_and_contact` | Address and Contact | Tab Break | None |  |  |  | None | None |
| `supplier_address` | Job Worker Address | Link | Address |  |  |  | None | None |
| `address_display` | Job Worker Address Details | Text Editor | None |  |  | ✅ | None | None |
| `contact_person` | Job Worker Contact | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact Name | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Contact Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Small Text | Email |  |  | ✅ | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Company Shipping Address | Link | Address |  |  |  | None | None |
| `shipping_address_display` | Shipping Address Details | Text Editor | None |  |  | ✅ | None | None |
| `billing_address` | Company Billing Address | Link | Address |  |  |  | None | None |
| `billing_address_display` | Billing Address Details | Text Editor | None |  |  | ✅ | None | None |
| `tab_additional_costs` | Additional Costs | Tab Break | None |  |  |  | None | None |
| `distribute_additional_costs_based_on` | Distribute Additional Costs Based On  | Select | Qty
Amount |  |  |  | Qty | None |
| `additional_costs` | Additional Costs | Table | Landed Cost Taxes and Charges |  |  |  | None | None |
| `total_additional_costs` | Total Additional Costs | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `tab_other_info` | Other Info | Tab Break | None |  |  |  | None | None |
| `order_status_section` | Order Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Open
Partially Received
Completed
Material Transferred
Partial Material Transferred
Cancelled
Closed | ✅ |  | ✅ | Draft | None |
| `column_break_39` | None | Column Break | None |  |  |  | None | None |
| `per_received` | % Received | Percent | None |  |  | ✅ | None | None |
| `printing_settings_section` | Printing Settings | Section Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `column_break_43` | None | Column Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `tab_connections` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 15
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_order/subcontracting_order.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.buying");

erpnext.landed_cost_taxes_and_charges.setup_triggers("Subcontracting Order");

// client script for Subcontracting Order Item is not necessarily required as the server side code will do everything that is necessary.
// this is just so that the user does not get potentially confused
frappe.ui.form.on("Subcontracting Order Item", {
	qty(frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		frappe.model.set_value(cdt, cdn, "amount", row.qty * row.rate);
		const service_item = frm.doc.service_items[row.idx - 1];
		frappe.model.set_value(
			service_item.doctype,
			service_item.name,
			"qty",
			row.qty * row.subcontracting_conversion_factor
		);
		frappe.model.set_value(service_item.doctype, service_item.name, "fg_item_qty", row.qty);
		frappe.model.set_value(
			service_item.doctype,
			service_item.name,
			"amount",
			row.qty * row.subcontracting_conversion_factor * service_item.rate
		);
	},
	before_items_remove(frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		frm.toggle_enable(["service_items"], true);
		frm.get_field("service_items").grid.grid_rows[row.idx - 1].remove();
		frm.toggle_enable(["service_items"], false);
	},
});

frappe.ui.form.on("Subcontracting Order", {
	setup: (frm) => {
		frm.get_field("items").grid.cannot_add_rows = true;
		frm.trigger("set_queries");

		frm.set_indicator_formatter("item_code", (doc) => (doc.qty <= doc.received_qty ? "green" : "orange"));

		frm.set_query("supplier_warehouse", () => {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("purchase_order", () => {
			return {
				filters: {
					docstatus: 1,
					is_subcontracted: 1,
					is_old_subcontracting_flow: 0,
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

		frm.set_query("set_warehouse", () => {
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

		frm.set_query("expense_account", "items", () => ({
			query: "erpnext.controllers.queries.get_expense_account",
			filters: {
				company: frm.doc.company,
			},
		}));

		frm.set_query("bom", "items", (doc, cdt, cdn) => {
			let d = locals[cdt][cdn];
			return {
				filters: {
					item: d.item_code,
					is_active: 1,
					docstatus: 1,
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("set_reserve_warehouse", () => {
			return {
				filters: {
					company: frm.doc.company,
					name: ["!=", frm.doc.supplier_warehouse],
					is_group: 0,
				},
			};
		});
	},

	set_queries: (frm) => {
		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("supplier_address", erpnext.queries.address_query);

		frm.set_query("billing_address", erpnext.queries.company_address_query);

		frm.set_query("shipping_address", () => {
			return erpnext.queries.company_address_query(frm.doc);
		});
	},

	onload: (frm) => {
		if (!frm.doc.transaction_date) {
			frm.set_value("transaction_date", frappe.datetime.get_today());
		}
	},

	purchase_order: (frm) => {
		frm.set_value("service_items", null);
		frm.set_value("items", null);
		frm.set_value("supplied_items", null);

		if (frm.doc.purchase_order) {
			erpnext.utils.map_current_doc({
				method: "erpnext.buying.doctype.purchase_order.purchase_order.make_subcontracting_order",
				source_name: frm.doc.purchase_order,
				target_doc: frm,
				freeze: true,
				freeze_message: __("Mapping Subcontracting Order ..."),
			});
		}
	},

	refresh: function (frm) {
		frappe.dynamic_link = { doc: frm.doc, fieldname: "supplier", doctype: "Supplier" };

		if (frm.doc.docstatus == 1 && frm.has_perm("submit")) {
			if (frm.doc.status == "Closed") {
				frm.add_custom_button(
					__("Re-open"),
					() => frm.events.update_subcontracting_order_status(frm),
					__("Status")
				);
			} else if (flt(frm.doc.per_received, 2) < 100) {
				frm.add_custom_button(
					__("Close"),
					() => frm.events.update_subcontracting_order_status(frm, "Closed"),
					__("Status")
				);
			}
		}

		frm.trigger("get_materials_from_supplier");
	},

	update_subcontracting_order_status(frm, status) {
		frappe.call({
			method: "erpnext.subcontracting.doctype.subcontracting_order.subcontracting_order.update_subcontracting_order_status",
			args: {
				sco: frm.doc.name,
				status: status,
			},
			callback: function (r) {
				if (!r.exc) {
					frm.reload_doc();
				}
			},
		});
	},

	get_materials_from_supplier: function (frm) {
		let sco_rm_details = [];

		if (frm.doc.status != "Closed" && frm.doc.supplied_items) {
			frm.doc.supplied_items.forEach((d) => {
				if (d.total_supplied_qty > 0 && d.total_supplied_qty != d.consumed_qty) {
					sco_rm_details.push(d.name);
				}
			});
		}

		if (sco_rm_details && sco_rm_details.length) {
			frm.add_custom_button(
				__("Return of Components"),
				() => {
					frm.call({
						method: "erpnext.controllers.subcontracting_controller.get_materials_from_supplier",
						freeze: true,
						freeze_message: __("Creating Stock Entry"),
						args: {
							subcontract_order: frm.doc.name,
							rm_details: sco_rm_details,
							order_doctype: cur_frm.doc.doctype,
						},
						callback: function (r) {
							if (r && r.message) {
								const doc = frappe.model.sync(r.message);
								frappe.set_route("Form", doc[0].doctype, doc[0].name);
							}
						},
					});
				},
				__("Create")
			);
		}
	},
});

frappe.ui.form.on("Landed Cost Taxes and Charges", {
	amount: function (frm, cdt, cdn) {
		frm.events.set_base_amount(frm, cdt, cdn);
	},

	expense_account: function (frm, cdt, cdn) {
		frm.events.set_account_currency(frm, cdt, cdn);
	},
});

erpnext.buying.SubcontractingOrderController = class SubcontractingOrderController {
	setup() {
		this.frm.custom_make_buttons = {
			"Subcontracting Receipt": "Subcontracting Receipt",
			"Stock Entry": "Material to Supplier",
		};
	}

	refresh(doc) {
		var me = this;

		if (doc.docstatus == 1) {
			if (!["Closed", "Completed"].includes(doc.status)) {
				if (flt(doc.per_received) < 100) {
					this.frm.add_custom_button(
						__("Subcontracting Receipt"),
						this.make_subcontracting_receipt,
						__("Create")
					);
					if (me.has_unsupplied_items()) {
						this.frm.add_custom_button(
							__("Material to Supplier"),
							this.make_stock_entry,
							__("Transfer")
						);
					}
				}
				if (flt(doc.per_received) < 100 && me.has_unsupplied_items()) {
					this.frm.page.set_inner_btn_group_as_primary(__("Transfer"));
				} else {
					this.frm.page.set_inner_btn_group_as_primary(__("Create"));
				}
			}
		}
	}

	items_add(doc, cdt, cdn) {
		if (doc.set_warehouse) {
			var row = frappe.get_doc(cdt, cdn);
			row.warehouse = doc.set_warehouse;
		}
	}

	set_warehouse(doc) {
		this.set_warehouse_in_children(doc.items, "warehouse", doc.set_warehouse);
	}

	set_reserve_warehouse(doc) {
		this.set_warehouse_in_children(doc.supplied_items, "reserve_warehouse", doc.set_reserve_warehouse);
	}

	set_warehouse_in_children(child_table, warehouse_field, warehouse) {
		let transaction_controller = new erpnext.TransactionController();
		transaction_controller.autofill_warehouse(child_table, warehouse_field, warehouse);
	}

	has_unsupplied_items() {
		let over_transfer_allowance = this.frm.doc.__onload.over_transfer_allowance;
		return this.frm.doc["supplied_items"].some((item) => {
			let required_qty = item.required_qty + (item.required_qty * over_transfer_allowance) / 100;
			return required_qty > item.supplied_qty - item.returned_qty;
		});
	}

	make_subcontracting_receipt() {
		frappe.model.open_mapped_doc({
			method: "erpnext.subcontracting.doctype.subcontracting_order.subcontracting_order.make_subcontracting_receipt",
			frm: cur_frm,
			freeze_message: __("Creating Subcontracting Receipt ..."),
		});
	}

	make_stock_entry() {
		frappe.call({
			method: "erpnext.controllers.subcontracting_controller.make_rm_stock_entry",
			args: {
				subcontract_order: cur_frm.doc.name,
				order_doctype: cur_frm.doc.doctype,
			},
			callback: (r) => {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	}
};

extend_cscript(cur_frm.cscript, new erpnext.buying.SubcontractingOrderController({ frm: cur_frm }));

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Subcontract Order Summary` | Script Report | Buying |
| `Subcontracted Raw Materials To Be Transferred` | Script Report | Buying |
| `Subcontracted Item To Be Received` | Script Report | Buying |



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
