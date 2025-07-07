# Master Control Plan: `Yoco Settings`

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
| `public_key` | Public Key | Data | None | ✅ |  |  | None | None |
| `secret_key` | Secret Key | Password | None | ✅ |  |  | None | None |
| `webhook_secret` | Webhook Secret | Password | None |  |  |  | None | Secret key for webhook signature verification (from Yoco webhook settings) |
| `sandbox_mode` | Sandbox Mode | Check | None |  |  |  | 1 | Enable for testing with Yoco sandbox environment |
| `apple_pay_section` | Apple Pay Configuration | Section Break | None |  |  |  | None | None |
| `enable_apple_pay` | Enable Apple Pay | Check | None |  |  |  | 1 | Enable Apple Pay as a payment option |
| `apple_pay_merchant_id` | Apple Pay Merchant ID | Data | None |  |  |  | None | Your Apple Pay merchant identifier (e.g., merchant.com.yourcompany.yoco) |


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
**Path:** `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/yoco_settings/yoco_settings.js`
```javascript
// Copyright (c) 2024, [Your Name] and contributors
// License: MIT. See LICENSE

frappe.ui.form.on('Yoco Settings', {
	// client-side scripts for Yoco Settings
    // TODO: Implement client-side integration with Yoco SDK for tokenization

    refresh: function(frm) {
        frm.add_custom_button(__('Test Connection'), function() {
            frm.call({
                method: 'test_connection',
                doc: frm.doc,
                callback: function(r) {
                    if (r.message.status === 'success') {
                        frappe.msgprint(__('Connection successful!'));
                    } else {
                        frappe.msgprint(__('Connection failed: ') + r.message.message, __('Error'));
                    }
                }
            });
        });
    }
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
