# Master Control Plan: `Permission Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `changed_by` | Changed by | Link | User |  |  | ✅ | None | None |
| `column_break_gvuy` | None | Column Break | None |  |  |  | None | None |
| `changed_at` | Changed at | Datetime | None |  |  | ✅ | None | None |
| `status` | Status | Select | Updated
Removed
Added |  | ✅ |  | None | None |
| `section_break_ttv7` | None | Section Break | None |  |  |  | None | None |
| `for_doctype` | For DocType | Link | DocType | ✅ |  | ✅ | None | None |
| `column_break_acow` | None | Column Break | None |  |  |  | None | None |
| `for_document` | For Document | Dynamic Link | for_doctype | ✅ |  | ✅ | None | None |
| `section_break_6gd5` | More Info | Section Break | None |  |  |  | None | None |
| `reference_type` | Reference Type | Link | DocType |  |  | ✅ | None | None |
| `column_break_8nk0` | None | Column Break | None |  |  |  | None | None |
| `reference` | Reference | Dynamic Link | reference_type |  |  | ✅ | None | None |
| `section_break_mt9x` | None | Section Break | None |  |  |  | None | None |
| `changes` | None | Text | None |  | ✅ |  | None | None |
| `changed_values` | Changes | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 2
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/permission_log/permission_log.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Permission Log", {
	refresh: function (frm) {
		frm.events.render_changed_values(frm);
	},

	render_changed_values: function (frm) {
		let wrapper = $(frm.fields_dict["changed_values"].wrapper).empty();
		const changes = JSON.parse(frm.doc.changes);
		let changes_table = $(`<table class="table table-bordered">
			<thead>
				<tr>
					<td>${__("Field")}</td>
					<td>${__("From")}</td>
					<td>${__("To")}</td>
				</tr>
			</thead>
			<tbody class="main-body"></tbody>
		</table>`);

		Object.entries(changes["from"]).forEach(([key, value]) => {
			if (Array.isArray(value || changes["to"][key])) {
				changes_table
					.find(".main-body")
					.append(frm.events.get_child_changes(key, value, changes["to"][key]));
			} else {
				changes_table.find("tbody").append(
					$(`<tr>
						<td>${frappe.model.unscrub(key)}</td>
						<td style="word-break: break-word" class="diff-remove">${changes["from"][key]}</td>
						<td style="word-break: break-word" class="diff-add">${changes["to"][key]}</td>
					</tr>`)
				);
			}
		});

		wrapper.append(changes_table);
	},

	get_child_changes: function (field_key, from, to) {
		let child_main = $(`<tr>
			<td>${frappe.model.unscrub(field_key)}</td>
			<td class="from"></td>
			<td class="to"></td>
		</tr>`);

		[from, to].forEach((val, index) => {
			if (!val) return;

			let for_value = index > 0 ? "to" : "frfromom";
			let child_table = $(`<table class="table-bordered small" style="margin-bottom: 5px">
				<tbody></tbody>
			</table>`);

			val.forEach((child_row) => {
				for (const [key, value] of Object.entries(child_row)) {
					child_table.find("tbody").append(
						$(
							`<tr>
							<td style="word-break: break-word">${frappe.model.unscrub(key)}</td>
							<td style="word-break: break-word">${value}</td>
						</tr>`
						)
					);
				}
			});

			child_main.find(`.${for_value}`).append(child_table);
		});

		return child_main;
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
