# Master Control Plan: `Import Supplier Invoice`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Regional`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `invoice_series` | Invoice Series | Select | ACC-PINV-.YYYY.- | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `supplier_group` | Supplier Group | Link | Supplier Group | ✅ |  |  | None | None |
| `tax_account` | Tax Account | Link | Account | ✅ |  |  | None | None |
| `default_buying_price_list` | Default Buying Price List | Link | Price List | ✅ |  |  | None | None |
| `upload_xml_invoices_section` | Upload XML Invoices | Section Break | None |  |  |  | None | None |
| `zip_file` | Zip File | Attach | None |  |  |  | None | None |
| `import_invoices` | Import Invoices | Button | process_file_data |  |  |  | None | Click on Import Invoices button once the zip file has been attached to the document. Any errors related to processing will be shown in the Error Log. |
| `status` | Status | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/regional/doctype/import_supplier_invoice/import_supplier_invoice.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Import Supplier Invoice", {
	onload: function (frm) {
		frappe.realtime.on("import_invoice_update", function (data) {
			frm.dashboard.show_progress(data.title, (data.count / data.total) * 100, data.message);
			if (data.count == data.total) {
				window.setTimeout((title) => frm.dashboard.hide_progress(title), 1500, data.title);
			}
		});
	},
	setup: function (frm) {
		frm.set_query("tax_account", function (doc) {
			return {
				filters: {
					account_type: "Tax",
					company: doc.company,
				},
			};
		});

		frm.set_query("default_buying_price_list", function (doc) {
			return {
				filters: {
					currency: frappe.get_doc(":Company", doc.company).default_currency,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.trigger("toggle_read_only_fields");
	},

	toggle_read_only_fields: function (frm) {
		if (["File Import Completed", "Processing File Data"].includes(frm.doc.status)) {
			cur_frm.set_read_only();
			frm.set_df_property("import_invoices", "hidden", 1);
		} else {
			frm.set_df_property("import_invoices", "hidden", 0);
		}
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
