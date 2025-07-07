# Master Control Plan: `Workflow Transition`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Workflow`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Defines actions on states and the next step and allowed roles.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `state` | State | Link | Workflow State | ✅ |  |  | None | None |
| `action` | Action | Link | Workflow Action Master | ✅ |  |  | None | None |
| `next_state` | Next State | Link | Workflow State | ✅ |  |  | None | None |
| `allowed` | Allowed | Link | Role | ✅ |  |  | None | None |
| `allow_self_approval` | Allow Self Approval | Check | None |  |  |  | 1 | Allow approval for creator of the document |
| `send_email_to_creator` | Send Email To Creator | Check | None |  |  |  | 0 | None |
| `conditions` | Conditions | Section Break | None |  |  |  | None | None |
| `condition` | Condition | Code | Python |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `example` | Example | HTML | <pre><code>doc.grand_total &gt; 0</code></pre>

<p>Conditions should be written in simple Python. Please use properties available in the form only.</p>
<p>Allowed functions:
</p><ul>
<li>frappe.db.get_value</li>
<li>frappe.db.get_list</li>
<li>frappe.session</li>
<li>frappe.utils.now_datetime</li>
<li>frappe.utils.get_datetime</li>
<li>frappe.utils.add_to_date</li>
<li>frappe.utils.now</li>
</ul>
<p>Example: </p><pre><code>doc.creation &gt; frappe.utils.add_to_date(frappe.utils.now_datetime(), days=-5, as_string=True, as_datetime=True) </code></pre><p></p> |  |  |  | None | None |
| `workflow_builder_id` | Workflow Builder ID | Data | None |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
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
