# Master Control Plan: `Asset`

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
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | ACC-ASS-.YYYY.- |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Read Only | None |  |  |  | None | None |
| `asset_name` | Asset Name | Data | None | ✅ |  |  | None | None |
| `asset_category` | Asset Category | Link | Asset Category |  |  | ✅ | None | None |
| `location` | Location | Link | Location | ✅ |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Submitted
Partially Depreciated
Fully Depreciated
Sold
Scrapped
In Maintenance
Out of Order
Issue
Receipt
Capitalized
Work In Progress |  |  | ✅ | Draft | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `asset_owner` | Asset Owner | Select | 
Company
Supplier
Customer |  |  |  | Company | None |
| `asset_owner_company` | Asset Owner Company | Link | Company |  |  |  | None | None |
| `is_existing_asset` | Is Existing Asset | Check | None |  |  |  | 0 | None |
| `is_composite_asset` | Is Composite Asset | Check | None |  |  |  | 0 | None |
| `is_composite_component` | Is Composite Component | Check | None |  |  |  | 0 | None |
| `purchase_details_section` | Purchase Details | Section Break | None |  |  |  | None | None |
| `purchase_receipt` | Purchase Receipt | Link | Purchase Receipt |  |  |  | None | None |
| `purchase_receipt_item` | Purchase Receipt Item | Data | None |  | ✅ |  | None | None |
| `purchase_invoice` | Purchase Invoice | Link | Purchase Invoice |  |  |  | None | None |
| `purchase_invoice_item` | Purchase Invoice Item | Data | None |  | ✅ |  | None | None |
| `purchase_date` | Purchase Date | Date | None | ✅ |  |  | None | None |
| `available_for_use_date` | Available-for-use Date | Date | None |  |  |  | None | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `gross_purchase_amount` | Net Purchase Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `purchase_amount` | Purchase Amount | Currency | None |  | ✅ | ✅ | None | None |
| `asset_quantity` | Asset Quantity | Int | None |  |  |  | 1 | None |
| `additional_asset_cost` | Additional Asset Cost | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `total_asset_cost` | Total Asset Cost | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `disposal_date` | Disposal Date | Date | None |  |  | ✅ | None | None |
| `depreciation_tab` | Depreciation | Tab Break | None |  |  |  | None | None |
| `calculate_depreciation` | Calculate Depreciation | Check | None |  |  |  | 0 | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `opening_accumulated_depreciation` | Opening Accumulated Depreciation | Currency | Company:company:default_currency |  |  |  | None | None |
| `opening_number_of_booked_depreciations` | Opening Number of Booked Depreciations | Int | None |  |  |  | None | None |
| `is_fully_depreciated` | Is Fully Depreciated | Check | None |  |  |  | 0 | None |
| `section_break_36` | Finance Books | Section Break | None |  |  |  | None | None |
| `finance_books` | None | Table | Asset Finance Book |  |  |  | None | None |
| `section_break_33` | None | Section Break | None |  | ✅ |  | None | None |
| `depreciation_method` | Depreciation Method | Select | 
Straight Line
Double Declining Balance
Manual |  |  |  | None | None |
| `value_after_depreciation` | Value After Depreciation | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `total_number_of_depreciations` | Total Number of Depreciations | Int | None |  |  |  | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `frequency_of_depreciation` | Frequency of Depreciation (Months) | Int | None |  |  |  | None | None |
| `next_depreciation_date` | Next Depreciation Date | Date | None |  |  |  | None | None |
| `depreciation_schedule_sb` | Depreciation Schedule | Section Break | None |  |  |  | None | None |
| `depreciation_schedule_view` | Depreciation Schedule View | HTML | None |  | ✅ |  | None | None |
| `insurance_details_tab` | Insurance | Tab Break | None |  |  |  | None | None |
| `policy_number` | Policy number | Data | None |  |  |  | None | None |
| `insurer` | Insurer | Data | None |  |  |  | None | None |
| `insured_value` | Insured value | Data | None |  |  |  | None | None |
| `column_break_48` | None | Column Break | None |  |  |  | None | None |
| `insurance_start_date` | Insurance Start Date | Date | None |  |  |  | None | None |
| `insurance_end_date` | Insurance End Date | Date | None |  |  |  | None | None |
| `comprehensive_insurance` | Comprehensive Insurance | Data | None |  |  |  | None | None |
| `other_info_tab` | Other Info | Tab Break | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `section_break_jtou` | Additional Info | Section Break | None |  |  |  | None | None |
| `custodian` | Custodian | Link | Employee |  |  |  | None | None |
| `default_finance_book` | Default Finance Book | Link | Finance Book |  | ✅ | ✅ | None | None |
| `depr_entry_posting_status` | Depreciation Entry Posting Status | Select | 
Successful
Failed |  | ✅ | ✅ | None | None |
| `booked_fixed_asset` | Booked Fixed Asset | Check | None |  | ✅ | ✅ | 0 | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `split_from` | Split From | Link | Asset |  |  | ✅ | None | None |
| `journal_entry_for_scrap` | Journal Entry for Scrap | Link | Journal Entry |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Asset |  |  | ✅ | None | None |
| `maintenance_required` | Maintenance Required | Check | None |  |  |  | 0 | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 16
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset/asset.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.asset");
frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Asset", {
	onload: function (frm) {
		frm.set_query("item_code", function () {
			return {
				filters: {
					is_fixed_asset: 1,
					is_stock_item: 0,
				},
			};
		});

		frm.set_query("warehouse", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});

		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	setup: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Journal Entry"];

		frm.make_methods = {
			"Asset Movement": () => {
				frappe.call({
					method: "erpnext.assets.doctype.asset.asset.make_asset_movement",
					freeze: true,
					args: {
						assets: [{ name: frm.doc.name }],
					},
					callback: function (r) {
						if (r.message) {
							var doc = frappe.model.sync(r.message)[0];
							frappe.set_route("Form", doc.doctype, doc.name);
						}
					},
				});
			},
		};

		frm.set_query("purchase_receipt", (doc) => {
			return {
				query: "erpnext.controllers.queries.get_purchase_receipts",
				filters: { item_code: doc.item_code },
			};
		});
		frm.set_query("purchase_invoice", (doc) => {
			return {
				query: "erpnext.controllers.queries.get_purchase_invoices",
				filters: { item_code: doc.item_code },
			};
		});

		if (frm.doc.docstatus == 1) {
			frm.custom_make_buttons = {
				"Asset Capitalization": "Asset Capitalization",
			};
		}
	},

	refresh: function (frm) {
		frappe.ui.form.trigger("Asset", "is_existing_asset");
		frm.toggle_display("next_depreciation_date", frm.doc.docstatus < 1);

		if (frm.doc.docstatus == 1) {
			if (["Submitted", "Partially Depreciated", "Fully Depreciated"].includes(frm.doc.status)) {
				frm.add_custom_button(
					__("Transfer Asset"),
					function () {
						erpnext.asset.transfer_asset(frm);
					},
					__("Manage")
				);

				frm.add_custom_button(
					__("Scrap Asset"),
					function () {
						erpnext.asset.scrap_asset(frm);
					},
					__("Manage")
				);

				frm.add_custom_button(
					__("Sell Asset"),
					function () {
						frm.trigger("make_sales_invoice");
					},
					__("Manage")
				);

				frm.add_custom_button(
					__("Repair Asset"),
					function () {
						frm.trigger("create_asset_repair");
					},
					__("Manage")
				);

				frm.add_custom_button(
					__("Split Asset"),
					function () {
						frm.trigger("split_asset");
					},
					__("Manage")
				);
			} else if (frm.doc.status == "Scrapped") {
				frm.add_custom_button(__("Restore Asset"), function () {
					erpnext.asset.restore_asset(frm);
				}).addClass("btn-primary");
			}

			if (frm.doc.maintenance_required && !frm.doc.maintenance_schedule) {
				frm.add_custom_button(
					__("Maintain Asset"),
					function () {
						frm.trigger("create_asset_maintenance");
					},
					__("Manage")
				);
			}

			if (["Submitted", "Partially Depreciated"].includes(frm.doc.status)) {
				frm.add_custom_button(
					__("Adjust Asset Value"),
					function () {
						frm.trigger("create_asset_value_adjustment");
					},
					__("Manage")
				);
			}

			if (!frm.doc.calculate_depreciation) {
				frm.add_custom_button(
					__("Create Depreciation Entry"),
					function () {
						frm.trigger("make_journal_entry");
					},
					__("Manage")
				);
			}

			if (frm.doc.purchase_receipt || !frm.doc.is_existing_asset) {
				frm.add_custom_button(
					__("View General Ledger"),
					function () {
						frappe.route_options = {
							voucher_no: frm.doc.name,
							from_date: frm.doc.available_for_use_date,
							to_date: frm.doc.available_for_use_date,
							company: frm.doc.company,
						};
						frappe.set_route("query-report", "General Ledger");
					},
					__("Manage")
				);
			}

			if (frm.doc.depr_entry_posting_status === "Failed") {
				frm.trigger("set_depr_posting_failure_alert");
			}

			frm.trigger("setup_chart_and_depr_schedule_view");
		}

		frm.trigger("toggle_reference_doc");

		if (frm.doc.docstatus == 0) {
			frm.toggle_reqd("finance_books", frm.doc.calculate_depreciation);

			if (frm.doc.is_composite_asset) {
				frappe.call({
					method: "erpnext.assets.doctype.asset.asset.has_active_capitalization",
					args: {
						asset: frm.doc.name,
					},
					callback: function (r) {
						if (!r.message) {
							$(".primary-action").prop("hidden", true);
							$(".form-message").text("Capitalize this asset to confirm");

							frm.add_custom_button(__("Capitalize Asset"), function () {
								frm.trigger("create_asset_capitalization");
							});
						}
					},
				});
			}
		}
	},

	set_depr_posting_failure_alert: function (frm) {
		const alert = `
			<div class="row">
				<div class="col-xs-12 col-sm-6">
					<span class="indicator whitespace-nowrap red">
						<span>${__("Failed to post depreciation entries")}</span>
					</span>
				</div>
			</div>`;

		frm.dashboard.set_headline_alert(alert);
	},

	toggle_reference_doc: function (frm) {
		if (frm.doc.purchase_receipt && frm.doc.purchase_invoice && frm.doc.docstatus === 1) {
			frm.set_df_property("purchase_invoice", "read_only", 1);
			frm.set_df_property("purchase_receipt", "read_only", 1);
		} else if (frm.doc.is_existing_asset || frm.doc.is_composite_asset) {
			frm.toggle_reqd("purchase_receipt", 0);
			frm.toggle_reqd("purchase_invoice", 0);
		} else if (frm.doc.purchase_receipt) {
			// if purchase receipt link is set then set PI disabled
			frm.toggle_reqd("purchase_invoice", 0);
			frm.set_df_property("purchase_invoice", "read_only", 1);
		} else if (frm.doc.purchase_invoice) {
			// if purchase invoice link is set then set PR disabled
			frm.toggle_reqd("purchase_receipt", 0);
			frm.set_df_property("purchase_receipt", "read_only", 1);
		} else {
			frm.toggle_reqd("purchase_receipt", 1);
			frm.set_df_property("purchase_receipt", "read_only", 0);
			frm.toggle_reqd("purchase_invoice", 1);
			frm.set_df_property("purchase_invoice", "read_only", 0);
		}
	},

	make_journal_entry: function (frm) {
		frappe.call({
			method: "erpnext.assets.doctype.asset.asset.make_journal_entry",
			args: {
				asset_name: frm.doc.name,
			},
			callback: function (r) {
				if (r.message) {
					var doclist = frappe.model.sync(r.message);
					frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				}
			},
		});
	},

	render_depreciation_schedule_view: function (frm, asset_depr_schedule_doc) {
		let wrapper = $(frm.fields_dict["depreciation_schedule_view"].wrapper).empty();

		let data = [];

		asset_depr_schedule_doc.depreciation_schedule.forEach((sch) => {
			const row = [
				sch["idx"],
				frappe.format(sch["schedule_date"], { fieldtype: "Date" }),
				frappe.format(sch["depreciation_amount"], { fieldtype: "Currency" }),
				frappe.format(sch["accumulated_depreciation_amount"], { fieldtype: "Currency" }),
				sch["journal_entry"] || "",
			];

			if (asset_depr_schedule_doc.shift_based) {
				row.push(sch["shift"]);
			}

			data.push(row);
		});

		let columns = [
			{ name: __("No."), editable: false, resizable: false, format: (value) => value, width: 60 },
			{ name: __("Schedule Date"), editable: false, resizable: false, width: 270 },
			{ name: __("Depreciation Amount"), editable: false, resizable: false, width: 164 },
			{ name: __("Accumulated Depreciation Amount"), editable: false, resizable: false, width: 164 },
		];

		if (asset_depr_schedule_doc.shift_based) {
			columns.push({
				name: __("Journal Entry"),
				editable: false,
				resizable: false,
				format: (value) => `<a href="/app/journal-entry/${value}">${value}</a>`,
				width: 245,
			});
			columns.push({ name: __("Shift"), editable: false, resizable: false, width: 59 });
		} else {
			columns.push({
				name: __("Journal Entry"),
				editable: false,
				resizable: false,
				format: (value) => `<a href="/app/journal-entry/${value}">${value}</a>`,
				width: 304,
			});
		}

		let datatable = new frappe.DataTable(wrapper.get(0), {
			columns: columns,
			data: data,
			layout: "fluid",
			serialNoColumn: false,
			checkboxColumn: true,
			cellHeight: 35,
		});

		datatable.style.setStyle(`.dt-scrollable`, {
			"font-size": "0.75rem",
			"margin-bottom": "1rem",
			"margin-left": "0.35rem",
			"margin-right": "0.35rem",
		});
		datatable.style.setStyle(`.dt-header`, { "margin-left": "0.35rem", "margin-right": "0.35rem" });
		datatable.style.setStyle(`.dt-cell--header .dt-cell__content`, {
			color: "var(--gray-600)",
			"font-size": "var(--text-sm)",
		});
		datatable.style.setStyle(`.dt-cell`, { color: "var(--text-color)" });
		datatable.style.setStyle(`.dt-cell--col-1`, { "text-align": "center" });
		datatable.style.setStyle(`.dt-cell--col-2`, { "font-weight": 600 });
		datatable.style.setStyle(`.dt-cell--col-3`, { "font-weight": 600 });
	},

	setup_chart_and_depr_schedule_view: async function (frm) {
		if (frm.doc.finance_books.length > 1) {
			return;
		}

		var x_intervals = [frappe.format(frm.doc.purchase_date, { fieldtype: "Date" })];
		var asset_values = [frm.doc.gross_purchase_amount];

		if (frm.doc.calculate_depreciation) {
			if (frm.doc.opening_accumulated_depreciation) {
				var depreciation_date = frappe.datetime.add_months(
					frm.doc.finance_books[0].depreciation_start_date,
					-1 * frm.doc.finance_books[0].frequency_of_depreciation
				);
				x_intervals.push(frappe.format(depreciation_date, { fieldtype: "Date" }));
				asset_values.push(
					flt(
						frm.doc.gross_purchase_amount - frm.doc.opening_accumulated_depreciation,
						precision("gross_purchase_amount")
					)
				);
			}

			let asset_depr_schedule_doc = (
				await frappe.call(
					"erpnext.assets.doctype.asset_depreciation_schedule.asset_depreciation_schedule.get_asset_depr_schedule_doc",
					{
						asset_name: frm.doc.name,
						status: "Active",
						finance_book: frm.doc.finance_books[0].finance_book || null,
					}
				)
			).message;

			$.each(asset_depr_schedule_doc.depreciation_schedule || [], function (i, v) {
				x_intervals.push(frappe.format(v.schedule_date, { fieldtype: "Date" }));
				var asset_value = flt(
					frm.doc.gross_purchase_amount - v.accumulated_depreciation_amount,
					precision("gross_purchase_amount")
				);
				if (v.journal_entry) {
					asset_values.push(asset_value);
				} else {
					if (["Scrapped", "Sold"].includes(frm.doc.status)) {
						asset_values.push(null);
					} else {
						asset_values.push(asset_value);
					}
				}
			});

			frm.toggle_display(["depreciation_schedule_view"], 1);
			frm.events.render_depreciation_schedule_view(frm, asset_depr_schedule_doc);
		} else {
			if (frm.doc.opening_accumulated_depreciation) {
				x_intervals.push(frappe.format(frm.doc.creation.split(" ")[0], { fieldtype: "Date" }));
				asset_values.push(
					flt(
						frm.doc.gross_purchase_amount - frm.doc.opening_accumulated_depreciation,
						precision("gross_purchase_amount")
					)
				);
			}

			let depr_entries = (
				await frappe.call({
					method: "get_manual_depreciation_entries",
					doc: frm.doc,
				})
			).message;

			$.each(depr_entries || [], function (i, v) {
				x_intervals.push(frappe.format(v.posting_date, { fieldtype: "Date" }));
				let last_asset_value = asset_values[asset_values.length - 1];
				asset_values.push(flt(last_asset_value - v.value, precision("gross_purchase_amount")));
			});
		}

		if (["Scrapped", "Sold"].includes(frm.doc.status)) {
			x_intervals.push(frappe.format(frm.doc.disposal_date, { fieldtype: "Date" }));
			asset_values.push(0);
		}

		frm.dashboard.render_graph({
			title: __("Asset Value"),
			data: {
				labels: x_intervals,
				datasets: [
					{
						color: "green",
						values: asset_values,
						formatted: asset_values.map((d) => d?.toFixed(2)),
					},
				],
			},
			type: "line",
		});
	},

	item_code: function (frm) {
		if (frm.doc.item_code && frm.doc.calculate_depreciation && frm.doc.gross_purchase_amount) {
			frm.trigger("set_finance_book");
		} else {
			frm.set_value("finance_books", []);
		}
	},

	set_finance_book: function (frm) {
		frappe.call({
			method: "erpnext.assets.doctype.asset.asset.get_item_details",
			args: {
				item_code: frm.doc.item_code,
				asset_category: frm.doc.asset_category,
				gross_purchase_amount: frm.doc.gross_purchase_amount,
			},
			callback: function (r, rt) {
				if (r.message) {
					frm.set_value("finance_books", r.message);
				}
			},
		});
	},

	is_existing_asset: function (frm) {
		frm.trigger("toggle_reference_doc");
	},

	is_composite_asset: function (frm) {
		if (frm.doc.is_composite_asset) {
			frm.set_value("gross_purchase_amount", 0);
			frm.set_df_property("gross_purchase_amount", "read_only", 1);
		} else {
			frm.set_df_property("gross_purchase_amount", "read_only", 0);
		}

		frm.trigger("toggle_reference_doc");
	},

	make_sales_invoice: function (frm) {
		frappe.call({
			args: {
				asset: frm.doc.name,
				item_code: frm.doc.item_code,
				company: frm.doc.company,
				serial_no: frm.doc.serial_no,
			},
			method: "erpnext.assets.doctype.asset.asset.make_sales_invoice",
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	create_asset_maintenance: function (frm) {
		frappe.call({
			args: {
				asset: frm.doc.name,
				item_code: frm.doc.item_code,
				item_name: frm.doc.item_name,
				asset_category: frm.doc.asset_category,
				company: frm.doc.company,
			},
			method: "erpnext.assets.doctype.asset.asset.create_asset_maintenance",
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	create_asset_repair: function (frm) {
		frappe.call({
			args: {
				company: frm.doc.company,
				asset: frm.doc.name,
				asset_name: frm.doc.asset_name,
			},
			method: "erpnext.assets.doctype.asset.asset.create_asset_repair",
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	create_asset_capitalization: function (frm) {
		frappe.call({
			args: {
				company: frm.doc.company,
				asset: frm.doc.name,
				asset_name: frm.doc.asset_name,
				item_code: frm.doc.item_code,
			},
			method: "erpnext.assets.doctype.asset.asset.create_asset_capitalization",
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				$(".primary-action").prop("hidden", false);
			},
		});
	},

	split_asset: function (frm) {
		const title = __("Split Asset");

		const fields = [
			{
				fieldname: "split_qty",
				fieldtype: "Int",
				label: __("Split Qty"),
				reqd: 1,
			},
		];

		let dialog = new frappe.ui.Dialog({
			title: title,
			fields: fields,
		});

		dialog.set_primary_action(__("Split"), function () {
			const dialog_data = dialog.get_values();
			frappe.call({
				args: {
					asset_name: frm.doc.name,
					split_qty: cint(dialog_data.split_qty),
				},
				method: "erpnext.assets.doctype.asset.asset.split_asset",
				callback: function (r) {
					let doclist = frappe.model.sync(r.message);
					frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				},
			});

			dialog.hide();
		});

		dialog.show();
	},

	create_asset_value_adjustment: function (frm) {
		frappe.call({
			args: {
				asset: frm.doc.name,
				asset_category: frm.doc.asset_category,
				company: frm.doc.company,
			},
			method: "erpnext.assets.doctype.asset.asset.create_asset_value_adjustment",
			freeze: 1,
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	calculate_depreciation: function (frm) {
		frm.toggle_reqd("finance_books", frm.doc.calculate_depreciation);
		if (frm.doc.item_code && frm.doc.calculate_depreciation && frm.doc.gross_purchase_amount) {
			frm.trigger("set_finance_book");
		} else {
			frm.set_value("finance_books", []);
		}
	},

	gross_purchase_amount: function (frm) {
		if (frm.doc.finance_books) {
			frm.doc.finance_books.forEach((d) => {
				frm.events.set_depreciation_rate(frm, d);
			});
		}
	},

	purchase_receipt: (frm) => {
		frm.trigger("toggle_reference_doc");
		if (frm.doc.purchase_receipt) {
			if (frm.doc.item_code) {
				frm.events.set_values_from_purchase_doc(frm, "Purchase Receipt");
			} else {
				frm.set_value("purchase_receipt", "");
				frappe.msgprint({
					title: __("Not Allowed"),
					message: __("Please select Item Code first"),
				});
			}
		}
	},

	purchase_invoice: (frm) => {
		frm.trigger("toggle_reference_doc");
		if (frm.doc.purchase_invoice) {
			if (frm.doc.item_code) {
				frm.events.set_values_from_purchase_doc(frm, "Purchase Invoice");
			} else {
				frm.set_value("purchase_invoice", "");
				frappe.msgprint({
					title: __("Not Allowed"),
					message: __("Please select Item Code first"),
				});
			}
		}
	},

	set_values_from_purchase_doc: (frm, doctype) => {
		frappe.call({
			method: "erpnext.assets.doctype.asset.asset.get_values_from_purchase_doc",
			args: {
				purchase_doc_name: frm.doc.purchase_receipt || frm.doc.purchase_invoice,
				item_code: frm.doc.item_code,
				doctype: doctype,
			},
			callback: (r) => {
				if (r.message) {
					let data = r.message;
					frm.set_value("company", data.company);
					frm.set_value("purchase_date", data.purchase_date);
					frm.set_value("gross_purchase_amount", data.gross_purchase_amount);
					frm.set_value("purchase_amount", data.gross_purchase_amount);
					frm.set_value("asset_quantity", data.asset_quantity);
					frm.set_value("cost_center", data.cost_center);
					if (data.asset_location) {
						frm.set_value("location", data.asset_location);
					}

					if (doctype === "Purchase Receipt") {
						frm.set_value("purchase_receipt_item", data.purchase_receipt_item);
					} else {
						frm.set_value("purchase_invoice_item", data.purchase_invoice_item);
					}
				}
			},
		});
	},

	set_depreciation_rate: function (frm, row) {
		if (
			row.total_number_of_depreciations &&
			row.frequency_of_depreciation &&
			row.expected_value_after_useful_life
		) {
			frappe.call({
				method: "get_depreciation_rate",
				doc: frm.doc,
				args: row,
				callback: function (r) {
					if (r.message) {
						frappe.flags.dont_change_rate = true;
						frappe.model.set_value(
							row.doctype,
							row.name,
							"rate_of_depreciation",
							flt(r.message, precision("rate_of_depreciation", row))
						);
					}
				},
			});
		}
	},

	set_salvage_value_percentage_or_expected_value_after_useful_life: function (
		frm,
		row,
		salvage_value_percentage_changed,
		expected_value_after_useful_life_changed
	) {
		if (expected_value_after_useful_life_changed) {
			frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life = true;
			const new_salvage_value_percentage = flt(
				(row.expected_value_after_useful_life * 100) / frm.doc.gross_purchase_amount,
				precision("salvage_value_percentage", row)
			);
			frappe.model.set_value(
				row.doctype,
				row.name,
				"salvage_value_percentage",
				new_salvage_value_percentage
			);
			frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life = false;
		} else if (salvage_value_percentage_changed) {
			frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life = true;
			const new_expected_value_after_useful_life = flt(
				frm.doc.gross_purchase_amount * (row.salvage_value_percentage / 100),
				precision("gross_purchase_amount")
			);
			frappe.model.set_value(
				row.doctype,
				row.name,
				"expected_value_after_useful_life",
				new_expected_value_after_useful_life
			);
			frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life = false;
		}
	},
});

frappe.ui.form.on("Asset Finance Book", {
	depreciation_method: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		frm.events.set_depreciation_rate(frm, row);
	},

	expected_value_after_useful_life: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		if (!frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life) {
			frm.events.set_salvage_value_percentage_or_expected_value_after_useful_life(
				frm,
				row,
				false,
				true
			);
		}
		frm.events.set_depreciation_rate(frm, row);
	},

	salvage_value_percentage: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		if (!frappe.flags.from_set_salvage_value_percentage_or_expected_value_after_useful_life) {
			frm.events.set_salvage_value_percentage_or_expected_value_after_useful_life(
				frm,
				row,
				true,
				false
			);
		}
	},

	frequency_of_depreciation: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		frm.events.set_depreciation_rate(frm, row);
	},

	total_number_of_depreciations: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		frm.events.set_depreciation_rate(frm, row);
	},

	rate_of_depreciation: function (frm, cdt, cdn) {
		if (!frappe.flags.dont_change_rate) {
			frappe.model.set_value(cdt, cdn, "expected_value_after_useful_life", 0);
		}

		frappe.flags.dont_change_rate = false;
	},

	depreciation_start_date: function (frm, cdt, cdn) {
		const book = locals[cdt][cdn];
		if (frm.doc.available_for_use_date && book.depreciation_start_date < frm.doc.available_for_use_date) {
			frappe.msgprint(__("Depreciation Posting Date cannot be before Available-for-use Date"));
			book.depreciation_start_date = "";
			frm.refresh_field("finance_books");
		}
	},
});

erpnext.asset.scrap_asset = function (frm) {
	var scrap_dialog = new frappe.ui.Dialog({
		title: __("Enter date to scrap asset"),
		fields: [
			{
				label: __("Select the date"),
				fieldname: "scrap_date",
				fieldtype: "Date",
				reqd: 1,
			},
		],
		size: "medium",
		primary_action_label: "Submit",
		primary_action(values) {
			frappe.call({
				args: {
					asset_name: frm.doc.name,
					scrap_date: values.scrap_date,
				},
				method: "erpnext.assets.doctype.asset.depreciation.scrap_asset",
				callback: function (r) {
					frm.reload_doc();
					scrap_dialog.hide();
				},
			});
		},
	});
	scrap_dialog.show();
};

erpnext.asset.restore_asset = function (frm) {
	frappe.confirm(__("Do you really want to restore this scrapped asset?"), function () {
		frappe.call({
			args: {
				asset_name: frm.doc.name,
			},
			method: "erpnext.assets.doctype.asset.depreciation.restore_asset",
			callback: (r) => frm.reload_doc(),
		});
	});
};

erpnext.asset.transfer_asset = function (frm) {
	frappe.call({
		method: "erpnext.assets.doctype.asset.asset.make_asset_movement",
		freeze: true,
		args: {
			assets: [{ name: frm.doc.name }],
			purpose: "Transfer",
		},
		callback: function (r) {
			if (r.message) {
				var doc = frappe.model.sync(r.message)[0];
				frappe.set_route("Form", doc.doctype, doc.name);
			}
		},
	});
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Fixed Asset Register` | Script Report | Assets |
| `Asset Depreciations and Balances` | Script Report | Accounts |
| `Asset Depreciation Ledger` | Script Report | Accounts |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Asset Value` | Asset Value | Sum | Assets |
| `New Assets (This Year)` | New Assets (This Year) | Count | Assets |
| `Total Assets` | Total Assets | Count | Assets |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
