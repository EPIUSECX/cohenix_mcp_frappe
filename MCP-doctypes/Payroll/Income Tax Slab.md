# Master Control Plan: `Income Tax Slab`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `effective_from` | Effective from | Date | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `standard_tax_exemption_amount` | Standard Tax Exemption Amount | Currency | currency |  |  |  | None | None |
| `allow_tax_exemption` | Allow Tax Exemption | Check | None |  |  |  | 0 | If enabled, Tax Exemption Declaration will be considered for income tax calculation. |
| `amended_from` | Amended From | Link | Income Tax Slab |  |  | ✅ | None | None |
| `taxable_salary_slabs_section` | Taxable Salary Slabs | Section Break | None |  |  |  | None | None |
| `slabs` | Taxable Salary Slabs | Table | Taxable Salary Slab | ✅ |  |  | None | None |
| `section_break_cajo` | None | Section Break | None |  |  |  | None | None |
| `tax_relief_limit` | Taxable Income Relief Threshold Limit | Currency | None |  |  |  | None | Maximum annual taxable income eligible for full tax relief. No tax is applied if income does not exceed this limit |
| `column_break_pdmy` | None | Column Break | None |  |  |  | None | None |
| `taxes_and_charges_on_income_tax_section` | Taxes and Charges on Income Tax | Section Break | None |  |  |  | None | None |
| `other_taxes_and_charges` | Other Taxes and Charges | Table | Income Tax Slab Other Charges |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/income_tax_slab/income_tax_slab.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Income Tax Slab", {
	refresh: function (frm) {
		if (frm.doc.docstatus != 1) return;
		frm.add_custom_button(
			__("Salary Structure Assignment"),
			() => {
				frappe.model.with_doctype("Salary Structure Assignment", () => {
					const doc = frappe.model.get_new_doc("Salary Structure Assignment");
					doc.income_tax_slab = frm.doc.name;
					frappe.set_route("Form", "Salary Structure Assignment", doc.name);
				});
			},
			__("Create"),
		);
		frm.page.set_inner_btn_group_as_primary(__("Create"));
	},

	currency: function (frm) {
		frm.refresh_fields();
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
