# Master Control Plan: `Asset Repair`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | ACC-ASR-.YYYY.- | ✅ |  |  | None | None |
| `asset` | Asset | Link | Asset | ✅ |  |  | None | None |
| `asset_name` | Asset Name | Read Only | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `repair_status` | Repair Status | Select | Pending
Completed
Cancelled |  |  |  | Pending | None |
| `failure_date` | Failure Date | Datetime | None | ✅ |  |  | None | None |
| `completion_date` | Completion Date | Datetime | None |  |  |  | None | None |
| `downtime` | Downtime | Data | None |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Asset Repair |  |  | ✅ | None | None |
| `section_break_9` | Description | Section Break | None |  |  |  | None | None |
| `description` | Error Description | Long Text | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `actions_performed` | Actions performed | Long Text | None |  |  |  | None | None |
| `accounting_details` | Repair Purchase Invoices | Section Break | None |  |  |  | None | None |
| `invoices` | None | Table | Asset Repair Purchase Invoice |  |  |  | None | None |
| `section_break_muyc` | None | Section Break | None |  |  |  | None | None |
| `column_break_ajbh` | None | Column Break | None |  |  |  | None | None |
| `column_break_hkem` | None | Column Break | None |  |  |  | None | None |
| `repair_cost` | Repair Cost | Currency | None |  |  | ✅ | 0 | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `stock_consumption_details_section` | Consumed Stock Items | Section Break | None |  |  |  | None | None |
| `stock_items` | Stock Items | Table | Asset Repair Consumed Item |  |  |  | None | None |
| `section_break_ltbb` | None | Section Break | None |  |  |  | None | None |
| `column_break_ewor` | None | Column Break | None |  |  |  | None | None |
| `column_break_ceuc` | None | Column Break | None |  |  |  | None | None |
| `consumed_items_cost` | Consumed Items Cost | Currency | None |  |  |  | None | None |
| `capitalizations_section` | Totals | Section Break | None |  |  |  | None | None |
| `column_break_spre` | None | Column Break | None |  |  |  | None | None |
| `capitalize_repair_cost` | Capitalize Repair Cost | Check | None |  |  |  | 0 | None |
| `increase_in_asset_life` | Increase In Asset Life(Months) | Int | None |  |  |  | None | None |
| `column_break_xebe` | None | Column Break | None |  |  |  | None | None |
| `total_repair_cost` | Total Repair Cost | Currency | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_repair/asset_repair.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Asset Repair", {
	setup: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Serial and Batch Bundle"];

		frm.fields_dict.cost_center.get_query = function (doc) {
			return {
				filters: {
					is_group: 0,
					company: doc.company,
				},
			};
		};

		frm.fields_dict.project.get_query = function (doc) {
			return {
				filters: {
					company: doc.company,
				},
			};
		};

		frm.set_query("asset", function () {
			return {
				filters: {
					company: frm.doc.company,
					docstatus: 1,
				},
			};
		});

		frm.set_query("purchase_invoice", "invoices", function () {
			return {
				query: "erpnext.assets.doctype.asset_repair.asset_repair.get_purchase_invoice",
				filters: {
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("expense_account", "invoices", function (doc, cdt, cdn) {
			let row = locals[cdt][cdn];
			return {
				query: "erpnext.assets.doctype.asset_repair.asset_repair.get_expense_accounts",
				filters: {
					purchase_invoice: row.purchase_invoice,
				},
			};
		});

		frm.set_query("warehouse", "stock_items", function () {
			return {
				filters: {
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("serial_and_batch_bundle", "stock_items", (doc, cdt, cdn) => {
			let row = locals[cdt][cdn];
			return {
				filters: {
					item_code: row.item_code,
					voucher_type: doc.doctype,
					voucher_no: ["in", [doc.name, ""]],
					is_cancelled: 0,
				},
			};
		});
	},

	refresh: function (frm) {
		if (frm.doc.docstatus) {
			frm.add_custom_button(__("View General Ledger"), function () {
				frappe.route_options = {
					voucher_no: frm.doc.name,
				};
				frappe.set_route("query-report", "General Ledger");
			});
		}

		let sbb_field = frm.get_docfield("stock_items", "serial_and_batch_bundle");
		if (sbb_field) {
			sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.item_code,
					voucher_type: frm.doc.doctype,
				};
			};
		}
	},

	repair_status: (frm) => {
		if (frm.doc.completion_date && frm.doc.repair_status == "Completed") {
			frappe.call({
				method: "erpnext.assets.doctype.asset_repair.asset_repair.get_downtime",
				args: {
					failure_date: frm.doc.failure_date,
					completion_date: frm.doc.completion_date,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("downtime", r.message + " Hrs");
					}
				},
			});
		}

		if (frm.doc.repair_status == "Completed" && !frm.doc.completion_date) {
			frm.set_value("completion_date", frappe.datetime.now_datetime());
		}
	},

	stock_items_on_form_rendered() {
		erpnext.setup_serial_or_batch_no();
	},

	stock_consumption: function (frm) {
		if (!frm.doc.stock_consumption) {
			frm.clear_table("stock_items");
			frm.refresh_field("stock_items");
		}
	},

	purchase_invoice: function (frm) {
		if (frm.doc.purchase_invoice) {
			frappe.call({
				method: "frappe.client.get_value",
				args: {
					doctype: "Purchase Invoice",
					fieldname: "base_net_total",
					filters: { name: frm.doc.purchase_invoice },
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("repair_cost", r.message.base_net_total);
					}
				},
			});
		} else {
			frm.set_value("repair_cost", 0);
		}
	},
});

frappe.ui.form.on("Asset Repair Consumed Item", {
	warehouse: function (frm, cdt, cdn) {
		var item = locals[cdt][cdn];

		if (!item.item_code) {
			frappe.msgprint(__("Please select an item code before setting the warehouse."));
			frappe.model.set_value(cdt, cdn, "warehouse", "");
			return;
		}

		let item_args = {
			item_code: item.item_code,
			warehouse: item.warehouse,
			qty: item.consumed_quantity,
			serial_no: item.serial_no,
			company: frm.doc.company,
		};

		frappe.call({
			method: "erpnext.stock.utils.get_incoming_rate",
			args: {
				args: item_args,
			},
			callback: function (r) {
				frappe.model.set_value(cdt, cdn, "valuation_rate", r.message);
			},
		});
	},

	consumed_quantity: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		frappe.model.set_value(cdt, cdn, "total_value", row.consumed_quantity * row.valuation_rate);
	},

	pick_serial_and_batch(frm, cdt, cdn) {
		let item = locals[cdt][cdn];
		let doc = frm.doc;

		frappe.db.get_value("Item", item.item_code, ["has_batch_no", "has_serial_no"]).then((r) => {
			if (r.message && (r.message.has_batch_no || r.message.has_serial_no)) {
				item.has_serial_no = r.message.has_serial_no;
				item.has_batch_no = r.message.has_batch_no;
				item.qty = item.consumed_quantity;
				item.type_of_transaction = item.consumed_quantity > 0 ? "Outward" : "Inward";

				item.title = item.has_serial_no ? __("Select Serial No") : __("Select Batch No");

				if (item.has_serial_no && item.has_batch_no) {
					item.title = __("Select Serial and Batch");
				}
				frm.doc.posting_date = frappe.datetime.get_today();
				frm.doc.posting_time = frappe.datetime.now_time();

				new erpnext.SerialBatchPackageSelector(frm, item, (r) => {
					if (r) {
						frappe.model.set_value(item.doctype, item.name, {
							serial_and_batch_bundle: r.name,
							use_serial_batch_fields: 0,
							valuation_rate: r.avg_rate,
							consumed_quantity: Math.abs(r.total_qty),
						});
					}
				});
			}
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
