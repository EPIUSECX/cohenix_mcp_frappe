# Master Control Plan: `Loyalty Program`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:loyalty_program_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `loyalty_program_name` | Loyalty Program Name | Data | None | ✅ |  |  | None | None |
| `loyalty_program_type` | Loyalty Program Type | Select | Single Tier Program
Multiple Tier Program |  |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `customer_territory` | Customer Territory | Link | Territory |  |  |  | None | None |
| `auto_opt_in` | Auto Opt In (For all customers) | Check | None |  |  |  | 0 | None |
| `rules` | Collection Tier | Section Break | None |  |  |  | None | None |
| `collection_rules` | Collection Rules | Table | Loyalty Program Collection | ✅ |  |  | None | None |
| `redemption` | Redemption | Section Break | None |  |  |  | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  |  | None | 1 Loyalty Points = How much base currency? |
| `expiry_duration` | Expiry Duration (in days) | Int | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `help_section` | Help Section | Section Break | None |  |  |  | None | None |
| `loyalty_program_help` | Loyalty Program Help | HTML | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/loyalty_program/loyalty_program.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Loyalty Program", {
	setup: function (frm) {
		var help_content = `<table class="table table-bordered" style="background-color: var(--scrollbar-track-color);">
				<tr><td>
					<h4>
						<i class="fa fa-hand-right"></i>
						${__("Notes")}
					</h4>
					<ul>
						<li>
							${__(
								"Loyalty Points will be calculated from the spent done (via the Sales Invoice), based on collection factor mentioned."
							)}
						</li>
						<li>
							${__(
								"There can be multiple tiered collection factor based on the total spent. But the conversion factor for redemption will always be same for all the tier."
							)}
						</li>
						<li>
							${__(
								"In the case of multi-tier program, Customers will be auto assigned to the concerned tier as per their spent"
							)}
						</li>
						<li>
							${__("If unlimited expiry for the Loyalty Points, keep the Expiry Duration empty or 0.")}
						</li>
						<li>
							${__(
								"If Auto Opt In is checked, then the customers will be automatically linked with the concerned Loyalty Program (on save)"
							)}
						</li>
						<li>
							${__("One customer can be part of only single Loyalty Program.")}
						</li>
					</ul>
				</td></tr>
			</table>`;
		set_field_options("loyalty_program_help", help_content);
	},

	onload: function (frm) {
		frm.set_query("expense_account", function (doc) {
			return {
				filters: {
					root_type: "Expense",
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_value("company", frappe.defaults.get_user_default("Company"));
		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},

	refresh: function (frm) {
		if (frm.doc.loyalty_program_type === "Single Tier Program" && frm.doc.collection_rules.length > 1) {
			frappe.throw(
				__("Please select the Multiple Tier Program type for more than one collection rules.")
			);
		}
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
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
