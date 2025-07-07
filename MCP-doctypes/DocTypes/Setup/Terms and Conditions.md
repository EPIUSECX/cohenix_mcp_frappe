# Master Control Plan: `Terms and Conditions`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** Standard Terms and Conditions that can be added to Sales and Purchases. Examples: Validity of the offer, Payment Terms, Safety and Usage, etc.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `applicable_modules_section` | Applicable Modules | Section Break | None |  |  |  | None | None |
| `selling` | Selling | Check | None |  |  |  | 1 | None |
| `buying` | Buying | Check | None |  |  |  | 1 | None |
| `hr` | HR | Check | None |  |  |  | 1 | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `terms_and_conditions_help` | Terms and Conditions Help | HTML | <h4>Standard Terms and Conditions Example</h4>

<pre>Delivery Terms for Order number {{ name }}

-Order Date : {{ transaction_date }} 
-Expected Delivery Date : {{ delivery_date }}
</pre>

<h4>How to get fieldnames</h4>

<p>The fieldnames you can use in your email template are the fields in the document from which you are sending the email. You can find out the fields of any documents via Setup &gt; Customize Form View and selecting the document type (e.g. Sales Invoice)</p>

<h4>Templating</h4>

<p>Templates are compiled using the Jinja Templating Language. To learn more about Jinja, <a class="strong" href="http://jinja.pocoo.org/docs/dev/templates/">read this documentation.</a></p> |  |  |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `hr` | HR | Check | None |  |  |  | 1 | None |



### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/terms_and_conditions/terms_and_conditions.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

// frappe.ui.form.on("Terms and Conditions", {
// 	refresh(frm) {}
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
