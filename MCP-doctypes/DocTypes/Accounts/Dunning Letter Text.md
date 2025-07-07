# Master Control Plan: `Dunning Letter Text`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `language` | Language | Link | Language |  |  |  | None | None |
| `is_default_language` | Is Default Language | Check | None |  |  |  | 0 | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `body_text` | Body Text | Text Editor | None |  |  |  | None | Letter or Email Body Text |
| `closing_text` | Closing Text | Text Editor | None |  |  |  | None | Letter or Email Closing Text |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `body_and_closing_text_help` | Body and Closing Text Help | HTML | <h4>Body Text and Closing Text Example</h4>

<div>We have noticed that you have not yet paid invoice {{sales_invoice}} for {{frappe.db.get_value("Currency", currency, "symbol")}} {{outstanding_amount}}. This is a friendly reminder that the invoice was due on {{due_date}}. Please pay the amount due immediately to avoid any further dunning cost.</div>

<h4>How to get fieldnames</h4>

<p>The fieldnames you can use in your template are the fields in the document. You can find out the fields of any documents via Setup &gt; Customize Form View and selecting the document type (e.g. Sales Invoice)</p>

<h4>Templating</h4>

<p>Templates are compiled using the Jinja Templating Language. To learn more about Jinja, <a class="strong" href="http://jinja.pocoo.org/docs/dev/templates/">read this documentation.</a></p> |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)




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
