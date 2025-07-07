# Master Control Plan: `Quotation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Maintenance Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Maintenance Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Maintenance User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Maintenance User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | SAL-QTN-.YYYY.- | ✅ |  |  | None | None |
| `quotation_to` | Quotation To | Link | DocType | ✅ |  |  | Customer | None |
| `party_name` | Party | Dynamic Link | quotation_to |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  | ✅ | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `valid_till` | Valid Till | Date | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `order_type` | Order Type | Select | 
Sales
Maintenance
Shopping Cart | ✅ |  |  | Sales | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `has_unit_price_items` | Has Unit Price Items | Check | None |  | ✅ |  | 0 | None |
| `amended_from` | Amended From | Link | Quotation |  |  | ✅ | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which customer's currency is converted to company's base currency |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Price list currency is converted to company's base currency |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `items` | Items | Table | Quotation Item | ✅ |  |  | None | None |
| `sec_break23` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Sales Taxes and Charges Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `column_break_36` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_34` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_36` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Sales Taxes and Charges | Table | Sales Taxes and Charges |  |  |  | None | None |
| `section_break_39` | None | Section Break | None |  |  |  | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_42` | None | Column Break | None |  |  |  | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `totals` | Totals | Section Break | fa fa-money |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `section_break_44` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `coupon_code` | Coupon Code | Link | Coupon Code |  |  |  | None | None |
| `column_break_46` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `referral_sales_partner` | Referral Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `bundle_items_section` | Bundle Items | Section Break | fa fa-suitcase |  |  |  | None | None |
| `packed_items` | Bundle Items | Table | Packed Item |  |  |  | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `billing_address_section` | Billing Address | Section Break | fa fa-bullhorn |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break98` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `shipping_address_name` | Shipping Address | Link | Address |  |  |  | None | None |
| `column_break_81` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `company_address_section` | Company Address | Section Break | None |  |  |  | None | None |
| `company_address` | Company Address Name | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_87` | None | Column Break | None |  |  |  | None | None |
| `company_contact_person` | Company Contact Person | Link | Contact |  |  |  | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `payment_schedule_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `terms_section_break` | Terms and Conditions | Section Break | fa fa-legal |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Term Details | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `subscription_section` | Auto Repeat | Section Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `print_settings` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_73` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  | ✅ | None | None |
| `lost_reasons_section` | Lost Reasons | Section Break | None |  |  |  | None | None |
| `lost_reasons` | Lost Reasons | Table MultiSelect | Quotation Lost Reason Detail |  |  | ✅ | None | None |
| `competitors` | Competitors | Table MultiSelect | Competitor Detail |  |  |  | None | None |
| `column_break_117` | None | Column Break | None |  |  |  | None | None |
| `order_lost_reason` | Detailed Reason | Small Text | None |  |  |  | None | None |
| `additional_info_section` | Additional Info | Section Break | fa fa-file-text |  |  |  | None | None |
| `status` | Status | Select | Draft
Open
Replied
Partially Ordered
Ordered
Lost
Cancelled
Expired | ✅ |  | ✅ | Draft | None |
| `customer_group` | Customer Group | Link | Customer Group |  | ✅ |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `column_break_108` | None | Column Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `opportunity` | Opportunity | Link | Opportunity |  |  | ✅ | None | None |
| `supplier_quotation` | Supplier Quotation | Link | Supplier Quotation |  |  |  | None | None |
| `enq_det` | Opportunity Item | Text | None |  | ✅ | ✅ | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 30
- **Dynamic Link Fields:** 1
- **Table Fields:** 7

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/quotation/quotation.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.cscript.tax_table = "Sales Taxes and Charges";

erpnext.accounts.taxes.setup_tax_validations("Sales Taxes and Charges Template");
erpnext.accounts.taxes.setup_tax_filters("Sales Taxes and Charges");
erpnext.pre_sales.set_as_lost("Quotation");
erpnext.sales_common.setup_selling_controller();

frappe.ui.form.on("Quotation", {
	setup: function (frm) {
		(frm.custom_make_buttons = {
			"Sales Order": "Sales Order",
		}),
			frm.set_query("quotation_to", function () {
				return {
					filters: {
						name: ["in", ["Customer", "Lead", "Prospect"]],
					},
				};
			});

		frm.set_df_property("packed_items", "cannot_add_rows", true);
		frm.set_df_property("packed_items", "cannot_delete_rows", true);

		frm.set_query("serial_and_batch_bundle", "packed_items", (doc, cdt, cdn) => {
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

		frm.set_indicator_formatter("item_code", function (doc) {
			return !doc.qty && frm.doc.has_unit_price_items ? "yellow" : "";
		});
	},

	refresh: function (frm) {
		frm.trigger("set_label");
		frm.trigger("set_dynamic_field_label");

		if (frm.doc.docstatus === 0) {
			erpnext.set_unit_price_items_note(frm);
		}

		let sbb_field = frm.get_docfield("packed_items", "serial_and_batch_bundle");
		if (sbb_field) {
			sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.item_code,
					warehouse: row.doc.warehouse,
					voucher_type: frm.doc.doctype,
				};
			};
		}
	},

	quotation_to: function (frm) {
		frm.trigger("set_label");
		frm.trigger("toggle_reqd_lead_customer");
		frm.trigger("set_dynamic_field_label");
		// frm.set_value("party_name", ""); // removed to set party_name from url for crm integration
		frm.set_value("customer_name", "");
	},

	set_label: function (frm) {
		frm.fields_dict.customer_address.set_label(__(frm.doc.quotation_to + " Address"));
	},
});

erpnext.selling.QuotationController = class QuotationController extends erpnext.selling.SellingController {
	onload(doc, dt, dn) {
		super.onload(doc, dt, dn);

		// TODO: think of better way to do this
		// this.frm.trigger("disable_customer_if_creating_from_opportunity");
	}
	party_name() {
		var me = this;
		erpnext.utils.get_party_details(this.frm, null, null, function () {
			me.apply_price_list();
		});

		if (me.frm.doc.quotation_to == "Lead" && me.frm.doc.party_name) {
			me.frm.trigger("get_lead_details");
		}
	}
	refresh(doc, dt, dn) {
		super.refresh(doc, dt, dn);
		frappe.dynamic_link = {
			doc: this.frm.doc,
			fieldname: "party_name",
			doctype: doc.quotation_to,
		};

		var me = this;

		if (doc.__islocal && !doc.valid_till) {
			if (frappe.boot.sysdefaults.quotation_valid_till) {
				this.frm.set_value(
					"valid_till",
					frappe.datetime.add_days(
						doc.transaction_date,
						frappe.boot.sysdefaults.quotation_valid_till
					)
				);
			} else {
				this.frm.set_value("valid_till", frappe.datetime.add_months(doc.transaction_date, 1));
			}
		}

		if (doc.docstatus == 1 && !["Lost", "Ordered"].includes(doc.status)) {
			if (
				frappe.boot.sysdefaults.allow_sales_order_creation_for_expired_quotation ||
				!doc.valid_till ||
				frappe.datetime.get_diff(doc.valid_till, frappe.datetime.get_today()) >= 0
			) {
				this.frm.add_custom_button(__("Sales Order"), () => this.make_sales_order(), __("Create"));
			}

			if (doc.status !== "Ordered") {
				this.frm.add_custom_button(__("Set as Lost"), () => {
					this.frm.trigger("set_as_lost_dialog");
				});
			}

			cur_frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (this.frm.doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("Opportunity"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.crm.doctype.opportunity.opportunity.make_quotation",
						source_doctype: "Opportunity",
						target: me.frm,
						setters: [
							{
								label: "Party",
								fieldname: "party_name",
								fieldtype: "Link",
								options: me.frm.doc.quotation_to,
								default: me.frm.doc.party_name || undefined,
							},
							{
								label: "Opportunity Type",
								fieldname: "opportunity_type",
								fieldtype: "Link",
								options: "Opportunity Type",
								default: me.frm.doc.order_type || undefined,
							},
						],
						get_query_filters: {
							status: ["not in", ["Lost", "Closed"]],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From"),
				"btn-default"
			);
		}

		this.toggle_reqd_lead_customer();
	}

	make_sales_order() {
		var me = this;

		let has_alternative_item = this.frm.doc.items.some((item) => item.is_alternative);
		if (has_alternative_item) {
			this.show_alternative_items_dialog();
		} else {
			frappe.model.open_mapped_doc({
				method: "erpnext.selling.doctype.quotation.quotation.make_sales_order",
				frm: me.frm,
			});
		}
	}

	set_dynamic_field_label() {
		if (this.frm.doc.quotation_to == "Customer") {
			this.frm.set_df_property("party_name", "label", "Customer");
			this.frm.fields_dict.party_name.get_query = null;
		} else if (this.frm.doc.quotation_to == "Lead") {
			this.frm.set_df_property("party_name", "label", "Lead");
			this.frm.fields_dict.party_name.get_query = function () {
				return { query: "erpnext.controllers.queries.lead_query" };
			};
		} else if (this.frm.doc.quotation_to == "Prospect") {
			this.frm.set_df_property("party_name", "label", "Prospect");
			this.frm.fields_dict.party_name.get_query = null;
		}
	}

	toggle_reqd_lead_customer() {
		var me = this;

		// to overwrite the customer_filter trigger from queries.js
		this.frm.toggle_reqd("party_name", this.frm.doc.quotation_to);
		this.frm.set_query("customer_address", this.address_query);
		this.frm.set_query("shipping_address_name", this.address_query);
	}

	tc_name() {
		this.get_terms();
	}

	address_query(doc) {
		return {
			query: "frappe.contacts.doctype.address.address.address_query",
			filters: {
				link_doctype: frappe.dynamic_link.doctype,
				link_name: doc.party_name,
			},
		};
	}

	validate_company_and_party(party_field) {
		if (!this.frm.doc.quotation_to) {
			frappe.msgprint(
				__("Please select a value for {0} quotation_to {1}", [
					this.frm.doc.doctype,
					this.frm.doc.name,
				])
			);
			return false;
		} else if (this.frm.doc.quotation_to == "Lead") {
			return true;
		} else {
			return super.validate_company_and_party(party_field);
		}
	}

	get_lead_details() {
		var me = this;
		if (!this.frm.doc.quotation_to === "Lead") {
			return;
		}

		frappe.call({
			method: "erpnext.crm.doctype.lead.lead.get_lead_details",
			args: {
				lead: this.frm.doc.party_name,
				posting_date: this.frm.doc.transaction_date,
				company: this.frm.doc.company,
			},
			callback: function (r) {
				if (r.message) {
					me.frm.updating_party_details = true;
					me.frm.set_value(r.message);
					me.frm.refresh();
					me.frm.updating_party_details = false;
				}
			},
		});
	}

	show_alternative_items_dialog() {
		let me = this;

		const table_fields = [
			{
				fieldtype: "Data",
				fieldname: "name",
				label: __("Name"),
				read_only: 1,
			},
			{
				fieldtype: "Link",
				fieldname: "item_code",
				options: "Item",
				label: __("Item Code"),
				read_only: 1,
				in_list_view: 1,
				columns: 2,
				formatter: (value, df, options, doc) => {
					return doc.is_alternative ? `<span class="indicator yellow">${value}</span>` : value;
				},
			},
			{
				fieldtype: "Text Editor",
				fieldname: "description",
				label: __("Description"),
				in_list_view: 1,
				read_only: 1,
			},
			{
				fieldtype: "Currency",
				fieldname: "amount",
				label: __("Amount"),
				options: "currency",
				in_list_view: 1,
				read_only: 1,
			},
			{
				fieldtype: "Check",
				fieldname: "is_alternative",
				label: __("Is Alternative"),
				read_only: 1,
			},
		];

		this.data = this.frm.doc.items
			.filter((item) => item.is_alternative || item.has_alternative_item)
			.map((item) => {
				return {
					name: item.name,
					item_code: item.item_code,
					description: item.description,
					amount: item.amount,
					is_alternative: item.is_alternative,
				};
			});

		const dialog = new frappe.ui.Dialog({
			title: __("Select Alternative Items for Sales Order"),
			fields: [
				{
					fieldname: "info",
					fieldtype: "HTML",
					read_only: 1,
				},
				{
					fieldname: "alternative_items",
					fieldtype: "Table",
					cannot_add_rows: true,
					cannot_delete_rows: true,
					in_place_edit: true,
					reqd: 1,
					data: this.data,
					description: __("Select an item from each set to be used in the Sales Order."),
					get_data: () => {
						return this.data;
					},
					fields: table_fields,
				},
			],
			primary_action: function () {
				frappe.model.open_mapped_doc({
					method: "erpnext.selling.doctype.quotation.quotation.make_sales_order",
					frm: me.frm,
					args: {
						selected_items: dialog.fields_dict.alternative_items.grid.get_selected_children(),
					},
				});
				dialog.hide();
			},
			primary_action_label: __("Continue"),
		});

		dialog.fields_dict.info.$wrapper.html(
			`<p class="small text-muted">
				<span class="indicator yellow"></span>
				${__("Alternative Items")}
			</p>`
		);
		dialog.show();
	}

	currency() {
		super.currency();
		let me = this;
		const company_currency = this.get_company_currency();
		if (this.frm.doc.currency && this.frm.doc.currency !== company_currency) {
			this.get_exchange_rate(
				this.frm.doc.transaction_date,
				this.frm.doc.currency,
				company_currency,
				function (exchange_rate) {
					if (exchange_rate != me.frm.doc.conversion_rate) {
						me.set_margin_amount_based_on_currency(exchange_rate);
						me.set_actual_charges_based_on_currency(exchange_rate);
						me.frm.set_value("conversion_rate", exchange_rate);
					}
				}
			);
		}
	}

	disable_customer_if_creating_from_opportunity(doc) {
		if (doc.opportunity) {
			this.frm.set_df_property("party_name", "read_only", 1);
		}
	}
};

cur_frm.script_manager.make(erpnext.selling.QuotationController);

frappe.ui.form.on(
	"Quotation Item",
	"items_on_form_rendered",
	"packed_items_on_form_rendered",
	function (frm, cdt, cdn) {
		// enable tax_amount field if Actual
	}
);

frappe.ui.form.on("Quotation Item", "stock_balance", function (frm, cdt, cdn) {
	var d = frappe.model.get_doc(cdt, cdn);
	frappe.route_options = { item_code: d.item_code };
	frappe.set_route("query-report", "Stock Balance");
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Lost Quotations` | Script Report | Selling |
| `Quotation Trends` | Script Report | Selling |



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
