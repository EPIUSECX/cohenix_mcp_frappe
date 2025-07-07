# Master Control Plan: `Domain Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `active_domains_sb` | Active Domains | Section Break | None |  |  |  | None | None |
| `domains_html` | Domains HTML | HTML | None |  |  |  | None | None |
| `active_domains` | Active Domains | Table | Has Domain |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/domain_settings/domain_settings.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Domain Settings", {
	before_load: function (frm) {
		if (!frm.domains_multicheck) {
			frm.domains_multicheck = frappe.ui.form.make_control({
				parent: frm.fields_dict.domains_html.$wrapper,
				df: {
					fieldname: "domains_multicheck",
					fieldtype: "MultiCheck",
					get_data: () => {
						let active_domains = (frm.doc.active_domains || []).map(
							(row) => row.domain
						);
						return frappe.boot.all_domains.map((domain) => {
							return {
								label: domain,
								value: domain,
								checked: active_domains.includes(domain),
							};
						});
					},
					on_change: () => {
						frm.dirty();
					},
				},
				render_input: true,
			});
			frm.domains_multicheck.refresh_input();
		}
	},

	validate: function (frm) {
		frm.trigger("set_options_in_table");
	},

	set_options_in_table: function (frm) {
		let selected_options = frm.domains_multicheck.get_value();
		let unselected_options = frm.domains_multicheck.options
			.map((option) => option.value)
			.filter((value) => {
				return !selected_options.includes(value);
			});

		let map = {},
			list = [];
		(frm.doc.active_domains || []).map((row) => {
			map[row.domain] = row.name;
			list.push(row.domain);
		});

		unselected_options.map((option) => {
			if (list.includes(option)) {
				frappe.model.clear_doc("Has Domain", map[option]);
			}
		});

		selected_options.map((option) => {
			if (!list.includes(option)) {
				frappe.model.clear_doc("Has Domain", map[option]);
				let row = frappe.model.add_child(frm.doc, "Has Domain", "active_domains");
				row.domain = option;
			}
		});

		refresh_field("active_domains");
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
