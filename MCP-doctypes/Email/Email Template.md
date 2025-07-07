# Master Control Plan: `Email Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject` | Subject | Data | None | ✅ |  |  | None | None |
| `use_html` | Use HTML | Check | None |  |  |  | 0 | None |
| `response_html` | Response  | Code | Jinja |  |  |  | None | None |
| `response` | Response | Text Editor | None |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `email_reply_help` | Email Reply Help | HTML | <h4>Email Reply Example</h4>

<pre>Order Overdue

Transaction {{ name }} has exceeded Due Date. Please take necessary action.

Details

- Customer: {{ customer }}
- Amount: {{ grand_total }}
</pre>

<h4>How to get fieldnames</h4>

<p>The fieldnames you can use in your email template are the fields in the document from which you are sending the email. You can find out the fields of any documents via Setup &gt; Customize Form View and selecting the document type (e.g. Sales Invoice)</p>

<h4>Templating</h4>

<p>Templates are compiled using the Jinja Templating Language. To learn more about Jinja, <a class="strong" href="http://jinja.pocoo.org/docs/dev/templates/">read this documentation.</a></p>
 |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_template/email_template.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Email Template", {
	refresh: function () {},
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
