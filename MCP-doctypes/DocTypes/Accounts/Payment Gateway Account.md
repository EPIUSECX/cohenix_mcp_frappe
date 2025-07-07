# Master Control Plan: `Payment Gateway Account`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `payment_gateway` | Payment Gateway | Link | Payment Gateway | ✅ |  |  | None | None |
| `payment_channel` | Payment Channel | Select | 
Email
Phone
Other |  |  |  | Email | None |
| `is_default` | Is Default | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `payment_account` | Payment Account | Link | Account | ✅ |  |  | None | None |
| `currency` | Currency | Read Only | None |  |  |  | None | None |
| `payment_request_message` | None | Section Break | None |  |  |  | None | None |
| `message` | Default Payment Request Message | Small Text | None |  |  |  | Please click on the link below to make your payment | None |
| `message_examples` | Message Examples | HTML | <pre><h5>Message Example</h5>

&lt;p&gt; Thank You for being a part of {{ doc.company }}! We hope you are enjoying the service.&lt;/p&gt;

&lt;p&gt; Please find enclosed the E Bill statement. The outstanding amount is {{ doc.grand_total }}.&lt;/p&gt;

&lt;p&gt; We don't want you to be spending time running around in order to pay for your Bill.<br>After all, life is beautiful and the time you have in hand should be spent to enjoy it!<br>So here are our little ways to help you get more time for life! &lt;/p&gt;

&lt;a href="{{ payment_url }}"&gt; click here to pay &lt;/a&gt;

</pre>
 |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_gateway_account/payment_gateway_account.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Payment Gateway Account", {
	refresh(frm) {
		erpnext.utils.check_payments_app();
		if (!frm.doc.__islocal) {
			frm.set_df_property("payment_gateway", "read_only", 1);
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
