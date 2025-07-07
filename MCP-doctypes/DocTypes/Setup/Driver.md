# Master Control Plan: `Driver`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Fleet Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Delivery User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| Delivery Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | HR-DRI-.YYYY.- |  |  |  | None | None |
| `full_name` | Full Name | Data | None | ✅ |  |  | None | None |
| `status` | Status | Select | Active
Suspended
Left | ✅ |  |  | None | None |
| `transporter` | Transporter | Link | Supplier |  |  |  | None | Applicable for external driver |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee |  |  |  | None | None |
| `cell_number` | Cellphone Number | Data | None |  |  |  | None | None |
| `address` | Address | Link | Address |  |  |  | None | None |
| `user` | User | Link | User |  |  |  | None | None |
| `license_details` | License Details | Section Break | None |  |  |  | None | None |
| `license_number` | License Number | Data | None |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `issuing_date` | Issuing Date | Date | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `expiry_date` | Expiry Date | Date | None |  |  |  | None | None |
| `driving_license_categories` | Driving License Categories | Section Break | None |  |  |  | None | None |
| `driving_license_category` | Driving License Category | Table | Driving License Category |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/driver/driver.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Driver", {
	setup: function (frm) {
		frm.set_query("transporter", function () {
			return {
				filters: {
					is_transporter: 1,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.set_query("address", function () {
			return {
				filters: {
					is_your_company_address: !frm.doc.transporter ? 1 : 0,
				},
			};
		});
	},

	transporter: function (frm, cdt, cdn) {
		// this assumes that supplier's address has same title as supplier's name
		frappe.db
			.get_doc("Address", null, { address_title: frm.doc.transporter })
			.then((r) => {
				frappe.model.set_value(cdt, cdn, "address", r.name);
			})
			.catch((err) => {
				console.log(err);
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
