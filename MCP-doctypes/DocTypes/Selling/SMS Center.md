# Master Control Plan: `SMS Center`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `send_to` | Send To | Select | 
All Contact
All Customer Contact
All Supplier Contact
All Sales Partner Contact
All Lead (Open)
All Employee (Active)
All Sales Person |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `branch` | Branch | Link | Branch |  |  |  | None | None |
| `create_receiver_list` | Create Receiver List | Button | create_receiver_list |  |  |  | None | None |
| `receiver_list` | Receiver List | Code | None |  |  |  | None | None |
| `column_break9` | None | Column Break | None |  |  |  | None | None |
| `message` | Message | Text | None | ✅ |  |  | None | Messages greater than 160 characters will be split into multiple messages |
| `total_characters` | Total Characters | Int | None |  |  | ✅ | None | None |
| `total_messages` | Total Message(s) | Int | None |  |  | ✅ | None | None |
| `send_sms` | Send SMS | Button | send_sms |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/sms_center/sms_center.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

extend_cscript(cur_frm.cscript, {
	message: function () {
		var total_characters = this.frm.doc.message.length;
		var total_msg = 1;

		if (total_characters > 160) {
			total_msg = cint(total_characters / 160);
			total_msg = total_characters % 160 == 0 ? total_msg : total_msg + 1;
		}

		this.frm.set_value("total_characters", total_characters);
		this.frm.set_value("total_messages", this.frm.doc.message ? total_msg : 0);
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
