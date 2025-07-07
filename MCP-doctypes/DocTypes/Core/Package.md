# Master Control Plan: `Package`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `package_name` | Package Name | Data | None | ✅ |  |  | None | None |
| `readme` | Readme | Markdown Editor | None |  |  |  | None | None |
| `license_type` | License Type | Select | 
MIT License
GNU General Public License
GNU Affero General Public License |  |  |  | None | None |
| `license` | License | Markdown Editor | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/package/package.js`
```javascript
// Copyright (c) 2021, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Package", {
	validate: function (frm) {
		if (!frm.doc.package_name) {
			frm.set_value("package_name", frm.doc.name.toLowerCase().replace(" ", "-"));
		}
	},

	license_type: function (frm) {
		frappe
			.call("frappe.core.doctype.package.package.get_license_text", {
				license_type: frm.doc.license_type,
			})
			.then((r) => {
				frm.set_value("license", r.message);
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
