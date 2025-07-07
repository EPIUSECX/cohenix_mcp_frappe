# Master Control Plan: `Request for Quotation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | PUR-RFQ-.YYYY.- | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `billing_address` | Company Billing Address | Link | Address |  |  |  | None | None |
| `billing_address_display` | Billing Address Details | Text Editor | None |  |  | ✅ | None | None |
| `vendor` | Supplier | Link | Supplier |  | ✅ | ✅ | None | For individual supplier |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `schedule_date` | Required Date | Date | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Submitted
Cancelled | ✅ |  | ✅ | None | None |
| `has_unit_price_items` | Has Unit Price Items | Check | None |  | ✅ |  | 0 | None |
| `amended_from` | Amended From | Link | Request for Quotation |  |  | ✅ | None | None |
| `suppliers_section` | None | Section Break | None |  |  |  | None | None |
| `suppliers` | Suppliers | Table | Request for Quotation Supplier | ✅ |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Request for Quotation Item | ✅ |  |  | None | None |
| `supplier_response_section` | Email Details | Section Break | None |  |  |  | None | None |
| `email_template` | Email Template | Link | Email Template |  |  |  | None | None |
| `preview` | Preview Email | Button | None |  |  |  | None | None |
| `col_break_email_1` | None | Column Break | None |  |  |  | None | None |
| `html_llwp` | None | HTML | <p>In your <b>Email Template</b>, you can use the following special variables:
</p>
<ul>
        <li>
            <code>{{ update_password_link }}</code>: A link where your supplier can set a new password to log into your portal.
        </li>
        <li>
            <code>{{ portal_link }}</code>: A link to this RFQ in your supplier portal.
        </li>
        <li>
            <code>{{ supplier_name }}</code>: The company name of your supplier.
        </li>
        <li>
            <code>{{ contact.salutation }} {{ contact.last_name }}</code>: The contact person of your supplier.
        </li><li>
            <code>{{ user_fullname }}</code>: Your full name.
        </li>
    </ul>
<p></p>
<p>Apart from these, you can access all values in this RFQ, like <code>{{ message_for_supplier }}</code> or <code>{{ terms }}</code>.</p> |  |  | ✅ | None | None |
| `send_attached_files` | Send Attached Files | Check | None |  |  |  | 1 | If enabled, all files attached to this document will be attached to each email |
| `send_document_print` | Send Document Print | Check | None |  |  |  | 0 | If enabled, a print of this document will be attached to each email |
| `sec_break_email_2` | None | Section Break | None |  |  |  | None | None |
| `message_for_supplier` | Message for Supplier | Text Editor | None | ✅ |  |  | None | None |
| `terms_section_break` | Terms and Conditions | Section Break | fa fa-legal |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `printing_settings` | Printing Settings | Section Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `opportunity` | Opportunity | Link | Opportunity |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/request_for_quotation/request_for_quotation.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.add_fetch("contact", "email_id", "email_id");

erpnext.buying.setup_buying_controller();

frappe.ui.form.on("Request for Quotation", {
	setup: function (frm) {
		frm.custom_make_buttons = {
			"Supplier Quotation": "Create",
		};

		frm.fields_dict["suppliers"].grid.get_field("contact").get_query = function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			return {
				query: "frappe.contacts.doctype.contact.contact.contact_query",
				filters: {
					link_doctype: "Supplier",
					link_name: d.supplier || "",
				},
			};
		};

		frm.set_query("warehouse", "items", () => ({
			filters: {
				company: frm.doc.company,
				is_group: 0,
			},
		}));

		frm.set_indicator_formatter("item_code", function (doc) {
			return !doc.qty && frm.doc.has_unit_price_items ? "yellow" : "";
		});
	},

	onload: function (frm) {
		if (!frm.doc.message_for_supplier) {
			frm.set_value(
				"message_for_supplier",
				__("Please supply the specified items at the best possible rates")
			);
		}
	},

	refresh: function (frm, cdt, cdn) {
		if (frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Supplier Quotation"),
				function () {
					frm.trigger("make_supplier_quotation");
				},
				__("Create")
			);

			frm.add_custom_button(
				__("Send Emails to Suppliers"),
				function () {
					frappe.call({
						method: "erpnext.buying.doctype.request_for_quotation.request_for_quotation.send_supplier_emails",
						freeze: true,
						args: {
							rfq_name: frm.doc.name,
						},
						callback: function (r) {
							frm.reload_doc();
						},
					});
				},
				__("Tools")
			);

			frm.add_custom_button(
				__("Download PDF"),
				() => {
					frappe.prompt(
						[
							{
								fieldtype: "Link",
								label: "Select a Supplier",
								fieldname: "supplier",
								options: "Supplier",
								reqd: 1,
								default: frm.doc.suppliers?.length == 1 ? frm.doc.suppliers[0].supplier : "",
								get_query: () => {
									return {
										filters: [
											[
												"Supplier",
												"name",
												"in",
												frm.doc.suppliers.map((row) => {
													return row.supplier;
												}),
											],
										],
									};
								},
							},
							{
								fieldtype: "Section Break",
								label: "Print Settings",
								fieldname: "print_settings",
								collapsible: 1,
							},
							{
								fieldtype: "Link",
								label: "Print Format",
								fieldname: "print_format",
								options: "Print Format",
								placeholder: "Standard",
								get_query: () => {
									return {
										filters: {
											doc_type: "Request for Quotation",
										},
									};
								},
							},
							{
								fieldtype: "Link",
								label: "Language",
								fieldname: "language",
								options: "Language",
								default: frappe.boot.lang,
							},
							{
								fieldtype: "Link",
								label: "Letter Head",
								fieldname: "letter_head",
								options: "Letter Head",
								default: frm.doc.letter_head,
							},
						],
						(data) => {
							var w = window.open(
								frappe.urllib.get_full_url(
									"/api/method/erpnext.buying.doctype.request_for_quotation.request_for_quotation.get_pdf?" +
										new URLSearchParams({
											name: frm.doc.name,
											supplier: data.supplier,
											print_format: data.print_format || "Standard",
											language: data.language || frappe.boot.lang,
											letterhead: data.letter_head || frm.doc.letter_head || "",
										}).toString()
								)
							);
							if (!w) {
								frappe.msgprint(__("Please enable pop-ups"));
								return;
							}
						},
						__("Download PDF for Supplier"),
						__("Download")
					);
				},
				__("Tools")
			);

			frm.page.set_inner_btn_group_as_primary(__("Create"));

			frm.add_custom_button(
				__("Supplier Quotation Comparison"),
				function () {
					frm.trigger("show_supplier_quotation_comparison");
				},
				__("View")
			);
		}

		if (frm.doc.docstatus === 0) {
			erpnext.set_unit_price_items_note(frm);
		}
	},

	show_supplier_quotation_comparison(frm) {
		const today = new Date();
		const oneMonthAgo = new Date(today);
		oneMonthAgo.setMonth(today.getMonth() - 1);

		frappe.route_options = {
			company: frm.doc.company,
			from_date: moment(oneMonthAgo).format("YYYY-MM-DD"),
			to_date: moment(today).format("YYYY-MM-DD"),
			request_for_quotation: frm.doc.name,
		};
		frappe.set_route("query-report", "Supplier Quotation Comparison");
	},

	make_supplier_quotation: function (frm) {
		var doc = frm.doc;
		var dialog = new frappe.ui.Dialog({
			title: __("Create Supplier Quotation"),
			fields: [
				{
					fieldtype: "Link",
					label: __("Supplier"),
					fieldname: "supplier",
					options: "Supplier",
					reqd: 1,
					get_query: () => {
						return {
							filters: [
								[
									"Supplier",
									"name",
									"in",
									frm.doc.suppliers.map((row) => {
										return row.supplier;
									}),
								],
							],
						};
					},
				},
			],
			primary_action_label: __("Create"),
			primary_action: (args) => {
				if (!args) return;
				dialog.hide();

				return frappe.call({
					type: "GET",
					method: "erpnext.buying.doctype.request_for_quotation.request_for_quotation.make_supplier_quotation_from_rfq",
					args: {
						source_name: doc.name,
						for_supplier: args.supplier,
					},
					freeze: true,
					callback: function (r) {
						if (!r.exc) {
							var doc = frappe.model.sync(r.message);
							frappe.set_route("Form", r.message.doctype, r.message.name);
						}
					},
				});
			},
		});

		dialog.show();
	},

	schedule_date(frm) {
		if (frm.doc.schedule_date) {
			frm.doc.items.forEach((item) => {
				item.schedule_date = frm.doc.schedule_date;
			});
		}
		refresh_field("items");
	},
	preview: (frm) => {
		let dialog = new frappe.ui.Dialog({
			title: __("Preview Email"),
			fields: [
				{
					label: __("Supplier"),
					fieldtype: "Select",
					fieldname: "supplier",
					options: frm.doc.suppliers.map((row) => row.supplier),
					reqd: 1,
				},
				{
					fieldtype: "Column Break",
					fieldname: "col_break_1",
				},
				{
					label: __("Subject"),
					fieldtype: "Data",
					fieldname: "subject",
					read_only: 1,
					depends_on: "subject",
				},
				{
					fieldtype: "Section Break",
					fieldname: "sec_break_1",
					hide_border: 1,
				},
				{
					label: __("Email"),
					fieldtype: "HTML",
					fieldname: "email_preview",
				},
				{
					fieldtype: "Section Break",
					fieldname: "sec_break_2",
				},
				{
					label: __("Note"),
					fieldtype: "HTML",
					fieldname: "note",
				},
			],
		});

		dialog.fields_dict["supplier"].df.onchange = () => {
			frm.call("get_supplier_email_preview", {
				supplier: dialog.get_value("supplier"),
			}).then(({ message }) => {
				dialog.fields_dict.email_preview.$wrapper.empty();
				dialog.fields_dict.email_preview.$wrapper.append(message.message);
				dialog.set_value("subject", message.subject);
			});
		};

		const msg = __(
			"This is a preview of the email to be sent. A PDF of the document will automatically be attached with the email."
		);
		dialog.fields_dict.note.$wrapper.append(`<p class="small text-muted">${msg}</p>`);

		dialog.show();
	},
});
frappe.ui.form.on("Request for Quotation Item", {
	items_add(frm, cdt, cdn) {
		if (frm.doc.schedule_date) {
			frappe.model.set_value(cdt, cdn, "schedule_date", frm.doc.schedule_date);
		}
	},
});
frappe.ui.form.on("Request for Quotation Supplier", {
	supplier: function (frm, cdt, cdn) {
		var d = locals[cdt][cdn];
		frappe.call({
			method: "erpnext.accounts.party.get_party_details",
			args: {
				party: d.supplier,
				party_type: "Supplier",
			},
			callback: function (r) {
				if (r.message) {
					frappe.model.set_value(cdt, cdn, "contact", r.message.contact_person);
					frappe.model.set_value(cdt, cdn, "email_id", r.message.contact_email);
				}
			},
		});
	},
});

erpnext.buying.RequestforQuotationController = class RequestforQuotationController extends (
	erpnext.buying.BuyingController
) {
	refresh() {
		var me = this;
		super.refresh();
		if (this.frm.doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("Material Request"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.stock.doctype.material_request.material_request.make_request_for_quotation",
						source_doctype: "Material Request",
						target: me.frm,
						setters: {
							schedule_date: undefined,
							status: undefined,
						},
						get_query_filters: {
							material_request_type: "Purchase",
							docstatus: 1,
							status: ["!=", "Stopped"],
							per_ordered: ["<", 100],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);

			// Get items from Opportunity
			this.frm.add_custom_button(
				__("Opportunity"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.crm.doctype.opportunity.opportunity.make_request_for_quotation",
						source_doctype: "Opportunity",
						target: me.frm,
						setters: {
							party_name: undefined,
							opportunity_from: undefined,
							status: undefined,
						},
						get_query_filters: {
							status: ["not in", ["Closed", "Lost"]],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);

			// Get items from open Material Requests based on supplier
			this.frm.add_custom_button(
				__("Possible Supplier"),
				function () {
					// Create a dialog window for the user to pick their supplier
					var dialog = new frappe.ui.Dialog({
						title: __("Select Possible Supplier"),
						fields: [
							{
								fieldname: "supplier",
								fieldtype: "Link",
								options: "Supplier",
								label: "Supplier",
								reqd: 1,
								description: __("Get Items from Material Requests against this Supplier"),
							},
						],
						primary_action_label: __("Get Items"),
						primary_action: (args) => {
							if (!args) return;
							dialog.hide();

							erpnext.utils.map_current_doc({
								method: "erpnext.buying.doctype.request_for_quotation.request_for_quotation.get_item_from_material_requests_based_on_supplier",
								source_name: args.supplier,
								target: me.frm,
								setters: {
									company: me.frm.doc.company,
								},
								get_query_filters: {
									material_request_type: "Purchase",
									docstatus: 1,
									status: ["!=", "Stopped"],
									per_ordered: ["<", 100],
								},
							});
							dialog.hide();
						},
					});

					dialog.show();
				},
				__("Get Items From")
			);

			// Link Material Requests
			this.frm.add_custom_button(
				__("Link to Material Requests"),
				function () {
					erpnext.buying.link_to_mrs(me.frm);
				},
				__("Tools")
			);

			// Get Suppliers
			this.frm.add_custom_button(
				__("Get Suppliers"),
				function () {
					me.get_suppliers_button(me.frm);
				},
				__("Tools")
			);
		}
	}

	calculate_taxes_and_totals() {
		return;
	}

	tc_name() {
		this.get_terms();
	}

	get_suppliers_button(frm) {
		var doc = frm.doc;
		var dialog = new frappe.ui.Dialog({
			title: __("Get Suppliers"),
			fields: [
				{
					fieldtype: "Select",
					label: __("Get Suppliers By"),
					fieldname: "search_type",
					options: ["Supplier Group", "Tag"],
					reqd: 1,
					onchange() {
						if (dialog.get_value("search_type") == "Tag") {
							frappe
								.call({
									method: "erpnext.buying.doctype.request_for_quotation.request_for_quotation.get_supplier_tag",
								})
								.then((r) => {
									dialog.set_df_property("tag", "options", r.message);
								});
						}
					},
				},
				{
					fieldtype: "Link",
					label: __("Supplier Group"),
					fieldname: "supplier_group",
					options: "Supplier Group",
					reqd: 0,
					depends_on: "eval:doc.search_type == 'Supplier Group'",
				},
				{
					fieldtype: "Select",
					label: __("Tag"),
					fieldname: "tag",
					reqd: 0,
					depends_on: "eval:doc.search_type == 'Tag'",
				},
			],
			primary_action_label: __("Add Suppliers"),
			primary_action: (args) => {
				if (!args) return;
				dialog.hide();

				//Remove blanks
				for (var j = 0; j < frm.doc.suppliers.length; j++) {
					if (!Object.prototype.hasOwnProperty.call(frm.doc.suppliers[j], "supplier")) {
						frm.get_field("suppliers").grid.grid_rows[j].remove();
					}
				}

				function load_suppliers(r) {
					if (r.message) {
						for (var i = 0; i < r.message.length; i++) {
							var exists = false;
							let supplier = "";
							if (r.message[i].constructor === Array) {
								supplier = r.message[i][0];
							} else {
								supplier = r.message[i].name;
							}

							for (var j = 0; j < doc.suppliers.length; j++) {
								if (supplier === doc.suppliers[j].supplier) {
									exists = true;
								}
							}
							if (!exists) {
								var d = frm.add_child("suppliers");
								d.supplier = supplier;
								frm.script_manager.trigger("supplier", d.doctype, d.name);
							}
						}
					}
					frm.refresh_field("suppliers");
				}

				if (args.search_type === "Tag" && args.tag) {
					return frappe.call({
						type: "GET",
						method: "frappe.desk.doctype.tag.tag.get_tagged_docs",
						args: {
							doctype: "Supplier",
							tag: "%" + args.tag + "%",
						},
						callback: load_suppliers,
					});
				} else if (args.supplier_group) {
					frappe.db
						.get_list("Supplier", {
							filters: { supplier_group: args.supplier_group },
							limit: 100,
							order_by: "name",
						})
						.then((r) => {
							load_suppliers({ message: r });
						});
				}
			},
		});

		dialog.show();
	}
};

// for backward compatibility: combine new and previous states
extend_cscript(cur_frm.cscript, new erpnext.buying.RequestforQuotationController({ frm: cur_frm }));

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
