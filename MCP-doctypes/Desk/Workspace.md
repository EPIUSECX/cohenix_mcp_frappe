# Master Control Plan: `Workspace`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:label`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Workspace Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `label` | Name | Data | None | ✅ |  |  | None | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `sequence_id` | Sequence Id | Float | None |  |  |  | None | None |
| `for_user` | For User | Data | None |  |  |  | None | None |
| `parent_page` | Parent Page | Link | Workspace |  |  |  | None | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `app` | App | Data | None |  |  |  | None | None |
| `type` | Type | Select | Workspace
Link
URL | ✅ |  |  | Workspace | None |
| `link_type` | Link Type | Select | DocType
Page
Report |  |  |  | None | None |
| `link_to` | Link To | Dynamic Link | link_type |  |  |  | None | None |
| `external_link` | External Link | Data | URL |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `icon` | Icon | Icon | None |  |  |  | None | None |
| `indicator_color` | Indicator Color | Select | green
cyan
blue
orange
yellow
gray
grey
red
pink
darkgrey
purple
light-blue |  |  |  | None | None |
| `restrict_to_domain` | Restrict to Domain | Link | Domain |  |  |  | None | None |
| `hide_custom` | Hide Custom DocTypes and Reports | Check | None |  |  |  | 0 | Checking this will hide custom doctypes and reports cards in Links section |
| `public` | Public | Check | None |  |  | ✅ | 0 | None |
| `is_hidden` | Is Hidden | Check | None |  |  |  | 0 | None |
| `content` | Content | Long Text | None |  | ✅ |  | [] | None |
| `number_cards_tab` | Number Cards | Tab Break | None |  |  |  | None | None |
| `number_cards` | Number Cards | Table | Workspace Number Card |  |  |  | None | None |
| `tab_break_2` | Dashboards | Tab Break | None |  |  |  | None | None |
| `charts` | Charts | Table | Workspace Chart |  |  |  | None | None |
| `tab_break_15` | Shortcuts | Tab Break | None |  |  |  | None | None |
| `shortcuts` | Shortcuts | Table | Workspace Shortcut |  |  |  | None | None |
| `tab_break_18` | Link Cards | Tab Break | None |  |  |  | None | None |
| `links` | Links | Table | Workspace Link |  |  |  | None | None |
| `quick_lists_tab` | Quick Lists | Tab Break | None |  |  |  | None | None |
| `quick_lists` | Quick Lists | Table | Workspace Quick List |  |  |  | None | None |
| `custom_blocks_tab` | Custom Blocks | Tab Break | None |  |  |  | None | None |
| `custom_blocks` | Custom Blocks | Table | Workspace Custom Block |  |  |  | None | None |
| `roles_tab` | Roles | Tab Break | None |  |  |  | None | None |
| `roles` | Roles | Table | Has Role |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 7

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/workspace/workspace.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Workspace", {
	setup: function () {
		frappe.meta.get_field("Workspace Link", "only_for").no_default = true;
	},

	refresh: function (frm) {
		frm.enable_save();

		let url = `/app/${
			frm.doc.public
				? frappe.router.slug(frm.doc.title)
				: "private/" + frappe.router.slug(frm.doc.title)
		}`;
		frm.sidebar
			.add_user_action(__("Go to Workspace"))
			.attr("href", url)
			.attr("target", "_blank");

		frm.layout.message.empty();
		let message = __("Please click Edit on the Workspace for best results");

		if (
			(frm.doc.for_user && frm.doc.for_user !== frappe.session.user) ||
			(frm.doc.public && !frappe.user.has_role("Workspace Manager"))
		) {
			frm.trigger("disable_form");

			if (frm.doc.public) {
				message = __("Only Workspace Manager can edit public workspaces");
			} else {
				message = __(
					"We do not allow editing of this document. Simply click the Edit button on the workspace page to make your workspace editable and customize it as you wish"
				);
			}
		}

		if (frappe.boot.developer_mode) {
			frm.set_df_property("module", "read_only", 0);
		}

		frm.layout.show_message(message);
	},

	disable_form: function (frm) {
		frm.fields
			.filter((field) => field.has_input)
			.forEach((field) => {
				frm.set_df_property(field.df.fieldname, "read_only", "1");
			});
		frm.disable_save();
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
