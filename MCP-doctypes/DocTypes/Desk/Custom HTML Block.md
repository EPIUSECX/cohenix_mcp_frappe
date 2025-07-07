# Master Control Plan: `Custom HTML Block`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Workspace Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `private` | Private | Check | None |  |  | ✅ | 0 | None |
| `preview_section` | Preview | Section Break | None |  |  |  | None | None |
| `preview` | None | HTML | None |  |  |  | None | None |
| `html_section` | HTML | Section Break | None |  |  |  | None | None |
| `html` | None | Code | HTML |  |  |  | None | None |
| `javascript_section` | Javascript | Section Break | None |  |  |  | None | None |
| `js_message` | JS Message | HTML | <p>To interact with above HTML you will have to use `root_element` as a parent selector.</p><p>For example:</p><pre class="p-3 bg-gray-100 border-radius rounded-sm mb-0" style="width: fit-content;"><code>// here root_element is provided by default
let some_class_element = root_element.querySelector('.some-class');
some_class_element.textContent = "New content";
</code></pre> |  |  |  | None | None |
| `script` | None | Code | JS |  |  |  | None | None |
| `css_section` | CSS | Section Break | None |  |  |  | None | None |
| `style` | None | Code | CSS |  |  |  | None | None |
| `roles_section` | Roles | Section Break | None |  |  |  | None | None |
| `roles` | Roles | Table | Has Role |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/custom_html_block/custom_html_block.js`
```javascript
// Copyright (c) 2023, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Custom HTML Block", {
	refresh(frm) {
		if (
			!has_common(frappe.user_roles, [
				"Administrator",
				"System Manager",
				"Workspace Manager",
			])
		) {
			frm.set_value("private", true);
		} else {
			frm.set_df_property("private", "read_only", false);
		}

		let wrapper = frm.fields_dict["preview"].wrapper;
		wrapper.classList.add("mb-3");

		frappe.create_shadow_element(wrapper, frm.doc.html, frm.doc.style, frm.doc.script);
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
