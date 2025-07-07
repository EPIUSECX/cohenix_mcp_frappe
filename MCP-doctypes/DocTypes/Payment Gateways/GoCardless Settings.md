# Master Control Plan: `GoCardless Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payment Gateways`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:gateway_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `gateway_name` | Payment Gateway Name | Data | None | ✅ |  |  | None | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `access_token` | Access Token | Data | None | ✅ |  |  | None | None |
| `webhooks_secret` | Webhooks Secret | Data | None |  |  |  | None | None |
| `use_sandbox` | Use Sandbox | Check | None |  |  |  | 0 | None |
| `header_img` | Header Image | Attach Image | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/gocardless_settings/gocardless_settings.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

// frappe.ui.form.on('GoCardless Settings', {
// 	refresh(frm) {

// 	},
// });

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
