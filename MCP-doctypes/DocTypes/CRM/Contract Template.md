# Master Control Plan: `Contract Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  |  |  | None | None |
| `contract_terms` | Contract Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `sb_fulfilment` | None | Section Break | None |  |  |  | None | None |
| `requires_fulfilment` | Requires Fulfilment | Check | None |  |  |  | 0 | None |
| `fulfilment_terms` | Fulfilment Terms and Conditions | Table | Contract Template Fulfilment Terms |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `contract_template_help` | Contract Template Help | HTML | <h4>Contract Template Example</h4>

<pre>Contract for Customer {{ party_name }}

-Valid From : {{ start_date }} 
-Valid To : {{ end_date }}
</pre>

<h4>How to get fieldnames</h4>

<p>The field names you can use in your Contract Template are the fields in the Contract for which you are creating the template. You can find out the fields of any documents via Setup &gt; Customize Form View and selecting the document type (e.g. Contract)</p>

<h4>Templating</h4>

<p>Templates are compiled using the Jinja Templating Language. To learn more about Jinja, <a class="strong" href="http://jinja.pocoo.org/docs/dev/templates/">read this documentation.</a></p> |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/contract_template/contract_template.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Contract Template", {
	refresh: function (frm) {},
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
