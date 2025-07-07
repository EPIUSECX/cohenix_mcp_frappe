# Master Control Plan: `Bank Account`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `account_name` | Account Name | Data | None | ✅ |  |  | None | None |
| `account` | Company Account | Link | Account |  |  |  | None | None |
| `bank` | Bank | Link | Bank | ✅ |  |  | None | None |
| `account_type` | Account Type | Link | Bank Account Type |  |  |  | None | None |
| `account_subtype` | Account Subtype | Link | Bank Account Subtype |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `is_default` | Is Default Account | Check | None |  |  |  | 0 | None |
| `is_company_account` | Is Company Account | Check | None |  |  |  | 0 | Setting the account as a Company Account is necessary for Bank Reconciliation |
| `company` | Company | Link | Company |  |  |  | None | None |
| `section_break_11` | Party Details | Section Break | None |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `account_details_section` | Account Details | Section Break | None |  |  |  | None | None |
| `iban` | IBAN | Data | None |  |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `branch_code` | Branch Code | Data | None |  |  |  | None | None |
| `bank_account_no` | Bank Account No | Data | None |  |  |  | None | None |
| `address_and_contact` | Address and Contact | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  |  | None | None |
| `integration_details_section` | Integration Details | Section Break | None |  |  |  | None | None |
| `integration_id` | Integration ID | Data | None |  | ✅ | ✅ | None | None |
| `last_integration_date` | Last Integration Date | Date | None |  |  |  | None | Change this date manually to setup the next synchronization start date |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `mask` | Mask | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_account/bank_account.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bank Account", {
	setup: function (frm) {
		frm.set_query("account", function () {
			return {
				filters: {
					account_type: "Bank",
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
		frm.set_query("party_type", function () {
			return {
				query: "erpnext.setup.doctype.party_type.party_type.get_party_type",
			};
		});
	},
	refresh: function (frm) {
		frappe.dynamic_link = { doc: frm.doc, fieldname: "name", doctype: "Bank Account" };

		frm.toggle_display(["address_html", "contact_html"], !frm.doc.__islocal);

		if (frm.doc.__islocal) {
			frappe.contacts.clear_address_and_contact(frm);
		} else {
			frappe.contacts.render_address_and_contact(frm);
		}

		if (frm.doc.integration_id) {
			frm.add_custom_button(__("Unlink external integrations"), function () {
				frappe.confirm(
					__(
						"This action will unlink this account from any external service integrating ERPNext with your bank accounts. It cannot be undone. Are you certain ?"
					),
					function () {
						frm.set_value("integration_id", "");
					}
				);
			});
		}
	},

	is_company_account: function (frm) {
		frm.set_df_property("account", "reqd", frm.doc.is_company_account);
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Account Balance` | Script Report | Accounts |



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
