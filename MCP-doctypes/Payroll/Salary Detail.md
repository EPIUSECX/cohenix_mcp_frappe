# Master Control Plan: `Salary Detail`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `salary_component` | Component | Link | Salary Component | ✅ |  |  | None | None |
| `abbr` | Abbr | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  |  | None | None |
| `year_to_date` | Year To Date | Currency | currency |  |  | ✅ | None | Total salary booked against this component for this employee from the beginning of the year (payroll period or fiscal year) up to the current salary slip's end date. |
| `section_break_5` | Component properties and references  | Section Break | None |  |  |  | None | None |
| `additional_salary` | Additional Salary  | Link | Additional Salary |  |  | ✅ | None | None |
| `is_recurring_additional_salary` | Is Recurring Additional Salary | Check | None |  |  | ✅ | 0 | None |
| `statistical_component` | Statistical Component | Check | None |  |  |  | 0 | If selected, the value specified or calculated in this component will not contribute to the earnings or deductions. However, it's value can be referenced by other components that can be added or deducted.  |
| `depends_on_payment_days` | Depends on Payment Days | Check | None |  |  | ✅ | 0 | None |
| `exempted_from_income_tax` | Exempted from Income Tax | Check | None |  |  | ✅ | 0 | None |
| `is_tax_applicable` | Is Tax Applicable | Check | None |  |  | ✅ | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `is_flexible_benefit` | Is Flexible Benefit | Check | None |  |  | ✅ | 0 | None |
| `variable_based_on_taxable_salary` | Variable Based On Taxable Salary | Check | None |  |  | ✅ | 0 | None |
| `do_not_include_in_total` | Do not include in total | Check | None |  |  |  | 0 | None |
| `deduct_full_tax_on_selected_payroll_date` | Deduct Full Tax on Selected Payroll Date | Check | None |  |  | ✅ | 0 | None |
| `section_break_2` | Condition and formula | Section Break | None |  |  |  | None | None |
| `condition` | Condition | Code | PythonExpression |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `amount_based_on_formula` | Amount based on formula | Check | None |  |  |  | 0 | None |
| `formula` | Formula | Code | PythonExpression |  |  |  | None | None |
| `section_break_19` | None | Section Break | None |  |  |  | None | None |
| `default_amount` | Default Amount | Currency | currency |  |  |  | None | None |
| `additional_amount` | Additional Amount | Currency | currency |  | ✅ | ✅ | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `tax_on_flexible_benefit` | Tax on flexible benefit | Currency | currency |  |  | ✅ | None | None |
| `tax_on_additional_salary` | Tax on additional salary | Currency | currency |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)




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
