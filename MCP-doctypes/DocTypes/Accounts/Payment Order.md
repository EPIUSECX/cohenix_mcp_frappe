# Master Control Plan: `Payment Order`

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
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | PMO- | ✅ |  |  | PMO- | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `payment_order_type` | Payment Order Type | Select | 
Payment Request
Payment Entry | ✅ |  | ✅ | None | None |
| `party` | Supplier | Link | Supplier |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  |  | Today | None |
| `company_bank` | Bank | Link | Bank |  |  |  | None | None |
| `company_bank_account` | Company Bank Account | Link | Bank Account | ✅ |  |  | None | None |
| `account` | Account | Data | None |  |  |  | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `references` | Payment Order Reference | Table | Payment Order Reference | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Payment Order |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_order/payment_order.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Payment Order", {
	setup: function (frm) {
		frm.set_query("company_bank_account", function () {
			return {
				filters: {
					is_company_account: 1,
				},
			};
		});

		frm.set_df_property("references", "cannot_add_rows", true);
	},
	refresh: function (frm) {
		if (frm.doc.docstatus == 0) {
			frm.add_custom_button(
				__("Payment Request"),
				function () {
					frm.trigger("get_from_payment_request");
				},
				__("Get Payments from")
			);

			frm.add_custom_button(
				__("Payment Entry"),
				function () {
					frm.trigger("get_from_payment_entry");
				},
				__("Get Payments from")
			);

			frm.trigger("remove_button");
		}

		// payment Entry
		if (frm.doc.docstatus === 1 && frm.doc.payment_order_type === "Payment Request") {
			frm.add_custom_button(__("Create Journal Entries"), function () {
				frm.trigger("make_payment_records");
			});
		}
	},

	remove_row_if_empty: function (frm) {
		// remove if first row is empty
		if (frm.doc.references.length > 0 && !frm.doc.references[0].reference_name) {
			frm.doc.references = [];
		}
	},

	remove_button: function (frm) {
		// remove custom button of order type that is not imported

		let label = ["Payment Request", "Payment Entry"];

		if (frm.doc.references.length > 0 && frm.doc.payment_order_type) {
			label = label.reduce((x) => {
				x != frm.doc.payment_order_type;
				return x;
			});
			frm.remove_custom_button(label, "Get from");
		}
	},

	get_from_payment_entry: function (frm) {
		frm.trigger("remove_row_if_empty");
		erpnext.utils.map_current_doc({
			method: "erpnext.accounts.doctype.payment_entry.payment_entry.make_payment_order",
			source_doctype: "Payment Entry",
			target: frm,
			date_field: "posting_date",
			setters: {
				party_type: "Supplier",
				party: frm.doc.supplier || "",
			},
			get_query_filters: {
				bank: frm.doc.bank,
				docstatus: 1,
				payment_type: ["!=", "Receive"],
				bank_account: frm.doc.company_bank_account,
				paid_from: frm.doc.account,
				payment_order_status: ["=", "Initiated"],
			},
		});
	},

	get_from_payment_request: function (frm) {
		frm.trigger("remove_row_if_empty");
		erpnext.utils.map_current_doc({
			method: "erpnext.accounts.doctype.payment_request.payment_request.make_payment_order",
			source_doctype: "Payment Request",
			target: frm,
			setters: {
				party_type: "Supplier",
				party: frm.doc.supplier || "",
			},
			get_query_filters: {
				bank: frm.doc.bank,
				docstatus: 1,
				status: ["=", "Initiated"],
			},
		});
	},

	make_payment_records: function (frm) {
		var dialog = new frappe.ui.Dialog({
			title: __("For Supplier"),
			fields: [
				{
					fieldtype: "Link",
					label: __("Supplier"),
					fieldname: "supplier",
					options: "Supplier",
					get_query: function () {
						return {
							query: "erpnext.accounts.doctype.payment_order.payment_order.get_supplier_query",
							filters: { parent: frm.doc.name },
						};
					},
					reqd: 1,
				},

				{
					fieldtype: "Link",
					label: __("Mode of Payment"),
					fieldname: "mode_of_payment",
					options: "Mode of Payment",
					get_query: function () {
						return {
							query: "erpnext.accounts.doctype.payment_order.payment_order.get_mop_query",
							filters: { parent: frm.doc.name },
						};
					},
				},
			],
		});

		dialog.set_primary_action(__("Submit"), function () {
			var args = dialog.get_values();
			if (!args) return;

			return frappe.call({
				method: "erpnext.accounts.doctype.payment_order.payment_order.make_payment_records",
				args: {
					name: frm.doc.name,
					supplier: args.supplier,
					mode_of_payment: args.mode_of_payment,
				},
				freeze: true,
				callback: function (r) {
					dialog.hide();
					frm.refresh();
				},
			});
		});

		dialog.show();
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
