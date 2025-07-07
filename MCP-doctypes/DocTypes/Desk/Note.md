# Master Control Plan: `Note`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ |
| Desk User | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `public` | Public | Check | None |  |  |  | 0 | None |
| `notify_on_login` | Notify users with a popup when they log in | Check | None |  |  |  | 0 | None |
| `notify_on_every_login` | Notify Users On Every Login | Check | None |  |  |  | 0 | If enabled, users will be notified every time they login. If not enabled, users will only be notified once. |
| `expire_notification_on` | Expire Notification On | Datetime | None |  |  |  | None | None |
| `content` | Content | Text Editor | None |  |  |  | None | Help: To link to another record in the system, use "/app/note/[Note Name]" as the Link URL. (don't use "http://") |
| `seen_by_section` | Seen By | Section Break | None |  |  |  | None | None |
| `seen_by` | Seen By Table | Table | Note Seen By |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/note/note.js`
```javascript
frappe.ui.form.on("Note", {
	refresh: function (frm) {
		if (!frm.is_new()) {
			frm.is_note_editable = false;
			frm.events.set_editable(frm);
		}
	},
	set_editable: function (frm) {
		if (frm.has_perm("write")) {
			const read_label = __("Read mode");
			const edit_label = __("Edit mode");
			frm.remove_custom_button(frm.is_note_editable ? edit_label : read_label);
			frm.add_custom_button(frm.is_note_editable ? read_label : edit_label, function () {
				frm.is_note_editable = !frm.is_note_editable;
				frm.events.set_editable(frm);
			});
		}
		// toggle "read_only" for content and "hidden" of all other fields

		// content read_only
		frm.set_df_property("content", "read_only", frm.is_note_editable ? 0 : 1);

		// hide all other fields
		for (const field of frm.meta.fields) {
			if (field.fieldname !== "content") {
				frm.set_df_property(
					field.fieldname,
					"hidden",
					frm.is_note_editable && !field.hidden && frm.get_perm(field.permlevel, "write")
						? 0
						: 1
				);
			}
		}

		// no label, description for content either
		frm.get_field("content").toggle_label(frm.is_note_editable);
		frm.get_field("content").toggle_description(frm.is_note_editable);
	},
});

frappe.tour["Note"] = [
	{
		fieldname: "title",
		title: "Title of the Note",
		description: "This is the name by which the note will be saved, you can change this later",
	},
	{
		fieldname: "public",
		title: "Sets the Note to Public",
		description:
			"You can change the visibility of the note with this, setting it to public will allow other users to view it.",
	},
];

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
