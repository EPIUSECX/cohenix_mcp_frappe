# Master Control Plan: `Mpesa Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payment Gateways`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:payment_gateway_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `payment_gateway_name` | Payment Gateway Name | Data | None | ✅ |  |  | None | None |
| `consumer_key` | Consumer Key | Data | None | ✅ |  |  | None | None |
| `consumer_secret` | Consumer Secret | Password | None | ✅ |  |  | None | None |
| `initiator_name` | Initiator Name | Data | None |  |  |  | None | None |
| `till_number` | Till Number | Data | None | ✅ |  |  | None | None |
| `transaction_limit` | Transaction Limit | Float | None |  |  |  | 150000 | None |
| `sandbox` | Sandbox | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `business_shortcode` | Business Shortcode | Data | None |  |  |  | None | None |
| `online_passkey` |  Online PassKey | Password | None | ✅ |  |  | None | None |
| `security_credential` | Security Credential | Small Text | None |  |  |  | None | None |
| `get_account_balance` | Get Account Balance | Button | None |  |  |  | None | None |
| `account_balance` | Account Balance | Long Text | None |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/mpesa_settings/mpesa_settings.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Mpesa Settings", {
  onload_post_render: function (frm) {
    frm.events.setup_account_balance_html(frm);
  },

  refresh: function (frm) {
    frappe.realtime.on("refresh_mpesa_dashboard", function () {
      frm.reload_doc();
      frm.events.setup_account_balance_html(frm);
    });
  },

  get_account_balance: function (frm) {
    if (!frm.doc.initiator_name && !frm.doc.security_credential) {
      frappe.throw(
        __("Please set the initiator name and the security credential")
      );
    }
    frappe.call({
      method: "get_account_balance_info",
      doc: frm.doc,
    });
  },

  setup_account_balance_html: function (frm) {
    if (!frm.doc.account_balance) return;
    $("div").remove(".form-dashboard-section.custom");
    frm.dashboard.add_section(
      frappe.render_template("account_balance", {
        data: JSON.parse(frm.doc.account_balance),
      })
    );
    frm.dashboard.show();
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
