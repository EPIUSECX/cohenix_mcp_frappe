# Master Control Plan: `Lead`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | CRM-LEAD-.YYYY.- |  |  |  | None | None |
| `salutation` | Salutation | Link | Salutation |  |  |  | None | None |
| `first_name` | First Name | Data | None |  |  |  | None | None |
| `middle_name` | Middle Name | Data | None |  |  |  | None | None |
| `last_name` | Last Name | Data | None |  |  |  | None | None |
| `column_break_1` | None | Column Break | None |  |  |  | None | None |
| `lead_name` | Full Name | Data | None |  |  | ✅ | None | None |
| `job_title` | Job Title | Data | None |  |  |  | None | None |
| `gender` | Gender | Link | Gender |  |  |  | None | None |
| `col_break123` | None | Column Break | None |  |  |  | None | None |
| `lead_owner` | Lead Owner | Link | User |  |  |  | __user | None |
| `status` | Status | Select | Lead
Open
Replied
Opportunity
Quotation
Lost Quotation
Interested
Converted
Do Not Contact | ✅ |  |  | Lead | None |
| `customer` | From Customer | Link | Customer |  |  |  | None | None |
| `type` | Lead Type | Select | 
Client
Channel Partner
Consultant |  |  |  | None | None |
| `request_type` | Request Type | Select | 
Product Enquiry
Request for Information
Suggestions
Other |  |  |  | None | None |
| `contact_info_tab` | Contact Info | Section Break | None |  |  |  | None | None |
| `email_id` | Email | Data | Email |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `mobile_no` | Mobile No | Data | Phone |  |  |  | None | None |
| `whatsapp_no` | WhatsApp | Data | Phone |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `phone` | Phone | Data | Phone |  |  |  | None | None |
| `phone_ext` | Phone Ext. | Data | None |  |  |  | None | None |
| `organization_section` | Organization | Section Break | None |  |  |  | None | None |
| `company_name` | Organization Name | Data | None |  |  |  | None | None |
| `no_of_employees` | No of Employees | Select | 1-10
11-50
51-200
201-500
501-1000
1000+ |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `annual_revenue` | Annual Revenue | Currency | None |  |  |  | None | None |
| `industry` | Industry | Link | Industry Type |  |  |  | None | None |
| `market_segment` | Market Segment | Link | Market Segment |  |  |  | None | None |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `fax` | Fax | Data | None |  |  |  | None | None |
| `address_section` | Address & Contacts | Section Break | None |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  | ✅ | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `city` | City | Data | None |  |  |  | None | None |
| `state` | State/Province | Data | None |  |  |  | None | None |
| `country` | Country | Link | Country |  |  |  | None | None |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  | ✅ | None | None |
| `section_break_analytics` | Analytics | Section Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `column_break_gkxo` | None | Column Break | None |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `column_break_gqka` | None | Column Break | None |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `qualification_tab` | Qualification | Section Break | None |  |  |  | None | None |
| `qualification_status` | Qualification Status | Select | Unqualified
In Process
Qualified |  |  |  | None | None |
| `column_break_64` | None | Column Break | None |  |  |  | None | None |
| `qualified_by` | Qualified By | Link | User |  |  |  | None | None |
| `qualified_on` | Qualified on | Date | None |  |  |  | None | None |
| `other_info_tab` | Additional Information | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `title` | Title | Data | None |  | ✅ | ✅ | None | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `unsubscribed` | Unsubscribed | Check | None |  |  |  | 0 | None |
| `blog_subscriber` | Blog Subscriber | Check | None |  |  |  | 0 | None |
| `activities_tab` | Activities | Tab Break | None |  |  |  | None | None |
| `open_activities_html` | Open Activities HTML | HTML | None |  |  |  | None | None |
| `all_activities_section` | All Activities | Section Break | None |  |  |  | None | None |
| `all_activities_html` | All Activities HTML | HTML | None |  |  |  | None | None |
| `notes_tab` | Notes | Tab Break | None |  |  |  | None | None |
| `notes_html` | Notes HTML | HTML | None |  |  |  | None | None |
| `notes` | Notes | Table | CRM Note |  | ✅ |  | None | None |
| `dashboard_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 14
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/lead/lead.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext");
cur_frm.email_field = "email_id";

erpnext.LeadController = class LeadController extends frappe.ui.form.Controller {
	setup() {
		this.frm.make_methods = {
			Customer: this.make_customer.bind(this),
			Quotation: this.make_quotation.bind(this),
			Opportunity: this.make_opportunity.bind(this),
		};

		// For avoiding integration issues.
		this.frm.set_df_property("first_name", "reqd", true);
	}

	onload() {
		this.frm.set_query("lead_owner", function (doc, cdt, cdn) {
			return { query: "frappe.core.doctype.user.user.user_query" };
		});
	}

	refresh() {
		var me = this;
		let doc = this.frm.doc;
		erpnext.toggle_naming_series();

		if (!this.frm.is_new() && doc.__onload && !doc.__onload.is_customer) {
			this.frm.add_custom_button(__("Customer"), this.make_customer.bind(this), __("Create"));
			this.frm.add_custom_button(__("Opportunity"), this.make_opportunity.bind(this), __("Create"));
			this.frm.add_custom_button(__("Quotation"), this.make_quotation.bind(this), __("Create"));
			if (!doc.__onload.linked_prospects.length) {
				this.frm.add_custom_button(__("Prospect"), this.make_prospect.bind(this), __("Create"));
				this.frm.add_custom_button(
					__("Add to Prospect"),
					() => {
						this.add_lead_to_prospect(this.frm);
					},
					__("Action")
				);
			}
		}

		if (!this.frm.is_new()) {
			frappe.contacts.render_address_and_contact(this.frm);
		} else {
			frappe.contacts.clear_address_and_contact(this.frm);
		}

		this.show_notes();
		this.show_activities();
	}

	add_lead_to_prospect(frm) {
		frappe.prompt(
			[
				{
					fieldname: "prospect",
					label: __("Prospect"),
					fieldtype: "Link",
					options: "Prospect",
					reqd: 1,
				},
			],
			function (data) {
				frappe.call({
					method: "erpnext.crm.doctype.lead.lead.add_lead_to_prospect",
					args: {
						lead: frm.doc.name,
						prospect: data.prospect,
					},
					callback: function (r) {
						if (!r.exc) {
							frm.reload_doc();
						}
					},
					freeze: true,
					freeze_message: __("Adding Lead to Prospect..."),
				});
			},
			__("Add Lead to Prospect"),
			__("Add")
		);
	}

	make_customer() {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.lead.lead.make_customer",
			frm: this.frm,
		});
	}

	make_quotation() {
		frappe.model.open_mapped_doc({
			method: "erpnext.crm.doctype.lead.lead.make_quotation",
			frm: this.frm,
		});
	}

	async make_opportunity() {
		const frm = this.frm;
		let existing_prospect = (
			await frappe.db.get_value(
				"Prospect Lead",
				{
					lead: frm.doc.name,
				},
				"name",
				null,
				"Prospect"
			)
		).message?.name;

		let fields = [];
		if (!existing_prospect) {
			fields.push(
				{
					label: "Create Prospect",
					fieldname: "create_prospect",
					fieldtype: "Check",
					default: 1,
				},
				{
					label: "Prospect Name",
					fieldname: "prospect_name",
					fieldtype: "Data",
					default: frm.doc.company_name,
					depends_on: "create_prospect",
					mandatory_depends_on: "create_prospect",
				}
			);
		}

		await frm.reload_doc();

		let existing_contact = (
			await frappe.db.get_value(
				"Contact",
				{
					first_name: frm.doc.first_name || frm.doc.lead_name,
					last_name: frm.doc.last_name,
				},
				"name"
			)
		).message?.name;

		if (!existing_contact) {
			fields.push({
				label: "Create Contact",
				fieldname: "create_contact",
				fieldtype: "Check",
				default: "1",
			});
		}

		if (fields.length) {
			const d = new frappe.ui.Dialog({
				title: __("Create Opportunity"),
				fields: fields,
				primary_action: function (data) {
					frappe.call({
						method: "create_prospect_and_contact",
						doc: frm.doc,
						args: {
							data: data,
						},
						freeze: true,
						callback: function (r) {
							if (!r.exc) {
								frappe.model.open_mapped_doc({
									method: "erpnext.crm.doctype.lead.lead.make_opportunity",
									frm: frm,
								});
							}
							d.hide();
						},
					});
				},
				primary_action_label: __("Create"),
			});
			d.show();
		} else {
			frappe.model.open_mapped_doc({
				method: "erpnext.crm.doctype.lead.lead.make_opportunity",
				frm: frm,
			});
		}
	}

	make_prospect() {
		const me = this;
		frappe.model.with_doctype("Prospect", function () {
			let prospect = frappe.model.get_new_doc("Prospect");
			prospect.company_name = me.frm.doc.company_name;
			prospect.no_of_employees = me.frm.doc.no_of_employees;
			prospect.industry = me.frm.doc.industry;
			prospect.market_segment = me.frm.doc.market_segment;
			prospect.territory = me.frm.doc.territory;
			prospect.fax = me.frm.doc.fax;
			prospect.website = me.frm.doc.website;
			prospect.prospect_owner = me.frm.doc.lead_owner;
			prospect.notes = me.frm.doc.notes;

			let leads_row = frappe.model.add_child(prospect, "leads");
			leads_row.lead = me.frm.doc.name;

			frappe.set_route("Form", "Prospect", prospect.name);
		});
	}

	company_name() {
		if (!this.frm.doc.lead_name) {
			this.frm.set_value("lead_name", this.frm.doc.company_name);
		}
	}

	show_notes() {
		if (this.frm.doc.docstatus == 1) return;

		const crm_notes = new erpnext.utils.CRMNotes({
			frm: this.frm,
			notes_wrapper: $(this.frm.fields_dict.notes_html.wrapper),
		});
		crm_notes.refresh();
	}

	show_activities() {
		if (this.frm.doc.docstatus == 1) return;

		const crm_activities = new erpnext.utils.CRMActivities({
			frm: this.frm,
			open_activities_wrapper: $(this.frm.fields_dict.open_activities_html.wrapper),
			all_activities_wrapper: $(this.frm.fields_dict.all_activities_html.wrapper),
			form_wrapper: $(this.frm.wrapper),
		});
		crm_activities.refresh();
	}
};

extend_cscript(cur_frm.cscript, new erpnext.LeadController({ frm: cur_frm }));

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Lead Owner Efficiency` | Script Report | CRM |
| `Campaign Efficiency` | Script Report | CRM |
| `Prospects Engaged But Not Converted` | Script Report | CRM |
| `Lead Details` | Script Report | CRM |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Lead Source` | Lead Source | Group By | CRM |
| `Incoming Leads` | Incoming Leads | Count | CRM |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `New Lead (Last 1 Month)` | New Lead (Last 1 Month) | Count | CRM |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
