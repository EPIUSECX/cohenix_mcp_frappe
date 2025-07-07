# Master Control Plan: `POS Profile`

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
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `country` | Country | Read Only | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Campaign |  |  |  | None | None |
| `company_address` | Company Address | Link | Address |  |  |  | None | None |
| `section_break_15` | Applicable for Users | Section Break | None |  |  |  | None | None |
| `applicable_for_users` | Applicable for Users | Table | POS Profile User |  |  |  | None | None |
| `section_break_11` | Payment Methods | Section Break | None |  |  |  | None | None |
| `payments` | Payment Methods | Table | POS Payment Method | ✅ |  |  | None | None |
| `section_break_14` | Configuration | Section Break | None |  |  |  | None | None |
| `hide_images` | Hide Images | Check | None |  |  |  | 0 | None |
| `hide_unavailable_items` | Hide Unavailable Items | Check | None |  |  |  | 0 | None |
| `auto_add_item_to_cart` | Automatically Add Filtered Item To Cart | Check | None |  |  |  | 0 | None |
| `validate_stock_on_save` | Validate Stock on Save | Check | None |  |  |  | 0 | None |
| `print_receipt_on_order_complete` | Print Receipt on Order Complete | Check | None |  |  |  | 0 | None |
| `action_on_new_invoice` | Action on New Invoice | Select | Always Ask
Save Changes and Load New Invoice
Discard Changes and Load New Invoice |  |  |  | Always Ask | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `update_stock` | Update Stock | Check | None |  | ✅ | ✅ | 1 | None |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `allow_rate_change` | Allow User to Edit Rate | Check | None |  |  |  | 0 | None |
| `allow_discount_change` | Allow User to Edit Discount | Check | None |  |  |  | 0 | None |
| `set_grand_total_to_default_mop` | Set Grand Total to Default Payment Method | Check | None |  |  |  | 1 | None |
| `allow_partial_payment` | Allow Partial Payment | Check | None |  |  |  | 0 | None |
| `section_break_23` | Filters | Section Break | None |  |  |  | None | None |
| `item_groups` | Item Groups | Table | POS Item Group |  |  |  | None | Only show Items from these Item Groups |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `customer_groups` | Customer Groups | Table | POS Customer Group |  |  |  | None | Only show Customer of these Customer Groups |
| `section_break_16` | Print Settings | Section Break | None |  |  |  | None | None |
| `print_format` | Print Format | Link | Print Format |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `tc_name` | Terms and Conditions | Link | Terms and Conditions |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `section_break_19` | Accounting | Section Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `write_off_account` | Write Off Account | Link | Account | ✅ |  |  | None | None |
| `write_off_cost_center` | Write Off Cost Center | Link | Cost Center | ✅ |  |  | None | None |
| `write_off_limit` | Write Off Limit | Currency | None | ✅ |  |  | 1 | Auto write off precision loss while consolidation |
| `account_for_change_amount` | Account for Change Amount | Link | Account |  |  |  | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | If enabled, the consolidated invoices will have rounded total disabled |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `income_account` | Income Account | Link | Account |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `taxes_and_charges` | Taxes and Charges | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `apply_discount_on` | Apply Discount On | Select | Grand Total
Net Total |  |  |  | Grand Total | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 22
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_profile/pos_profile.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt
frappe.ui.form.on("POS Profile", {
	setup: function (frm) {
		frm.set_query("selling_price_list", function () {
			return { filters: { selling: 1 } };
		});

		frm.set_query("tc_name", function () {
			return { filters: { selling: 1 } };
		});

		erpnext.queries.setup_queries(frm, "Warehouse", function () {
			return erpnext.queries.warehouse(frm.doc);
		});

		frm.set_query("print_format", function () {
			return {
				filters: [["Print Format", "doc_type", "=", "POS Invoice"]],
			};
		});

		frm.set_query("account_for_change_amount", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				filters: {
					account_type: ["in", ["Cash", "Bank"]],
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("taxes_and_charges", function () {
			return {
				filters: [
					["Sales Taxes and Charges Template", "company", "=", frm.doc.company],
					["Sales Taxes and Charges Template", "docstatus", "!=", 2],
				],
			};
		});

		frm.set_query("company_address", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				query: "frappe.contacts.doctype.address.address.address_query",
				filters: {
					link_doctype: "Company",
					link_name: doc.company,
				},
			};
		});

		frm.set_query("income_account", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				filters: {
					is_group: 0,
					company: doc.company,
					account_type: "Income Account",
				},
			};
		});

		frm.set_query("cost_center", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				filters: {
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("expense_account", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				filters: {
					report_type: "Profit and Loss",
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("select_print_heading", function () {
			return {
				filters: [["Print Heading", "docstatus", "!=", 2]],
			};
		});

		frm.set_query("write_off_account", function (doc) {
			return {
				filters: {
					report_type: "Profit and Loss",
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("write_off_cost_center", function (doc) {
			return {
				filters: {
					is_group: 0,
					company: doc.company,
				},
			};
		});

		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},

	refresh: function (frm) {
		if (frm.doc.company) {
			frm.trigger("toggle_display_account_head");
		}
	},

	company: function (frm) {
		frm.trigger("toggle_display_account_head");
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	toggle_display_account_head: function (frm) {
		frm.toggle_display("expense_account", erpnext.is_perpetual_inventory_enabled(frm.doc.company));
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
