# Master Control Plan: `Account`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Heads (or groups) against which Accounting Entries are made and balances are maintained.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `properties` | None | Section Break | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disable | Check | None |  |  |  | 0 | None |
| `account_name` | Account Name | Data | None | ✅ |  |  | None | None |
| `account_number` | Account Number | Data | None |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `root_type` | Root Type | Select | 
Asset
Liability
Income
Expense
Equity |  |  | ✅ | None | None |
| `report_type` | Report Type | Select | 
Balance Sheet
Profit and Loss |  |  | ✅ | None | None |
| `account_currency` | Currency | Link | Currency |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `parent_account` | Parent Account | Link | Account | ✅ |  |  | None | None |
| `account_type` | Account Type | Select | 
Accumulated Depreciation
Asset Received But Not Billed
Bank
Cash
Chargeable
Capital Work in Progress
Cost of Goods Sold
Current Asset
Current Liability
Depreciation
Direct Expense
Direct Income
Equity
Expense Account
Expenses Included In Asset Valuation
Expenses Included In Valuation
Fixed Asset
Income Account
Indirect Expense
Indirect Income
Liability
Payable
Receivable
Round Off
Round Off for Opening
Stock
Stock Adjustment
Stock Received But Not Billed
Service Received But Not Billed
Tax
Temporary |  |  |  | None | Setting Account Type helps in selecting this Account in transactions. |
| `tax_rate` | Tax Rate | Float | None |  |  |  | None | Rate at which this tax is applied |
| `freeze_account` | Frozen | Select | No
Yes |  |  |  | None | If the account is frozen, entries are allowed to restricted users. |
| `balance_must_be` | Balance must be | Select | 
Debit
Credit |  |  |  | None | None |
| `lft` | Lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | Rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Data | None |  | ✅ | ✅ | None | None |
| `include_in_gross` | Include in gross | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/account/account.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Account", {
	setup: function (frm) {
		frm.add_fetch("parent_account", "report_type", "report_type");
		frm.add_fetch("parent_account", "root_type", "root_type");
	},
	onload: function (frm) {
		frm.set_query("parent_account", function (doc) {
			return {
				filters: {
					is_group: 1,
					company: doc.company,
				},
			};
		});
	},
	refresh: function (frm) {
		frm.toggle_display("account_name", frm.is_new());

		// hide fields if group
		frm.toggle_display(["tax_rate"], cint(frm.doc.is_group) == 0);

		frm.toggle_enable(["is_group", "company", "account_number"], frm.is_new());

		if (cint(frm.doc.is_group) == 0) {
			frm.toggle_display("freeze_account", frm.doc.__onload && frm.doc.__onload.can_freeze_account);
		}

		// read-only for root accounts
		if (!frm.is_new()) {
			if (!frm.doc.parent_account) {
				frm.set_read_only();
				frm.set_intro(__("This is a root account and cannot be edited."));
			} else {
				// credit days and type if customer or supplier
				frm.set_intro(null);
				frm.trigger("account_type");
				// show / hide convert buttons
				frm.trigger("add_toolbar_buttons");
			}
			if (frm.has_perm("write")) {
				frm.add_custom_button(
					__("Merge Account"),
					function () {
						frm.trigger("merge_account");
					},
					__("Actions")
				);
				frm.add_custom_button(
					__("Update Account Name / Number"),
					function () {
						frm.trigger("update_account_number");
					},
					__("Actions")
				);
			}
		}
	},
	account_type: function (frm) {
		if (frm.doc.is_group == 0) {
			frm.toggle_display(["tax_rate"], frm.doc.account_type == "Tax");
			frm.toggle_display("warehouse", frm.doc.account_type == "Stock");
		}
	},
	add_toolbar_buttons: function (frm) {
		frm.add_custom_button(
			__("Chart of Accounts"),
			() => {
				frappe.set_route("Tree", "Account");
			},
			__("View")
		);

		if (frm.doc.is_group == 1) {
			frm.add_custom_button(
				__("Convert to Non-Group"),
				function () {
					return frappe.call({
						doc: frm.doc,
						method: "convert_group_to_ledger",
						callback: function () {
							frm.refresh();
						},
					});
				},
				__("Actions")
			);
		} else if (cint(frm.doc.is_group) == 0 && frappe.boot.user.can_read.indexOf("GL Entry") !== -1) {
			frm.add_custom_button(
				__("General Ledger"),
				function () {
					frappe.route_options = {
						account: frm.doc.name,
						from_date: erpnext.utils.get_fiscal_year(frappe.datetime.get_today(), true)[1],
						to_date: erpnext.utils.get_fiscal_year(frappe.datetime.get_today(), true)[2],
						company: frm.doc.company,
					};
					frappe.set_route("query-report", "General Ledger");
				},
				__("View")
			);

			frm.add_custom_button(
				__("Convert to Group"),
				function () {
					return frappe.call({
						doc: frm.doc,
						method: "convert_ledger_to_group",
						callback: function () {
							frm.refresh();
						},
					});
				},
				__("Actions")
			);
		}
	},

	merge_account: function (frm) {
		var d = new frappe.ui.Dialog({
			title: __("Merge with Existing Account"),
			fields: [
				{
					label: "Name",
					fieldname: "name",
					fieldtype: "Data",
					reqd: 1,
					default: frm.doc.name,
				},
			],
			primary_action: function () {
				var data = d.get_values();
				frappe.call({
					method: "erpnext.accounts.doctype.account.account.merge_account",
					args: {
						old: frm.doc.name,
						new: data.name,
					},
					callback: function (r) {
						if (!r.exc) {
							if (r.message) {
								frappe.set_route("Form", "Account", r.message);
							}
							d.hide();
						}
					},
				});
			},
			primary_action_label: __("Merge"),
		});
		d.show();
	},

	update_account_number: function (frm) {
		var d = new frappe.ui.Dialog({
			title: __("Update Account Number / Name"),
			fields: [
				{
					label: "Account Name",
					fieldname: "account_name",
					fieldtype: "Data",
					reqd: 1,
					default: frm.doc.account_name,
				},
				{
					label: "Account Number",
					fieldname: "account_number",
					fieldtype: "Data",
					default: frm.doc.account_number,
				},
			],
			primary_action: function () {
				var data = d.get_values();
				if (
					data.account_number === frm.doc.account_number &&
					data.account_name === frm.doc.account_name
				) {
					d.hide();
					return;
				}

				frappe.call({
					method: "erpnext.accounts.doctype.account.account.update_account_number",
					args: {
						account_number: data.account_number,
						account_name: data.account_name,
						name: frm.doc.name,
					},
					callback: function (r) {
						if (!r.exc) {
							if (r.message) {
								frappe.set_route("Form", "Account", r.message);
							} else {
								frm.set_value("account_number", data.account_number);
								frm.set_value("account_name", data.account_name);
							}
							d.hide();
						}
					},
				});
			},
			primary_action_label: __("Update"),
		});
		d.show();
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Financial Ratios` | Script Report | Accounts |
| `Consolidated Financial Statement` | Script Report | Accounts |



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
