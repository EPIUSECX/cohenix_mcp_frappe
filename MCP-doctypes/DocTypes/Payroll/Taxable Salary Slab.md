# Master Control Plan: `Taxable Salary Slab`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
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
| `from_amount` | From Amount | Currency | currency | ✅ |  |  | 0 | None |
| `to_amount` | To Amount | Currency | currency |  |  |  | None | None |
| `percent_deduction` | Percent Deduction | Percent | None | ✅ |  |  | 0 | None |
| `condition` | Condition | Code | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `html_6` | None | HTML | <h4>Condition Examples</h4>
<ol>
<li>Applying tax if employee born between 31-12-1937 and 01-01-1958 (Employees aged 60 to 80)<br>
<code>Condition: date_of_birth&gt;date(1937, 12, 31) and date_of_birth&lt;date(1958, 01, 01)</code></li><br><li>Applying tax by employee gender<br>
<code>Condition: gender=="Male"</code></li><br>
<li>Applying tax by Salary Component<br>
<code>Condition: base &gt; 10000</code></li></ol> |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
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
