# Master Control Plan: `Accounting Dimension Filter`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:{accounting_dimension}-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `accounting_dimension` | Accounting Dimension | Select | None | ✅ |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `apply_restriction_on_values` | Apply restriction on dimension values | Check | None |  |  |  | 1 | None |
| `allow_or_restrict` | Allow Or Restrict Dimension | Select | Allow
Restrict | ✅ |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `accounts` | Applicable On Account | Table | Applicable On Account | ✅ |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `dimensions` | Applicable Dimension | Table | Allowed Dimension |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `dimension_filter_help` | Dimension Filter Help | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/accounting_dimension_filter/accounting_dimension_filter.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Accounting Dimension Filter", {
	refresh: function (frm, cdt, cdn) {
		let help_content = `<table class="table table-bordered" style="background-color: var(--scrollbar-track-color);">
				<tr><td>
					<p>
						<i class="fa fa-hand-right"></i>
						{{__('Note: On checking Is Mandatory the accounting dimension will become mandatory against that specific account for all accounting transactions')}}
					</p>
				</td></tr>
			</table>`;

		frm.set_df_property("dimension_filter_help", "options", help_content);
	},
	onload: function (frm) {
		frm.set_query("applicable_on_account", "accounts", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});

		frappe.db.get_list("Accounting Dimension", { fields: ["document_type"] }).then((res) => {
			let options = ["Cost Center", "Project"];

			res.forEach((dimension) => {
				options.push(dimension.document_type);
			});

			frm.set_df_property("accounting_dimension", "options", options);
		});

		frm.trigger("setup_filters");
	},

	setup_filters: function (frm) {
		let filters = {};

		if (frm.doc.accounting_dimension) {
			frappe.model.with_doctype(frm.doc.accounting_dimension, function () {
				if (frappe.model.is_tree(frm.doc.accounting_dimension)) {
					filters["is_group"] = 0;
				}

				if (frappe.meta.has_field(frm.doc.accounting_dimension, "company")) {
					filters["company"] = frm.doc.company;
				}

				frm.set_query("dimension_value", "dimensions", function () {
					return {
						filters: filters,
					};
				});
			});
		}
	},

	accounting_dimension: function (frm) {
		frm.clear_table("dimensions");
		let row = frm.add_child("dimensions");
		row.accounting_dimension = frm.doc.accounting_dimension;
		frm.fields_dict["dimensions"].grid.update_docfield_property(
			"dimension_value",
			"label",
			frm.doc.accounting_dimension
		);
		frm.refresh_field("dimensions");
		frm.trigger("setup_filters");
	},
	apply_restriction_on_values: function (frm) {
		/** If restriction on values is not applied, we should set "allow_or_restrict" to "Restrict" with an empty allowed dimension table.
		 * Hence it's not "restricted" on any value.
		 */
		if (!frm.doc.apply_restriction_on_values) {
			frm.set_value("allow_or_restrict", "Restrict");
			frm.clear_table("dimensions");
			frm.refresh_field("dimensions");
		}
	},
});

frappe.ui.form.on("Allowed Dimension", {
	dimensions_add: function (frm, cdt, cdn) {
		let row = locals[cdt][cdn];
		row.accounting_dimension = frm.doc.accounting_dimension;
		frm.refresh_field("dimensions");
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
