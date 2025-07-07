# Master Control Plan: `Process Statement Of Accounts`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `report` | Report | Select | General Ledger
Accounts Receivable | ✅ |  |  | None | None |
| `section_break_11` | Report Filters | Section Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  |  | Today | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `categorize_by` | Categorize By | Select | 
Categorize by Voucher
Categorize by Voucher (Consolidated) |  |  |  | Categorize by Voucher (Consolidated) | None |
| `cost_center` | Cost Center | Table MultiSelect | PSOA Cost Center |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `ignore_exchange_rate_revaluation_journals` | Ignore Exchange Rate Revaluation Journals | Check | None |  |  |  | 0 | None |
| `ignore_cr_dr_notes` | Ignore System Generated Credit / Debit Notes | Check | None |  |  |  | 0 | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `project` | Project | Table MultiSelect | PSOA Project |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `sales_person` | Sales Person | Link | Sales Person |  |  |  | None | None |
| `show_remarks` | Show Remarks | Check | None |  |  |  | 0 | None |
| `based_on_payment_terms` | Based On Payment Terms | Check | None |  |  |  | 0 | None |
| `section_break_3` | Customers | Section Break | None |  |  |  | None | None |
| `customer_collection` | Select Customers By | Select | 
Customer Group
Territory
Sales Partner
Sales Person |  |  |  | None | None |
| `collection_name` | Recipient | Dynamic Link | customer_collection |  |  |  | None | None |
| `fetch_customers` | Fetch Customers | Button | fetch_customers |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `primary_mandatory` | Send To Primary Contact | Check | None |  |  |  | 1 | A customer must have primary contact email. |
| `show_net_values_in_party_account` | Show Net Values in Party Account | Check | None |  |  |  | 0 | None |
| `column_break_17` | None | Section Break | None |  |  |  | None | None |
| `customers` | Customers | Table | Process Statement Of Accounts Customer | ✅ |  |  | None | None |
| `preferences` | Print Preferences | Section Break | None |  |  |  | None | None |
| `orientation` | Orientation | Select | Landscape
Portrait |  |  |  | None | None |
| `include_break` | Page Break After Each SoA | Check | None |  |  |  | 1 | None |
| `include_ageing` | Include Ageing Summary | Check | None |  |  |  | 0 | None |
| `ageing_based_on` | Ageing Based On | Select | Due Date
Posting Date |  |  |  | Due Date | None |
| `section_break_14` | None | Column Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `terms_and_conditions` | Terms and Conditions | Link | Terms and Conditions |  |  |  | None | None |
| `section_break_1` | Email Settings | Section Break | None |  |  |  | None | None |
| `enable_auto_email` | Enable Auto Email | Check | None |  |  |  | 0 | None |
| `column_break_ocfq` | None | Column Break | None |  |  |  | None | None |
| `sender` | Sender | Link | Email Account |  |  |  | None | None |
| `section_break_18` | None | Section Break | None |  |  |  | None | None |
| `frequency` | Frequency | Select | Weekly
Monthly
Quarterly |  |  |  | None | None |
| `filter_duration` | Filter Duration (Months) | Int | None |  |  |  | 1 | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | Today | None |
| `section_break_33` | None | Section Break | None |  |  |  | None | None |
| `pdf_name` | PDF Name | Data | None |  |  |  | None | None |
| `subject` | Subject | Data | None |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `cc_to` | CC To | Table MultiSelect | Process Statement Of Accounts CC |  |  |  | None | None |
| `section_break_30` | None | Section Break | None |  |  |  | None | None |
| `body` | Body | Text Editor | None |  |  |  | None | None |
| `help_text` | Help Text | HTML | <br>
<h4>Note</h4>
<ul>
<li>
You can use <a href="https://jinja.palletsprojects.com/en/2.11.x/" target="_blank">Jinja tags</a> in <b>Subject</b> and <b>Body</b> fields for dynamic values.
</li><li>
    All fields in this doctype are available under the <b>doc</b> object and all fields for the customer to whom the mail will go to is available under the  <b>customer</b> object.
</li></ul>
<h4> Examples</h4>
<!-- {% raw %} -->
<ul>
    <li><b>Subject</b>:<br><br><pre><code>Statement Of Accounts for {{ customer.customer_name }}</code></pre><br></li>
    <li><b>Body</b>: <br><br>
<pre><code>Hello {{ customer.customer_name }},<br>PFA your Statement Of Accounts from {{ doc.from_date }} to {{ doc.to_date }}.</code> </pre></li>
</ul>
<!-- {% endraw %} --> |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 11
- **Dynamic Link Fields:** 1
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_statement_of_accounts/process_statement_of_accounts.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Process Statement Of Accounts", {
	view_properties: function (frm) {
		frappe.route_options = { doc_type: "Customer" };
		frappe.set_route("Form", "Customize Form");
	},
	refresh: function (frm) {
		if (!frm.doc.__islocal) {
			frm.add_custom_button(__("Send Emails"), function () {
				if (frm.is_dirty()) frappe.throw(__("Please save before proceeding."));
				frappe.call({
					method: "erpnext.accounts.doctype.process_statement_of_accounts.process_statement_of_accounts.send_emails",
					args: {
						document_name: frm.doc.name,
					},
					callback: function (r) {
						if (r && r.message) {
							frappe.show_alert({ message: __("Emails Queued"), indicator: "blue" });
						} else {
							frappe.msgprint(__("No Records for these settings."));
						}
					},
				});
			});
			frm.add_custom_button(__("Download"), function () {
				if (frm.is_dirty()) frappe.throw(__("Please save before proceeding."));
				let url = frappe.urllib.get_full_url(
					"/api/method/erpnext.accounts.doctype.process_statement_of_accounts.process_statement_of_accounts.download_statements?" +
						"document_name=" +
						encodeURIComponent(frm.doc.name)
				);
				$.ajax({
					url: url,
					type: "GET",
					success: function (result) {
						if (jQuery.isEmptyObject(result)) {
							frappe.msgprint(__("No Records for these settings."));
						} else {
							window.location = url;
						}
					},
				});
			});
		}
	},
	onload: function (frm) {
		frm.set_query("currency", function () {
			return {
				filters: {
					enabled: 1,
				},
			};
		});
		frm.set_query("account", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
		frm.set_query("cost_center", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
		frm.set_query("project", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
		if (frm.doc.__islocal) {
			frm.set_value("from_date", frappe.datetime.add_months(frappe.datetime.get_today(), -1));
			frm.set_value("to_date", frappe.datetime.get_today());
		}
	},
	report: function (frm) {
		let filters = {
			company: frm.doc.company,
		};
		if (frm.doc.report == "Accounts Receivable") {
			filters["account_type"] = "Receivable";
		}
		frm.set_query("account", function () {
			return {
				filters: filters,
			};
		});
	},
	customer_collection: function (frm) {
		frm.set_value("collection_name", "");
		if (frm.doc.customer_collection) {
			frm.get_field("collection_name").set_label(frm.doc.customer_collection);
		}
	},
	frequency: function (frm) {
		if (frm.doc.frequency != "") {
			frm.set_value("start_date", frappe.datetime.get_today());
		} else {
			frm.set_value("start_date", "");
		}
	},
	fetch_customers: function (frm) {
		if (frm.doc.collection_name) {
			frappe.call({
				method: "erpnext.accounts.doctype.process_statement_of_accounts.process_statement_of_accounts.fetch_customers",
				args: {
					customer_collection: frm.doc.customer_collection,
					collection_name: frm.doc.collection_name,
					primary_mandatory: frm.doc.primary_mandatory,
				},
				callback: function (r) {
					if (!r.exc) {
						if (r.message.length) {
							frm.clear_table("customers");
							for (const customer of r.message) {
								var row = frm.add_child("customers");
								row.customer = customer.name;
								row.primary_email = customer.primary_email;
								row.billing_email = customer.billing_email;
							}
							frm.refresh_field("customers");
						} else {
							frappe.throw(__("No Customers found with selected options."));
						}
					}
				},
			});
		} else {
			frappe.throw("Enter " + frm.doc.customer_collection + " name.");
		}
	},
});

frappe.ui.form.on("Process Statement Of Accounts Customer", {
	customer: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (!row.customer) {
			return;
		}
		frappe.call({
			method: "erpnext.accounts.doctype.process_statement_of_accounts.process_statement_of_accounts.get_customer_emails",
			args: {
				customer_name: row.customer,
				primary_mandatory: frm.doc.primary_mandatory,
			},
			callback: function (r) {
				if (!r.exe) {
					if (r.message.length) {
						frappe.model.set_value(cdt, cdn, "primary_email", r.message[0]);
						frappe.model.set_value(cdt, cdn, "billing_email", r.message[1]);
					} else {
						return;
					}
				}
			},
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
