# Master Control Plan: `Coupon Code`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:coupon_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `coupon_name` | Coupon Name | Data | None | ✅ |  |  | None | e.g. "Summer Holiday 2019 Offer 20" |
| `coupon_type` | Coupon Type | Select | Promotional
Gift Card | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `coupon_code` | Coupon Code | Data | None |  |  |  | None | unique e.g. SAVE20  To be used to get discount |
| `from_external_ecomm_platform` | From External Ecomm Platform | Check | None |  |  |  | 0 | None |
| `pricing_rule` | Pricing Rule | Link | Pricing Rule |  |  |  | None | None |
| `uses` | Validity and Usage | Section Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None |  |  |  | None | None |
| `valid_upto` | Valid Up To | Date | None |  |  |  | None | None |
| `maximum_use` | Maximum Use | Int | None |  |  |  | None | None |
| `used` | Used | Int | None |  |  | ✅ | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `description` | Coupon Description | Text Editor | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Coupon Code |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/coupon_code/coupon_code.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Coupon Code", {
	setup: function (frm) {
		frm.set_query("pricing_rule", function () {
			return {
				filters: [["Pricing Rule", "coupon_code_based", "=", "1"]],
			};
		});
	},
	coupon_name: function (frm) {
		if (frm.doc.__islocal === 1) {
			frm.trigger("make_coupon_code");
		}
	},
	coupon_type: function (frm) {
		if (frm.doc.__islocal === 1) {
			frm.trigger("make_coupon_code");
		}
	},
	make_coupon_code: function (frm) {
		var coupon_name = frm.doc.coupon_name;
		var coupon_code;
		if (frm.doc.coupon_type == "Gift Card") {
			coupon_code = Math.random().toString(12).substring(2, 12).toUpperCase();
		} else if (frm.doc.coupon_type == "Promotional") {
			coupon_name = coupon_name.replace(/\s/g, "");
			coupon_code = coupon_name.toUpperCase().slice(0, 8);
		}
		frm.doc.coupon_code = coupon_code;
		frm.refresh_field("coupon_code");
	},
	refresh: function (frm) {
		if (frm.doc.pricing_rule) {
			frm.add_custom_button(__("Add/Edit Coupon Conditions"), function () {
				frappe.set_route("Form", "Pricing Rule", frm.doc.pricing_rule);
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
