# Master Control Plan: `Bulk Salary Structure Assignment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `set_assignment_details_section` | Set Assignment Details | Section Break | None |  |  |  | None | None |
| `salary_structure` | Salary Structure | Link | Salary Structure | ✅ |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `income_tax_slab` | Income Tax Slab | Link | Income Tax Slab |  |  |  | None | None |
| `column_break_rsep` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `payroll_payable_account` | Payroll Payable Account | Link | Account |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  | ✅ | None | None |
| `quick_filters_section` | Quick Filters | Section Break | None |  |  |  | None | None |
| `branch` | Branch | Link | Branch |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `column_break_jcpq` | None | Column Break | None |  |  |  | None | None |
| `grade` | Employee Grade | Link | Employee Grade |  |  |  | None | None |
| `employment_type` | Employment Type | Link | Employment Type |  |  |  | None | None |
| `advanced_filters_section` | Advanced Filters | Section Break | None |  |  |  | None | None |
| `filter_list` | Filter List | HTML | None |  |  |  | None | None |
| `select_employees_section` | Select Employees | Section Break | None |  |  |  | None | None |
| `employees_html` | Employees HTML | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/bulk_salary_structure_assignment/bulk_salary_structure_assignment.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bulk Salary Structure Assignment", {
	setup(frm) {
		frm.trigger("set_queries");
		hrms.setup_employee_filter_group(frm);
	},

	async refresh(frm) {
		frm.page.clear_indicator();
		frm.disable_save();
		frm.trigger("set_primary_action");
		await frm.trigger("set_payroll_payable_account");
		frm.trigger("get_employees");
		hrms.handle_realtime_bulk_action_notification(
			frm,
			"completed_bulk_salary_structure_assignment",
			"Salary Structure Assignment",
		);
	},

	from_date(frm) {
		frm.trigger("get_employees");
	},

	async company(frm) {
		await frm.trigger("set_payroll_payable_account");
		frm.trigger("get_employees");
	},

	branch(frm) {
		frm.trigger("get_employees");
	},

	department(frm) {
		frm.trigger("get_employees");
	},

	employment_type(frm) {
		frm.trigger("get_employees");
	},

	designation(frm) {
		frm.trigger("get_employees");
	},

	grade(frm) {
		frm.trigger("get_employees");
	},

	set_primary_action(frm) {
		frm.page.set_primary_action(__("Assign Structure"), () => {
			frm.trigger("assign_structure");
		});
	},

	set_queries(frm) {
		frm.set_query("salary_structure", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_active: "Yes",
					docstatus: 1,
				},
			};
		});
		frm.set_query("income_tax_slab", function () {
			return {
				filters: {
					company: frm.doc.company,
					disabled: 0,
					docstatus: 1,
					currency: frm.doc.currency,
				},
			};
		});
		frm.set_query("payroll_payable_account", function () {
			const company_currency = erpnext.get_currency(frm.doc.company);
			return {
				filters: {
					company: frm.doc.company,
					root_type: "Liability",
					is_group: 0,
					account_currency: ["in", [frm.doc.currency, company_currency]],
				},
			};
		});
	},

	set_payroll_payable_account(frm) {
		frappe.db.get_value("Company", frm.doc.company, "default_payroll_payable_account", (r) => {
			frm.set_value("payroll_payable_account", r.default_payroll_payable_account);
		});
	},

	get_employees(frm) {
		if (!frm.doc.from_date) return frm.events.render_employees_datatable(frm, []);

		frm.call({
			method: "get_employees",
			args: {
				advanced_filters: frm.advanced_filters || [],
			},
			doc: frm.doc,
		}).then((r) => frm.events.render_employees_datatable(frm, r.message));
	},

	render_employees_datatable(frm, employees) {
		frm.checked_rows_indexes = [];

		const columns = frm.events.get_employees_datatable_columns();
		const no_data_message = __(
			frm.doc.from_date
				? "There are no employees without a Salary Structure Assignment on this date based on the given filters."
				: "Please select From Date.",
		);
		const get_editor = (colIndex, rowIndex, value, parent, column) => {
			if (!["base", "variable"].includes(column.name)) return;
			const $input = document.createElement("input");
			$input.className = "dt-input h-100";
			$input.type = "number";
			$input.min = 0;
			parent.appendChild($input);
			return {
				initValue(value) {
					$input.focus();
					$input.value = value;
				},
				setValue(value) {
					$input.value = value;
				},
				getValue() {
					return Number($input.value);
				},
			};
		};
		const events = {
			onCheckRow() {
				frm.trigger("handle_row_check");
			},
		};

		hrms.render_employees_datatable(
			frm,
			columns,
			employees,
			no_data_message,
			get_editor,
			events,
		);
	},

	get_employees_datatable_columns() {
		return [
			{
				name: "employee",
				id: "employee",
				content: __("Employee"),
				editable: false,
				focusable: false,
			},
			{
				name: "employee_name",
				id: "employee_name",
				content: __("Name"),
				editable: false,
				focusable: false,
			},
			{
				name: "grade",
				id: "grade",
				content: __("Grade"),
				editable: false,
				focusable: false,
			},
			{
				name: "base",
				id: "base",
				content: __("Base"),
			},
			{
				name: "variable",
				id: "variable",
				content: __("Variable"),
			},
		].map((x) => ({
			...x,
			dropdown: false,
			align: "left",
		}));
	},

	render_update_button(frm) {
		["Base", "Variable"].forEach((d) =>
			frm.add_custom_button(
				__(d),
				function () {
					const dialog = new frappe.ui.Dialog({
						title: __("Set {0} for selected employees", [__(d)]),
						fields: [
							{
								label: __(d),
								fieldname: d,
								fieldtype: "Currency",
							},
						],
						primary_action_label: __("Update"),
						primary_action(values) {
							const col_idx = frm.employees_datatable.datamanager.columns.find(
								(col) => col.content === d,
							).colIndex;
							frm.checked_rows_indexes.forEach((row_idx) => {
								frm.employees_datatable.cellmanager.updateCell(
									col_idx,
									row_idx,
									values[d],
									true,
								);
							});
							dialog.hide();
						},
					});
					dialog.show();
				},
				__("Update"),
			),
		);
		frm.update_button_rendered = true;
	},

	handle_row_check(frm) {
		frm.checked_rows_indexes = frm.employees_datatable.rowmanager.getCheckedRows();
		if (!frm.checked_rows_indexes.length && frm.update_button_rendered) {
			["Base", "Variable"].forEach((d) => frm.remove_custom_button(__(d), __("Update")));
			frm.update_button_rendered = false;
		} else if (frm.checked_rows_indexes.length && !frm.update_button_rendered)
			frm.trigger("render_update_button");
	},

	assign_structure(frm) {
		const rows = frm.employees_datatable.getRows();
		const checked_rows_content = [];
		const employees_with_base_zero = [];

		frm.checked_rows_indexes.forEach((idx) => {
			const row_content = {};
			rows[idx].forEach((cell) => {
				if (["employee", "base", "variable"].includes(cell.column.name))
					row_content[cell.column.name] = cell.content;
			});
			checked_rows_content.push(row_content);
			if (!row_content["base"])
				employees_with_base_zero.push(`<b>${row_content["employee"]}</b>`);
		});

		hrms.validate_mandatory_fields(frm, checked_rows_content);
		if (employees_with_base_zero.length)
			return frm.events.validate_base_zero(
				frm,
				employees_with_base_zero,
				checked_rows_content,
			);

		return frm.events.show_confirm_dialog(frm, checked_rows_content);
	},

	validate_base_zero(frm, employees_with_base_zero, checked_rows_content) {
		frappe.warn(
			__("Are you sure you want to proceed?"),
			__("<b>Base</b> amount has not been set for the following employee(s): {0}", [
				employees_with_base_zero.join(", "),
			]),
			() => {
				frm.events.show_confirm_dialog(frm, checked_rows_content);
			},
			__("Continue"),
		);
	},

	show_confirm_dialog(frm, checked_rows_content) {
		frappe.confirm(
			__("Assign Salary Structure to {0} employee(s)?", [checked_rows_content.length]),
			() => {
				frm.events.bulk_assign_structure(frm, checked_rows_content);
			},
		);
	},

	bulk_assign_structure(frm, employees) {
		frm.call({
			method: "bulk_assign_structure",
			doc: frm.doc,
			args: {
				employees: employees,
			},
			freeze: true,
			freeze_message: __("Assigning Salary Structure"),
		});
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
