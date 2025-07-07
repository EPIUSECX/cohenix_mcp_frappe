# Master Control Plan: `Version`

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
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Administrator | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `ref_doctype` | DocType | Link | DocType | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `docname` | Document Name | Data | None | ✅ |  |  | None | None |
| `data` | Data | Code | None |  | ✅ |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `table_html` | Table HTML | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/version/version.js`
```javascript
frappe.ui.form.on("Version", "refresh", function (frm) {
	$(
		frappe.render_template("version_view", { doc: frm.doc, data: JSON.parse(frm.doc.data) })
	).appendTo(frm.fields_dict.table_html.$wrapper.empty());

	frm.add_custom_button(__("Show all Versions"), function () {
		frappe.set_route("List", "Version", {
			ref_doctype: frm.doc.ref_doctype,
			docname: frm.doc.docname,
		});
	});
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Calculated Discount Mismatch` | Script Report | Accounts |



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
