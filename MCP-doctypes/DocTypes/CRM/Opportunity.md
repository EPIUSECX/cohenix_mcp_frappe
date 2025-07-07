# Master Control Plan: `Opportunity`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** Potential Sales Deal

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | CRM-OPP-.YYYY.- | ✅ |  |  | None | None |
| `opportunity_from` | Opportunity From | Link | DocType | ✅ |  |  | None | None |
| `party_name` | Party | Dynamic Link | opportunity_from | ✅ |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  | ✅ | ✅ | None | None |
| `status` | Status | Select | Open
Quotation
Converted
Lost
Replied
Closed | ✅ |  |  | Open | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `opportunity_type` | Opportunity Type | Link | Opportunity Type |  |  |  | Sales | None |
| `opportunity_owner` | Opportunity Owner | Link | User |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `sales_stage` | Sales Stage | Link | Sales Stage |  |  |  | Prospecting | None |
| `expected_closing` | Expected Closing Date | Date | None |  |  |  | None | None |
| `probability` | Probability (%) | Percent | None |  |  |  | 100 | None |
| `organization_details_section` | Organization | Section Break | None |  |  |  | None | None |
| `no_of_employees` | No of Employees | Select | 1-10
11-50
51-200
201-500
501-1000
1000+ |  |  |  | None | None |
| `annual_revenue` | Annual Revenue | Currency | None |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `industry` | Industry | Link | Industry Type |  |  |  | None | None |
| `market_segment` | Market Segment | Link | Market Segment |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `city` | City | Data | None |  |  |  | None | None |
| `state` | State/Province | Data | None |  |  |  | None | None |
| `country` | Country | Link | Country |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `section_break_14` | Opportunity Value | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `column_break_36` | None | Column Break | None |  |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `opportunity_amount` | Opportunity Amount | Currency | currency |  |  |  | None | None |
| `base_opportunity_amount` | Opportunity Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_analytics` | Analytics | Section Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `column_break_emai` | None | Column Break | None |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `column_break_whcu` | None | Column Break | None |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `transaction_date` | Opportunity Date | Date | None | ✅ |  |  | Today | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  |  | None | None |
| `amended_from` | Amended From | Link | Opportunity |  |  | ✅ | None | None |
| `title` | Title | Data | None |  | ✅ |  | None | None |
| `first_response_time` | First Response Time | Duration | None |  |  | ✅ | None | None |
| `lost_detail_section` | Lost Reasons | Section Break | None |  |  |  | None | None |
| `lost_reasons` | Lost Reasons | Table MultiSelect | Opportunity Lost Reason Detail |  |  | ✅ | None | None |
| `order_lost_reason` | Detailed Reason | Small Text | None |  |  | ✅ | None | None |
| `column_break_56` | None | Column Break | None |  |  |  | None | None |
| `competitors` | Competitors | Table MultiSelect | Competitor Detail |  |  | ✅ | None | None |
| `contact_info` | Contacts | Tab Break | fa fa-bullhorn |  |  |  | None | None |
| `primary_contact_section` | Primary Contact | Section Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `job_title` | Job Title | Data | None |  |  |  | None | None |
| `column_break_54` | None | Column Break | None |  |  |  | None | None |
| `contact_email` | Contact Email | Data | Email |  |  |  | None | None |
| `contact_mobile` | Contact Mobile | Data | Phone |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `whatsapp` | WhatsApp | Data | Phone |  |  |  | None | None |
| `phone` | Phone | Data | Phone |  |  |  | None | None |
| `phone_ext` | Phone Ext. | Data | None |  |  |  | None | None |
| `address_contact_section` | Address & Contact | Section Break | None |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  |  | None | None |
| `customer_address` | Customer / Lead Address | Link | Address |  | ✅ |  | None | None |
| `address_display` | Address | Text Editor | None |  | ✅ | ✅ | None | None |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `items_section` | Items | Tab Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Opportunity Item |  |  |  | None | None |
| `section_break_32` | None | Section Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `activities_tab` | Activities | Tab Break | None |  |  |  | None | None |
| `open_activities_html` | Open Activities HTML | HTML | None |  |  |  | None | None |
| `all_activities_section` | All Activities | Section Break | None |  |  |  | None | None |
| `all_activities_html` | All Activities HTML | HTML | None |  |  |  | None | None |
| `notes_tab` | Comments | Tab Break | None |  |  |  | None | None |
| `notes_html` | Notes HTML | HTML | None |  |  |  | None | None |
| `notes` | Notes | Table | CRM Note |  | ✅ |  | None | None |
| `dashboard_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 18
- **Dynamic Link Fields:** 1
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/opportunity/opportunity.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt
frappe.provide("erpnext.crm");
erpnext.pre_sales.set_as_lost("Opportunity");
erpnext.sales_common.setup_selling_controller();

frappe.ui.form.on("Opportunity", {
	setup: function (frm) {
		frm.custom_make_buttons = {
			Quotation: "Quotation",
			"Supplier Quotation": "Supplier Quotation",
		};

		frm.set_query("opportunity_from", function () {
			return {
				filters: {
					name: ["in", ["Customer", "Lead", "Prospect"]],
				},
			};
		});

		frm.email_field = "contact_email";
	},

	validate: function (frm) {
		if (frm.doc.status == "Lost" && !frm.doc.lost_reasons.length) {
			frm.trigger("set_as_lost_dialog");
			frappe.throw(__("Lost Reasons are required in case opportunity is Lost."));
		}
	},

	onload_post_render: function (frm) {
		frm.get_field("items").grid.set_multiple_add("item_code", "qty");
	},

	party_name: function (frm) {
		frm.trigger("set_contact_link");

		if (frm.doc.opportunity_from == "Customer") {
			erpnext.utils.get_party_details(frm);
		} else if (frm.doc.opportunity_from == "Lead") {
			erpnext.utils.map_current_doc({
				method: "erpnext.crm.doctype.lead.lead.make_opportunity",
				source_name: frm.doc.party_name,
				frm: frm,
			});
		}
	},

	status: function (frm) {
		if (frm.doc.status == "Lost") {
			frm.trigger("set_as_lost_dialog");
		}
	},

	customer_address: function (frm, cdt, cdn) {
		erpnext.utils.get_address_display(frm, "customer_address", "address_display", false);
	},

	contact_person: erpnext.utils.get_contact_details,

	opportunity_from: function (frm) {
		frm.trigger("setup_opportunity_from");

		frm.set_value("party_name", "");
	},

	setup_opportunity_from: function (frm) {
		frm.trigger("setup_queries");
		frm.trigger("set_dynamic_field_label");
	},

	refresh: function (frm) {
		var doc = frm.doc;
		frm.trigger("setup_opportunity_from");
		erpnext.toggle_naming_series();

		if (!frm.is_new() && doc.status !== "Lost") {
			if (doc.items) {
				frm.add_custom_button(
					__("Supplier Quotation"),
					function () {
						frm.trigger("make_supplier_quotation");
					},
					__("Create")
				);

				frm.add_custom_button(
					__("Request For Quotation"),
					function () {
						frm.trigger("make_request_for_quotation");
					},
					__("Create")
				);
			}

			if (frm.doc.opportunity_from != "Customer") {
				frm.add_custom_button(
					__("Customer"),
					function () {
						frm.trigger("make_customer");
					},
					__("Create")
				);
			}

			frm.add_custom_button(
				__("Quotation"),
				function () {
					frm.trigger("create_quotation");
				},
				__("Create")
			);

			let company_currency = erpnext.get_currency(frm.doc.company);
			if (company_currency != frm.doc.currency) {
				frm.add_custom_button(__("Fetch Latest Exchange Rate"), function () {
					frm.trigger("currency");
				});
			}
		}

		if (!frm.doc.__islocal && frm.perm[0].write && frm.doc.docstatus == 0) {
			if (frm.doc.status === "Open") {
				frm.add_custom_button(__("Close"), function () {
					frm.set_value("status", "Closed");
					frm.save();
				});
			} else {
				frm.add_custom_button(__("Reopen"), function () {
					frm.set_value("lost_reasons", []);
					frm.set_value("status", "Open");
					frm.save();
				});
			}
		}

		if (!frm.is_new()) {
			frappe.contacts.render_address_and_contact(frm);
			// frm.trigger('render_contact_day_html');
		} else {
			frappe.contacts.clear_address_and_contact(frm);
		}

		if (frm.doc.opportunity_from && frm.doc.party_name) {
			frm.trigger("set_contact_link");
		}
	},

	set_contact_link: function (frm) {
		if (frm.doc.opportunity_from == "Customer" && frm.doc.party_name) {
			frappe.dynamic_link = { doc: frm.doc, fieldname: "party_name", doctype: "Customer" };
		} else if (frm.doc.opportunity_from == "Lead" && frm.doc.party_name) {
			frappe.dynamic_link = { doc: frm.doc, fieldname: "party_name", doctype: "Lead" };
		} else if (frm.doc.opportunity_from == "Prospect" && frm.doc.party_name) {
			frappe.dynamic_link = { doc: frm.doc, fieldname: "party_name", doctype: "Prospect" };
		}
	},

	currency: function (frm) {
		let company_currency = erpnext.get_currency(frm.doc.company);
		if (company_currency != frm.doc.currency) {
			frappe.call({
				method: "erpnext.setup.utils.get_exchange_rate",
				args: {
					from_currency: frm.doc.currency,
					to_currency: company_currency,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("conversion_rate", flt(r.message));
						frm.set_df_property(
							"conversion_rate",
							"description",
							"1 " + frm.doc.currency + " = [?] " + company_currency
						);
					}
				},
			});
		} else {
			frm.set_value("conversion_rate", 1.0);
			frm.set_df_property("conversion_rate", "hidden", 1);
			frm.set_df_property("conversion_rate", "description", "");
		}

		frm.trigger("opportunity_amount");
		frm.trigger("set_dynamic_field_label");
	},

	opportunity_amount: function (frm) {
		frm.set_value(
			"base_opportunity_amount",
			flt(frm.doc.opportunity_amount) * flt(frm.doc.conversion_rate)
		);
	},

	set_dynamic_field_label: function (frm) {
		if (frm.doc.opportunity_from) {
			frm.set_df_property("party_name", "label", frm.doc.opportunity_from);
		}
		frm.trigger("change_grid_labels");
		frm.trigger("change_form_labels");
	},

	make_supplier_quotation: function (frm) {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.opportunity.opportunity.make_supplier_quotation",
			frm: frm,
		});
	},

	make_request_for_quotation: function (frm) {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.opportunity.opportunity.make_request_for_quotation",
			frm: frm,
		});
	},

	change_form_labels: function (frm) {
		let company_currency = erpnext.get_currency(frm.doc.company);
		frm.set_currency_labels(["base_opportunity_amount", "base_total"], company_currency);
		frm.set_currency_labels(["opportunity_amount", "total"], frm.doc.currency);

		// toggle fields
		frm.toggle_display(
			["conversion_rate", "base_opportunity_amount", "base_total"],
			frm.doc.currency != company_currency
		);
	},

	change_grid_labels: function (frm) {
		let company_currency = erpnext.get_currency(frm.doc.company);
		frm.set_currency_labels(["base_rate", "base_amount"], company_currency, "items");
		frm.set_currency_labels(["rate", "amount"], frm.doc.currency, "items");

		let item_grid = frm.fields_dict.items.grid;
		$.each(["base_rate", "base_amount"], function (i, fname) {
			if (frappe.meta.get_docfield(item_grid.doctype, fname))
				item_grid.set_column_disp(fname, frm.doc.currency != company_currency);
		});
		frm.refresh_fields();
	},

	calculate_total: function (frm) {
		let total = 0,
			base_total = 0;
		frm.doc.items.forEach((item) => {
			total += item.amount;
			base_total += item.base_amount;
		});

		frm.set_value({
			total: flt(total),
			base_total: flt(base_total),
		});
	},
});
frappe.ui.form.on("Opportunity Item", {
	calculate: function (frm, cdt, cdn) {
		let row = frappe.get_doc(cdt, cdn);
		frappe.model.set_value(cdt, cdn, "amount", flt(row.qty) * flt(row.rate));
		frappe.model.set_value(cdt, cdn, "base_rate", flt(frm.doc.conversion_rate) * flt(row.rate));
		frappe.model.set_value(cdt, cdn, "base_amount", flt(frm.doc.conversion_rate) * flt(row.amount));
		frm.trigger("calculate_total");
	},
	qty: function (frm, cdt, cdn) {
		frm.trigger("calculate", cdt, cdn);
	},
	rate: function (frm, cdt, cdn) {
		frm.trigger("calculate", cdt, cdn);
	},
});

// TODO commonify this code
erpnext.crm.Opportunity = class Opportunity extends frappe.ui.form.Controller {
	onload() {
		if (!this.frm.doc.status) {
			this.frm.set_value("status", "Open");
		}
		if (!this.frm.doc.company && frappe.defaults.get_user_default("Company")) {
			this.frm.set_value("company", frappe.defaults.get_user_default("Company"));
		}
		if (!this.frm.doc.currency) {
			this.frm.set_value("currency", frappe.defaults.get_user_default("Currency"));
		}

		this.setup_queries();
	}

	refresh() {
		this.show_notes();
		this.show_activities();
	}

	setup_queries() {
		var me = this;

		me.frm.set_query("customer_address", erpnext.queries.address_query);

		this.frm.set_query("item_code", "items", function () {
			return {
				query: "erpnext.controllers.queries.item_query",
				filters: { is_sales_item: 1 },
			};
		});

		me.frm.set_query("contact_person", erpnext.queries["contact_query"]);

		if (me.frm.doc.opportunity_from == "Lead") {
			me.frm.set_query("party_name", erpnext.queries["lead"]);
		} else if (me.frm.doc.opportunity_from == "Customer") {
			me.frm.set_query("party_name", erpnext.queries["customer"]);
		} else if (me.frm.doc.opportunity_from == "Prospect") {
			me.frm.set_query("party_name", function () {
				return {
					filters: {
						company: me.frm.doc.company,
					},
				};
			});
		}
	}

	create_quotation() {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.opportunity.opportunity.make_quotation",
			frm: this.frm,
		});
	}

	make_customer() {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.opportunity.opportunity.make_customer",
			frm: this.frm,
		});
	}

	show_notes() {
		const crm_notes = new erpnext.utils.CRMNotes({
			frm: this.frm,
			notes_wrapper: $(this.frm.fields_dict.notes_html.wrapper),
		});
		crm_notes.refresh();
	}

	show_activities() {
		const crm_activities = new erpnext.utils.CRMActivities({
			frm: this.frm,
			open_activities_wrapper: $(this.frm.fields_dict.open_activities_html.wrapper),
			all_activities_wrapper: $(this.frm.fields_dict.all_activities_html.wrapper),
			form_wrapper: $(this.frm.wrapper),
		});
		crm_activities.refresh();
	}
};

extend_cscript(cur_frm.cscript, new erpnext.crm.Opportunity({ frm: cur_frm }));

cur_frm.cscript.item_code = function (doc, cdt, cdn) {
	var d = locals[cdt][cdn];
	if (d.item_code) {
		return frappe.call({
			method: "erpnext.crm.doctype.opportunity.opportunity.get_item_details",
			args: { item_code: d.item_code },
			callback: function (r, rt) {
				if (r.message) {
					$.each(r.message, function (k, v) {
						frappe.model.set_value(cdt, cdn, k, v);
					});
					refresh_field("image_view", d.name, "items");
				}
			},
		});
	}
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Opportunity Summary by Sales Stage` | Script Report | CRM |
| `Sales Pipeline Analytics` | Script Report | CRM |
| `First Response Time for Opportunity` | Script Report | CRM |
| `Territory-wise Sales` | Script Report | Selling |
| `Lost Opportunity` | Script Report | CRM |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Territory Wise Sales` | Territory Wise Sales | Group By | CRM |
| `Territory Wise Opportunity Count` | Territory Wise Opportunity Count | Group By | CRM |
| `Won Opportunities` | Won Opportunities | Count | CRM |
| `Opportunities via Campaigns` | Opportunities via Campaigns | Group By | CRM |
| `Opportunity Trends` | Opportunity Trends | Count | CRM |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Open Opportunity` | Open Opportunity | Count | CRM |
| `Won Opportunity (Last 1 Month)` | Won Opportunity (Last 1 Month) | Count | CRM |
| `New Opportunity (Last 1 Month)` | New Opportunity (Last 1 Month) | Count | CRM |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
