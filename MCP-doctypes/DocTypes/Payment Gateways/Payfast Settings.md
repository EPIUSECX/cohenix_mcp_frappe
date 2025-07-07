# Master Control Plan: `Payfast Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payment Gateways`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `merchant_id` | Merchant ID | Data | None | ✅ |  |  | None | None |
| `merchant_key` | Merchant Key | Data | None | ✅ |  |  | None | None |
| `passphrase` | Passphrase | Password | None |  |  |  | None | None |
| `sandbox_mode` | Sandbox Mode | Check | None |  |  |  | 0 | None |
| `return_url` | Return URL | Data | None |  |  |  | None | None |
| `cancel_url` | Cancel URL | Data | None |  |  |  | None | None |
| `notify_url` | Notify URL | Data | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/payfast_settings/payfast_settings.js`
```javascript
// Copyright (c) 2024, [Your Name] and contributors
// License: MIT. See LICENSE

frappe.ui.form.on('Payfast Settings', {
	// client-side scripts for Payfast Settings
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
