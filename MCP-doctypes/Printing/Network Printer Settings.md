# Master Control Plan: `Network Printer Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Printing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `server_ip` | Server IP | Data | None | ✅ |  |  | localhost | None |
| `port` | Port | Int | None | ✅ |  |  | 631 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `printer_name` | Printer Name | Select | None | ✅ |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/printing/doctype/network_printer_settings/network_printer_settings.js`
```javascript
// Copyright (c) 2021, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Network Printer Settings", {
	onload(frm) {
		frm.trigger("connect_print_server");
	},
	server_ip(frm) {
		frm.trigger("connect_print_server");
	},
	port(frm) {
		frm.trigger("connect_print_server");
	},
	connect_print_server(frm) {
		if (frm.doc.server_ip && frm.doc.port) {
			frappe.call({
				doc: frm.doc,
				method: "get_printers_list",
				args: {
					ip: frm.doc.server_ip,
					port: frm.doc.port,
				},
				callback: function (data) {
					frm.set_df_property("printer_name", "options", [""].concat(data.message));
				},
			});
		}
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
