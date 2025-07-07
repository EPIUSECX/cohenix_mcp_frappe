# Master Control Plan: `Razorpay Settings`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `api_key` | API Key | Data | None | ✅ |  |  | None | None |
| `api_secret` | API Secret | Password | None | ✅ |  |  | None | None |
| `redirect_to` | Redirect To | Data | None |  |  |  | None | Mention transaction completion page URL |


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
**Path:** `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/razorpay_settings/razorpay_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Razorpay Settings", {
  refresh: function (frm) {
    frm.add_custom_button(__("Clear"), function () {
      frm.call({
        doc: frm.doc,
        method: "clear",
        callback: function (r) {
          frm.refresh();
        },
      });
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
