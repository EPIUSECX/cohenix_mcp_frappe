# Master Control Plan: `SMS Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
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
| `sms_gateway_url` | SMS Gateway URL | Small Text | None | ✅ |  |  | None | Eg. smsgateway.com/api/send_sms.cgi |
| `message_parameter` | Message Parameter | Data | None | ✅ |  |  | None | Enter url parameter for message |
| `receiver_parameter` | Receiver Parameter | Data | None | ✅ |  |  | None | Enter url parameter for receiver nos |
| `static_parameters_section` | None | Column Break | None |  |  |  | None | None |
| `parameters` | Static Parameters | Table | SMS Parameter |  |  |  | None | Enter static url parameters here (Eg. sender=ERPNext, username=ERPNext, password=1234 etc.) |
| `use_post` | Use POST | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/sms_settings/sms_settings.js`
```javascript

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
