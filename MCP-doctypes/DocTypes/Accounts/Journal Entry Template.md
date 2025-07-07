# Master Control Plan: `Journal Entry Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:template_title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `template_title` | Template Title | Data | None | ✅ |  |  | None | None |
| `voucher_type` | Journal Entry Type | Select | Journal Entry
Inter Company Journal Entry
Bank Entry
Cash Entry
Credit Card Entry
Debit Note
Credit Note
Contra Entry
Excise Entry
Write Off Entry
Opening Entry
Depreciation Entry
Exchange Rate Revaluation | ✅ |  |  | None | None |
| `naming_series` | Series | Select | None | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `is_opening` | Is Opening | Select | No
Yes |  |  |  | No | None |
| `multi_currency` | Multi Currency | Check | None |  |  |  | 0 | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `accounts` | Accounting Entries | Table | Journal Entry Template Account |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/journal_entry_template/journal_entry_template.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Journal Entry Template", {
	onload: function (frm) {
		if (frm.is_new()) {
			frappe.call({
				type: "GET",
				method: "erpnext.accounts.doctype.journal_entry_template.journal_entry_template.get_naming_series",
				callback: function (r) {
					if (r.message) {
						frm.set_df_property("naming_series", "options", r.message.split("\n"));
						frm.set_value("naming_series", r.message.split("\n")[0]);
						frm.refresh_field("naming_series");
					}
				},
			});
		}
	},
	refresh: function (frm) {
		frappe.model.set_default_values(frm.doc);

		frm.set_query("account", "accounts", function () {
			var filters = {
				company: frm.doc.company,
				is_group: 0,
			};

			if (!frm.doc.multi_currency) {
				$.extend(filters, {
					account_currency: [
						"in",
						[frappe.get_doc(":Company", frm.doc.company).default_currency, null],
					],
				});
			}

			return { filters: filters };
		});
	},
	voucher_type: function (frm) {
		var add_accounts = function (doc, r) {
			$.each(r, function (i, d) {
				var row = frappe.model.add_child(doc, "Journal Entry Template Account", "accounts");
				row.account = d.account;
			});
			refresh_field("accounts");
		};

		if (!frm.doc.company) return;

		frm.trigger("clear_child");
		switch (frm.doc.voucher_type) {
			case "Bank Entry":
			case "Cash Entry":
				frappe.call({
					type: "GET",
					method: "erpnext.accounts.doctype.journal_entry.journal_entry.get_default_bank_cash_account",
					args: {
						account_type:
							frm.doc.voucher_type == "Bank Entry"
								? "Bank"
								: frm.doc.voucher_type == "Cash Entry"
								? "Cash"
								: null,
						company: frm.doc.company,
					},
					callback: function (r) {
						if (r.message) {
							// If default company bank account not set
							if (!$.isEmptyObject(r.message)) {
								add_accounts(frm.doc, [r.message]);
							}
						}
					},
				});
				break;
			default:
				frm.trigger("clear_child");
		}
	},
	clear_child: function (frm) {
		frappe.model.clear_table(frm.doc, "accounts");
		frm.refresh_field("accounts");
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
