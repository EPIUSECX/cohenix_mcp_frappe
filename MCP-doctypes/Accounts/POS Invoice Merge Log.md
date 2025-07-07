# Master Control Plan: `POS Invoice Merge Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `posting_date` | Posting Date | Date | None | ✅ |  |  | None | None |
| `posting_time` | Posting Time | Time | None | ✅ |  |  | None | None |
| `merge_invoices_based_on` | Merge Invoices Based On | Select | Customer
Customer Group | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `pos_closing_entry` | POS Closing Entry | Link | POS Closing Entry |  |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `pos_invoices` | POS Invoices | Table | POS Invoice Reference | ✅ |  |  | None | None |
| `references_section` | References | Section Break | None |  |  |  | None | None |
| `consolidated_invoice` | Consolidated Sales Invoice | Link | Sales Invoice |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `consolidated_credit_note` | Consolidated Credit Note | Link | Sales Invoice |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | POS Invoice Merge Log |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_invoice_merge_log/pos_invoice_merge_log.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("POS Invoice Merge Log", {
	setup: function (frm) {
		frm.set_query("pos_invoice", "pos_invoices", (doc) => {
			return {
				filters: {
					docstatus: 1,
					customer: doc.customer,
					consolidated_invoice: "",
				},
			};
		});
	},

	merge_invoices_based_on: function (frm) {
		frm.set_value("customer", "");
		frm.set_value("customer_group", "");
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
