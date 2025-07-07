# Master Control Plan: `Dunning`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | DUNN-.MM.-.YY.- |  |  |  | DUNN-.MM.-.YY.- | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Resolved
Unresolved
Cancelled |  |  | ✅ | Unresolved | None |
| `section_break_9` | Currency | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `conversion_rate` | Conversion Rate | Float | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `dunning_type` | Dunning Type | Link | Dunning Type |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `rate_of_interest` | Rate of Interest (%) Yearly | Float | None |  |  |  | 0 | None |
| `section_break_12` | None | Section Break | None |  |  |  | None | None |
| `overdue_payments` | Overdue Payments | Table | Overdue Payment |  |  |  | None | None |
| `section_break_28` | None | Section Break | None |  |  |  | None | None |
| `total_interest` | Total Interest | Currency | currency |  |  | ✅ | 0 | None |
| `dunning_fee` | Dunning Fee | Currency | currency |  |  |  | 0 | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `dunning_amount` | Dunning Amount | Currency | currency |  |  | ✅ | 0 | None |
| `base_dunning_amount` | Dunning Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `section_break_32` | None | Section Break | None |  |  |  | None | None |
| `spacer` | Spacer | Data | None |  | ✅ | ✅ | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `total_outstanding` | Total Outstanding | Currency | currency |  |  | ✅ | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | 0 | None |
| `printing_settings_section` | Printing Settings | Section Break | None |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  |  | None | None |
| `body_text` | Body Text | Text Editor | None |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `closing_text` | Closing Text | Text Editor | None |  |  |  | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `income_account` | Income Account | Link | Account |  |  |  | None | For dunning fee and interest |
| `column_break_48` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `amended_from` | Amended From | Link | Dunning |  |  | ✅ | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `address_and_contact_section` | None | Section Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_vodj` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  |  | ✅ | None | None |
| `section_break_xban` | None | Section Break | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `company_address` | Company Address | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address Display | Text Editor | None |  |  | ✅ | None | None |
| `column_break_lqmf` | None | Column Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/dunning/dunning.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Dunning", {
	setup: function (frm) {
		frm.set_query("sales_invoice", "overdue_payments", () => {
			return {
				filters: {
					docstatus: 1,
					company: frm.doc.company,
					customer: frm.doc.customer,
					outstanding_amount: [">", 0],
					status: "Overdue",
				},
			};
		});
		frm.set_query("income_account", () => {
			return {
				filters: {
					company: frm.doc.company,
					root_type: "Income",
					is_group: 0,
				},
			};
		});
		frm.set_query("cost_center", () => {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("customer_address", erpnext.queries.address_query);
		frm.set_query("company_address", erpnext.queries.company_address_query);

		// cannot add rows manually, only via button "Fetch Overdue Payments"
		frm.set_df_property("overdue_payments", "cannot_add_rows", true);
	},
	refresh: function (frm) {
		frm.set_df_property("company", "read_only", frm.doc.__islocal ? 0 : 1);
		if (frm.doc.docstatus === 1 && frm.doc.status === "Unresolved") {
			frm.add_custom_button(__("Resolve"), () => {
				frm.set_value("status", "Resolved");
			});
		}
		if (frm.doc.docstatus === 1 && frm.doc.status !== "Resolved") {
			frm.add_custom_button(
				__("Payment"),
				function () {
					frm.events.make_payment_entry(frm);
				},
				__("Create")
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (frm.doc.docstatus === 0) {
			frm.add_custom_button(__("Fetch Overdue Payments"), () => {
				erpnext.utils.map_current_doc({
					method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.create_dunning",
					source_doctype: "Sales Invoice",
					date_field: "due_date",
					target: frm,
					setters: {
						customer: frm.doc.customer || undefined,
					},
					get_query_filters: {
						docstatus: 1,
						status: "Overdue",
						company: frm.doc.company,
					},
					allow_child_item_selection: true,
					child_fieldname: "payment_schedule",
					child_columns: ["due_date", "outstanding"],
				});
			});
		}

		frappe.dynamic_link = { doc: frm.doc, fieldname: "customer", doctype: "Customer" };

		frm.toggle_display(
			"customer_name",
			frm.doc.customer_name && frm.doc.customer_name !== frm.doc.customer
		);
	},
	// When multiple companies are set up. in case company name is changed set default company address
	company: function (frm) {
		if (frm.doc.company) {
			frappe.call({
				method: "erpnext.setup.doctype.company.company.get_default_company_address",
				args: { name: frm.doc.company, existing_address: frm.doc.company_address || "" },
				debounce: 2000,
				callback: function (r) {
					frm.set_value("company_address", (r && r.message) || "");
				},
			});

			if (frm.fields_dict.currency) {
				const company_currency = erpnext.get_currency(frm.doc.company);

				if (!frm.doc.currency) {
					frm.set_value("currency", company_currency);
				}

				if (frm.doc.currency == company_currency) {
					frm.set_value("conversion_rate", 1.0);
				}
			}

			const company_doc = frappe.get_doc(":Company", frm.doc.company);
			if (company_doc.default_letter_head) {
				if (frm.fields_dict.letter_head) {
					frm.set_value("letter_head", company_doc.default_letter_head);
				}
			}
		}
	},
	currency: function (frm) {
		// this.set_dynamic_labels();
		const company_currency = erpnext.get_currency(frm.doc.company);
		// Added `ignore_pricing_rule` to determine if document is loading after mapping from another doc
		if (frm.doc.currency && frm.doc.currency !== company_currency) {
			frappe.call({
				method: "erpnext.setup.utils.get_exchange_rate",
				args: {
					transaction_date: frm.doc.posting_date,
					from_currency: frm.doc.currency,
					to_currency: company_currency,
					args: "for_selling",
				},
				freeze: true,
				freeze_message: __("Fetching exchange rates ..."),
				callback: function (r) {
					const exchange_rate = flt(r.message);
					if (exchange_rate != frm.doc.conversion_rate) {
						frm.set_value("conversion_rate", exchange_rate);
					}
				},
			});
		} else {
			frm.trigger("conversion_rate");
		}
	},
	customer: (frm) => {
		erpnext.utils.get_party_details(frm);
	},
	conversion_rate: function (frm) {
		if (frm.doc.currency === erpnext.get_currency(frm.doc.company)) {
			frm.set_value("conversion_rate", 1.0);
		}

		// Make read only if Accounts Settings doesn't allow stale rates
		frm.set_df_property("conversion_rate", "read_only", erpnext.stale_rate_allowed() ? 0 : 1);
	},
	customer_address: function (frm) {
		erpnext.utils.get_address_display(frm, "customer_address");
	},
	company_address: function (frm) {
		erpnext.utils.get_address_display(frm, "company_address");
	},
	dunning_type: function (frm) {
		frm.trigger("get_dunning_letter_text");
	},
	language: function (frm) {
		frm.trigger("get_dunning_letter_text");
	},
	get_dunning_letter_text: function (frm) {
		if (frm.doc.dunning_type) {
			frappe.call({
				method: "erpnext.accounts.doctype.dunning.dunning.get_dunning_letter_text",
				args: {
					dunning_type: frm.doc.dunning_type,
					language: frm.doc.language,
					doc: frm.doc,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("body_text", r.message.body_text);
						frm.set_value("closing_text", r.message.closing_text);
						frm.set_value("language", r.message.language);
					} else {
						frm.set_value("body_text", "");
						frm.set_value("closing_text", "");
					}
				},
			});
		}
	},
	posting_date: function (frm) {
		frm.trigger("calculate_overdue_days");
	},
	rate_of_interest: function (frm) {
		frm.trigger("calculate_interest");
	},
	dunning_fee: function (frm) {
		frm.trigger("calculate_totals");
	},
	overdue_payments_add: function (frm) {
		frm.trigger("calculate_totals");
	},
	overdue_payments_remove: function (frm) {
		frm.trigger("calculate_totals");
	},
	calculate_overdue_days: function (frm) {
		frm.doc.overdue_payments.forEach((row) => {
			if (frm.doc.posting_date && row.due_date) {
				const overdue_days = moment(frm.doc.posting_date).diff(row.due_date, "days");
				frappe.model.set_value(row.doctype, row.name, "overdue_days", overdue_days);
			}
		});
	},
	calculate_interest: function (frm) {
		frm.doc.overdue_payments.forEach((row) => {
			const interest_per_day = frm.doc.rate_of_interest / 100 / 365;
			const interest = flt(
				interest_per_day * row.overdue_days * row.outstanding,
				precision("interest", row)
			);
			frappe.model.set_value(row.doctype, row.name, "interest", interest);
		});
	},
	calculate_totals: function (frm) {
		const total_interest = frm.doc.overdue_payments.reduce((prev, cur) => prev + cur.interest, 0);
		const total_outstanding = frm.doc.overdue_payments.reduce((prev, cur) => prev + cur.outstanding, 0);
		const dunning_amount = total_interest + frm.doc.dunning_fee;
		const base_dunning_amount = dunning_amount * frm.doc.conversion_rate;
		const grand_total = total_outstanding + dunning_amount;

		function setWithPrecison(field, value) {
			frm.set_value(field, flt(value, precision(field)));
		}

		setWithPrecison("total_outstanding", total_outstanding);
		setWithPrecison("total_interest", total_interest);
		setWithPrecison("dunning_amount", dunning_amount);
		setWithPrecison("base_dunning_amount", base_dunning_amount);
		setWithPrecison("grand_total", grand_total);
	},
	make_payment_entry: function (frm) {
		return frappe.call({
			method: "erpnext.accounts.doctype.payment_entry.payment_entry.get_payment_entry",
			args: {
				dt: frm.doc.doctype,
				dn: frm.doc.name,
			},
			callback: function (r) {
				var doc = frappe.model.sync(r.message);
				frappe.set_route("Form", doc[0].doctype, doc[0].name);
			},
		});
	},
});

frappe.ui.form.on("Overdue Payment", {
	interest: function (frm) {
		frm.trigger("calculate_totals");
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
