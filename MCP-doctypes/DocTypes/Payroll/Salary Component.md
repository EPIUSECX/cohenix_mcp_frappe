# Master Control Plan: `Salary Component`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:salary_component`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `overview_tab` | Overview | Tab Break | None |  |  |  | None | None |
| `salary_component` | Name | Data | None | ✅ |  |  | None | None |
| `salary_component_abbr` | Abbr | Data | None | ✅ |  |  | None | None |
| `type` | Type | Select | Earning
Deduction | ✅ |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `depends_on_payment_days` | Depends on Payment Days | Check | None |  |  |  | 1 | None |
| `is_tax_applicable` | Is Tax Applicable | Check | None |  |  |  | 1 | None |
| `deduct_full_tax_on_selected_payroll_date` | Deduct Full Tax on Selected Payroll Date | Check | None |  |  |  | 0 | None |
| `variable_based_on_taxable_salary` | Variable Based On Taxable Salary | Check | None |  |  |  | 0 | If enabled, the component will be considered as a tax component and the amount will be auto-calculated as per the configured income tax slabs |
| `is_income_tax_component` | Is Income Tax Component | Check | None |  |  |  | 0 | If enabled, the component will be considered in the Income Tax Deductions report |
| `exempted_from_income_tax` | Exempted from Income Tax | Check | None |  |  |  | 0 | If checked, the full amount will be deducted from taxable income before calculating income tax without any declaration or proof submission. |
| `round_to_the_nearest_integer` | Round to the Nearest Integer | Check | None |  |  |  | 0 | None |
| `statistical_component` | Statistical Component | Check | None |  |  |  | 0 | If enabled, the value specified or calculated in this component will not contribute to the earnings or deductions. However, it's value can be referenced by other components that can be added or deducted.  |
| `do_not_include_in_total` | Do Not Include in Total | Check | None |  |  |  | 0 | None |
| `remove_if_zero_valued` | Remove if Zero Valued | Check | None |  |  |  | 1 | If enabled, the component will not be displayed in the salary slip if the amount is zero |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `section_break_5` | Accounts | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Salary Component Account |  |  |  | None | None |
| `configure_component_tab` | Condition & Formula | Tab Break | None |  |  |  | None | None |
| `condition_and_formula` | None | Section Break | None |  |  |  | None | None |
| `condition` | Condition | Code | PythonExpression |  |  |  | None | None |
| `amount` | Amount | Currency | None |  |  |  | None | None |
| `amount_based_on_formula` | Amount based on formula | Check | None |  |  |  | 0 | None |
| `formula` | Formula | Code | PythonExpression |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `help` | Help | HTML | <h3>Help</h3>

<p>Notes:</p>

<ol>
<li>Use field <code>base</code> for using base salary of the Employee</li>
<li>Use Salary Component abbreviations in conditions and formulas. <code>BS = Basic Salary</code></li>
<li>Use field name for employee details in conditions and formulas. <code>Employment Type = employment_type</code><code>Branch = branch</code></li>
<li>Use field name from Salary Slip in conditions and formulas. <code>Payment Days = payment_days</code><code>Leave without pay = leave_without_pay</code></li>
<li>Direct Amount can also be entered based on Condition. See example 3</li></ol>

<h4>Examples</h4>
<ol>
<li>Calculating Basic Salary based on <code>base</code>
<pre><code>Condition: base &lt; 10000</code></pre>
<pre><code>Formula: base * .2</code></pre></li>
<li>Calculating HRA based on Basic Salary<code>BS</code> 
<pre><code>Condition: BS &gt; 2000</code></pre>
<pre><code>Formula: BS * .1</code></pre></li>
<li>Calculating TDS based on Employment Type<code>employment_type</code> 
<pre><code>Condition: employment_type=="Intern"</code></pre>
<pre><code>Amount: 1000</code></pre></li>
</ol> |  |  |  | None | None |
| `flexible_benefits_tab` | Flexible Benefits | Tab Break | None |  |  |  | None | None |
| `is_flexible_benefit` | Is Flexible Benefit | Check | None |  |  |  | 0 | None |
| `max_benefit_amount` | Max Benefit Amount (Yearly) | Currency | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `pay_against_benefit_claim` | Pay Against Benefit Claim | Check | None |  |  |  | 0 | None |
| `only_tax_impact` | Only Tax Impact (Cannot Claim But Part of Taxable Income) | Check | None |  |  |  | 0 | None |
| `create_separate_payment_entry_against_benefit_claim` | Create Separate Payment Entry Against Benefit Claim | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_component/salary_component.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Salary Component", {
	setup: function (frm) {
		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			var d = locals[cdt][cdn];
			return {
				filters: {
					is_group: 0,
					company: d.company,
				},
			};
		});
		frm.set_query("earning_component_group", function () {
			return {
				filters: {
					is_group: 1,
					is_flexible_benefit: 1,
				},
			};
		});
	},

	refresh: function (frm) {
		hrms.payroll_utils.set_autocompletions_for_condition_and_formula(frm);

		if (!frm.doc.__islocal) {
			frm.trigger("add_update_structure_button");
			frm.add_custom_button(
				__("Salary Structure"),
				() => {
					frm.trigger("create_salary_structure");
				},
				__("Create"),
			);
		}
	},

	is_flexible_benefit: function (frm) {
		if (frm.doc.is_flexible_benefit) {
			set_value_for_condition_and_formula(frm);
			frm.set_value("formula", "");
			frm.set_value("amount", 0);
		}
	},

	type: function (frm) {
		if (frm.doc.type == "Earning") {
			frm.set_value("is_tax_applicable", 1);
			frm.set_value("variable_based_on_taxable_salary", 0);
		}
		if (frm.doc.type == "Deduction") {
			frm.set_value("is_tax_applicable", 0);
			frm.set_value("is_flexible_benefit", 0);
		}
	},

	variable_based_on_taxable_salary: function (frm) {
		if (frm.doc.variable_based_on_taxable_salary) {
			set_value_for_condition_and_formula(frm);
		}
	},

	create_separate_payment_entry_against_benefit_claim: function (frm) {
		if (frm.doc.create_separate_payment_entry_against_benefit_claim) {
			frm.set_df_property("accounts", "reqd", 1);
			frm.set_value("only_tax_impact", 0);
		} else {
			frm.set_df_property("accounts", "reqd", 0);
		}
	},

	only_tax_impact: function (frm) {
		if (frm.only_tax_impact) {
			frm.set_value("create_separate_payment_entry_against_benefit_claim", 0);
		}
	},

	add_update_structure_button: function (frm) {
		for (const df of ["Condition", "Formula"]) {
			frm.add_custom_button(
				__("Sync {0}", [__(df)]),
				function () {
					frappe
						.call({
							method: "get_structures_to_be_updated",
							doc: frm.doc,
						})
						.then((r) => {
							if (r.message.length)
								frm.events.update_salary_structures(frm, df, r.message);
							else
								frappe.msgprint({
									message: __(
										"Salary Component {0} is currently not used in any Salary Structure.",
										[frm.doc.name.bold()],
									),
									title: __("No Salary Structures"),
									indicator: "orange",
								});
						});
				},
				__("Update Salary Structures"),
			);
		}
	},

	update_salary_structures: function (frm, df, structures) {
		let msg = __("{0} will be updated for the following Salary Structures: {1}.", [
			df,
			frappe.utils.comma_and(
				structures.map((d) =>
					frappe.utils.get_form_link("Salary Structure", d, true).bold(),
				),
			),
		]);
		msg += "<br>";
		msg += __("Are you sure you want to proceed?");
		frappe.confirm(msg, () => {
			frappe
				.call({
					method: "update_salary_structures",
					doc: frm.doc,
					args: {
						structures: structures,
						field: df.toLowerCase(),
						value: frm.get_field(df.toLowerCase()).value || "",
					},
				})
				.then((r) => {
					if (!r.exc) {
						frappe.show_alert({
							message: __("Salary Structures updated successfully"),
							indicator: "green",
						});
					}
				});
		});
	},

	create_salary_structure: function (frm) {
		frappe.model.with_doctype("Salary Structure", () => {
			const salary_structure = frappe.model.get_new_doc("Salary Structure");
			const salary_detail = frappe.model.add_child(
				salary_structure,
				frm.doc.type === "Earning" ? "earnings" : "deductions",
			);
			salary_detail.salary_component = frm.doc.name;
			frappe.set_route("Form", "Salary Structure", salary_structure.name);
		});
	},
});

var set_value_for_condition_and_formula = function (frm) {
	frm.set_value("formula", null);
	frm.set_value("condition", null);
	frm.set_value("amount_based_on_formula", 0);
	frm.set_value("statistical_component", 0);
	frm.set_value("do_not_include_in_total", 0);
	frm.set_value("depends_on_payment_days", 0);
};

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
