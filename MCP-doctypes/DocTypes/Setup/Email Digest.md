# Master Control Plan: `Email Digest`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** Send regular summary reports via Email.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `settings` | Email Digest Settings | Section Break | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 0 | None |
| `company` | For Company | Link | Company | ✅ |  |  | None | None |
| `frequency` | How frequently? | Select | Daily
Weekly
Monthly | ✅ |  |  | None | None |
| `next_send` | Next email will be sent on: | Data | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `recipients` | Recipients | Table MultiSelect | Email Digest Recipient | ✅ |  |  | None | Note: Email will not be sent to disabled users |
| `accounts` | Accounts | Section Break | None |  |  |  | None | None |
| `accounts_module` | Profit & Loss | Column Break | None |  | ✅ |  | None | None |
| `income` | New Income | Check | None |  |  |  | 0 | None |
| `expenses_booked` | New Expenses | Check | None |  |  |  | 0 | None |
| `income_year_to_date` | Annual Income | Check | None |  |  |  | 0 | None |
| `expense_year_to_date` | Annual Expenses | Check | None |  |  |  | 0 | None |
| `column_break_16` | Balance Sheet | Column Break | None |  |  |  | None | None |
| `bank_balance` | Bank Balance | Check | None |  |  |  | 0 | None |
| `credit_balance` | Bank Credit Balance | Check | None |  |  |  | 0 | None |
| `invoiced_amount` | Receivables | Check | None |  |  |  | 0 | None |
| `payables` | Payables | Check | None |  |  |  | 0 | None |
| `work_in_progress` | Work in Progress | Column Break | None |  |  |  | None | None |
| `sales_orders_to_bill` | Sales Orders to Bill | Check | None |  |  |  | 0 | None |
| `purchase_orders_to_bill` | Purchase Orders to Bill | Check | None |  |  |  | 0 | None |
| `operation` | Operations | Section Break | None |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `sales_order` | New Sales Orders | Check | None |  |  |  | 0 | None |
| `purchase_order` | New Purchase Orders | Check | None |  |  |  | 0 | None |
| `sales_orders_to_deliver` | Sales Orders to Deliver | Check | None |  |  |  | 0 | None |
| `purchase_orders_to_receive` | Purchase Orders to Receive | Check | None |  |  |  | 0 | None |
| `sales_invoice` | New Sales Invoice | Check | None |  |  |  | 0 | None |
| `purchase_invoice` | New Purchase Invoice | Check | None |  |  |  | 0 | None |
| `column_break_operation` | None | Column Break | None |  |  |  | None | None |
| `new_quotations` | New Quotations | Check | None |  |  |  | 0 | None |
| `pending_quotations` | Open Quotations | Check | None |  |  |  | 0 | None |
| `issue` | Open Issues | Check | None |  |  |  | 0 | None |
| `project` | Open Projects | Check | None |  |  |  | 0 | None |
| `purchase_orders_items_overdue` | Purchase Orders Items Overdue | Check | None |  |  |  | 0 | None |
| `other` | Other | Section Break | None |  |  |  | None | None |
| `tools` | Tools | Column Break | None |  |  |  | None | None |
| `calendar_events` | Upcoming Calendar Events | Check | None |  |  |  | 0 | None |
| `todo_list` | Open To Do | Check | None |  |  |  | 0 | None |
| `notifications` | Open Notifications | Check | None |  |  |  | 0 | None |
| `column_break_32` |    | Column Break | None |  |  |  | None | None |
| `add_quote` | Add Quote | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/email_digest/email_digest.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Email Digest", {
	refresh: function (frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(__("View Now"), function () {
				frappe.call({
					method: "erpnext.setup.doctype.email_digest.email_digest.get_digest_msg",
					args: {
						name: frm.doc.name,
					},
					callback: function (r) {
						let d = new frappe.ui.Dialog({
							title: __("Email Digest: {0}", [frm.doc.name]),
							width: 800,
						});
						$(d.body).html(r.message);
						d.show();
					},
				});
			});

			frm.add_custom_button(__("Send Now"), function () {
				return frm.call("send", null, () => {
					frappe.show_alert({ message: __("Message Sent"), indicator: "green" });
				});
			});
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
