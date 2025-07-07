# Master Control Plan: `Period Closing Voucher`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `ACC-PCV-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `transaction_date` | Transaction Date | Date | None |  |  |  | Today | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `fiscal_year` | Fiscal Year | Link | Fiscal Year | ✅ |  |  | None | None |
| `period_start_date` | Period Start Date | Date | None | ✅ |  |  | None | None |
| `period_end_date` | Period End Date | Date | None | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Period Closing Voucher |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `closing_account_head` | Closing Account Head | Link | Account | ✅ |  |  | None | The account head under Liability or Equity, in which Profit/Loss will be booked |
| `gle_processing_status` | GL Entry Processing Status | Select | In Progress
Completed
Failed |  |  | ✅ | None | None |
| `remarks` | Remarks | Small Text | None | ✅ |  |  | None | None |
| `error_message` | Error Message | Text | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/period_closing_voucher/period_closing_voucher.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Period Closing Voucher", {
	onload: function (frm) {
		if (!frm.doc.transaction_date) frm.doc.transaction_date = frappe.datetime.obj_to_str(new Date());
	},

	setup: function (frm) {
		frm.set_query("closing_account_head", function () {
			return {
				filters: [
					["Account", "company", "=", frm.doc.company],
					["Account", "is_group", "=", "0"],
					["Account", "freeze_account", "=", "No"],
					["Account", "root_type", "in", "Liability, Equity"],
				],
			};
		});
	},

	fiscal_year: function (frm) {
		if (frm.doc.fiscal_year) {
			frappe.call({
				method: "erpnext.accounts.doctype.period_closing_voucher.period_closing_voucher.get_period_start_end_date",
				args: {
					fiscal_year: frm.doc.fiscal_year,
					company: frm.doc.company,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("period_start_date", r.message[0]);
						frm.set_value("period_end_date", r.message[1]);
					}
				},
			});
		}
	},

	refresh: function (frm) {
		if (frm.doc.docstatus > 0) {
			frm.add_custom_button(
				__("Ledger"),
				function () {
					frappe.route_options = {
						voucher_no: frm.doc.name,
						from_date: frm.doc.posting_date,
						to_date: moment(frm.doc.modified).format("YYYY-MM-DD"),
						company: frm.doc.company,
						categorize_by: "",
						show_cancelled_entries: frm.doc.docstatus === 2,
					};
					frappe.set_route("query-report", "General Ledger");
				},
				"fa fa-table"
			);
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
