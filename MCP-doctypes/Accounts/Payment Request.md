# Master Control Plan: `Payment Request`

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
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `payment_request_type` | Payment Request Type | Select | Outward
Inward | ✅ |  |  | Inward | None |
| `transaction_date` | Transaction Date | Date | None |  |  |  | None | None |
| `failed_reason` | Reason for Failure | Data | None |  | ✅ | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | ACC-PRQ-.YYYY.- | ✅ |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `party_details` | Party Details | Section Break | None |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `party_name` | Party Name | Data | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Doctype | Link | DocType |  |  | ✅ | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_doctype |  |  | ✅ | None | None |
| `transaction_details` | Transaction Details | Section Break | None |  |  |  | None | None |
| `grand_total` | Amount | Currency | currency | ✅ |  |  | None | Amount in transaction currency |
| `currency` | Transaction Currency | Link | Currency |  |  | ✅ | None | None |
| `is_a_subscription` | Is a Subscription | Check | None |  |  |  | 0 | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `outstanding_amount` | Outstanding Amount | Currency | party_account_currency |  |  | ✅ | None | Amount in party's bank account currency |
| `party_account_currency` | Party Account Currency | Link | Currency |  |  | ✅ | None | None |
| `subscription_section` | Subscription Section | Section Break | None |  |  |  | None | None |
| `subscription_plans` | Subscription Plans | Table | Subscription Plan Detail |  |  |  | None | None |
| `bank_account_details` | Bank Account Details | Section Break | None |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | None |
| `bank` | Bank | Link | Bank |  |  | ✅ | None | None |
| `bank_account_no` | Bank Account No | Read Only | None |  |  |  | None | None |
| `account` | Account | Read Only | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `iban` | IBAN | Read Only | None |  |  |  | None | None |
| `branch_code` | Branch Code | Read Only | None |  |  |  | None | None |
| `swift_number` | SWIFT Number | Read Only | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `recipient_and_message` | Recipient Message And Payment Details | Section Break | None |  |  |  | None | None |
| `print_format` | Print Format | Select | None |  |  |  | None | None |
| `email_to` | To | Data | None |  |  |  | None | None |
| `subject` | Subject | Data | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `payment_gateway_account` | Payment Gateway Account | Link | Payment Gateway Account |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Requested
Initiated
Partially Paid
Payment Ordered
Paid
Failed
Cancelled |  | ✅ | ✅ | Draft | None |
| `make_sales_invoice` | Make Sales Invoice | Check | None |  | ✅ | ✅ | 0 | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `message` | Message | Text | None |  |  |  | None | None |
| `message_examples` | Message Examples | HTML | <pre><h5>Message Example</h5>

&lt;p&gt;Dear {{ doc.contact_person }},&lt;/p&gt;

&lt;p&gt;Requesting payment for {{ doc.doctype }}, {{ doc.name }} for {{ doc.grand_total }}.&lt;/p&gt;

&lt;a href="{{ payment_url }}"&gt; click here to pay &lt;/a&gt;

</pre>
 |  |  |  | None | None |
| `mute_email` | Mute Email | Check | None |  | ✅ | ✅ | 0 | None |
| `section_break_7` | Payment Gateway Details | Section Break | None |  |  |  | None | None |
| `payment_gateway` | Payment Gateway | Read Only | None |  |  |  | None | None |
| `payment_account` | Payment Account | Read Only | None |  |  | ✅ | None | None |
| `payment_channel` | Payment Channel | Select | 
Email
Phone
Other |  |  | ✅ | None | None |
| `payment_order` | Payment Order | Link | Payment Order |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Payment Request |  |  | ✅ | None | None |
| `column_break_pnyv` | None | Column Break | None |  |  |  | None | None |
| `payment_url` | Payment URL | Data | URL |  |  | ✅ | None | None |
| `column_break_iiuv` | None | Column Break | None |  |  |  | None | None |
| `phone_number` | Phone Number | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 13
- **Dynamic Link Fields:** 2
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_request/payment_request.js`
```javascript
cur_frm.add_fetch("payment_gateway_account", "payment_account", "payment_account");
cur_frm.add_fetch("payment_gateway_account", "payment_gateway", "payment_gateway");
cur_frm.add_fetch("payment_gateway_account", "message", "message");

frappe.ui.form.on("Payment Request", {
	setup: function (frm) {
		frm.set_query("party_type", function () {
			return {
				query: "erpnext.setup.doctype.party_type.party_type.get_party_type",
			};
		});
	},
});

frappe.ui.form.on("Payment Request", "onload", function (frm, dt, dn) {
	if (frm.doc.reference_doctype) {
		frappe.call({
			method: "erpnext.accounts.doctype.payment_request.payment_request.get_print_format_list",
			args: { ref_doctype: frm.doc.reference_doctype },
			callback: function (r) {
				set_field_options("print_format", r.message["print_format"]);
			},
		});
	}
});

frappe.ui.form.on("Payment Request", "refresh", function (frm) {
	if (frm.doc.status == "Failed") {
		frm.set_intro(__("Failure: {0}", [frm.doc.failed_reason]), "red");
	}

	if (
		frm.doc.payment_request_type == "Inward" &&
		frm.doc.payment_channel !== "Phone" &&
		!["Initiated", "Paid"].includes(frm.doc.status) &&
		!frm.doc.__islocal &&
		frm.doc.docstatus == 1
	) {
		frm.add_custom_button(__("Resend Payment Email"), function () {
			frappe.call({
				method: "erpnext.accounts.doctype.payment_request.payment_request.resend_payment_email",
				args: { docname: frm.doc.name },
				freeze: true,
				freeze_message: __("Sending"),
				callback: function (r) {
					if (!r.exc) {
						frappe.msgprint(__("Message Sent"));
					}
				},
			});
		});
	}

	if (
		frm.doc.payment_request_type == "Outward" &&
		["Initiated", "Partially Paid"].includes(frm.doc.status)
	) {
		frm.add_custom_button(__("Create Payment Entry"), function () {
			frappe.call({
				method: "erpnext.accounts.doctype.payment_request.payment_request.make_payment_entry",
				args: { docname: frm.doc.name },
				freeze: true,
				callback: function (r) {
					if (!r.exc) {
						var doc = frappe.model.sync(r.message);
						frappe.set_route("Form", r.message.doctype, r.message.name);
					}
				},
			});
		}).addClass("btn-primary");
	}
});

frappe.ui.form.on("Payment Request", "is_a_subscription", function (frm) {
	frm.toggle_reqd("payment_gateway_account", frm.doc.is_a_subscription);
	frm.toggle_reqd("subscription_plans", frm.doc.is_a_subscription);

	if (frm.doc.is_a_subscription && frm.doc.reference_doctype && frm.doc.reference_name) {
		frappe.call({
			method: "erpnext.accounts.doctype.payment_request.payment_request.get_subscription_details",
			args: { reference_doctype: frm.doc.reference_doctype, reference_name: frm.doc.reference_name },
			freeze: true,
			callback: function (data) {
				if (!data.exc) {
					$.each(data.message || [], function (i, v) {
						var d = frappe.model.add_child(
							frm.doc,
							"Subscription Plan Detail",
							"subscription_plans"
						);
						d.qty = v.qty;
						d.plan = v.plan;
					});
					frm.refresh_field("subscription_plans");
				}
			},
		});
	}
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
