# Master Control Plan: `Contact Us Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Settings for Contact Us Page

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `disable_contact_us` | Disable Contact Us Page | Check | None |  |  |  | 0 | None |
| `introduction_section` | Introduction | Section Break | None |  |  |  | None | None |
| `forward_to_email` | Forward To Email Address | Data | Email |  |  |  | None | Send enquiries to this email address |
| `heading` | Heading | Data | None |  |  |  | None | Default: "Contact Us" |
| `introduction` | Introduction | Text Editor | None |  |  |  | None | Introductory information for the Contact Us Page |
| `query_options` | Query Options | Small Text | None |  |  |  | None | Contact options, like "Sales Query, Support Query" etc each on a new line or separated by commas. |
| `address` | Address | Section Break | None |  |  |  | None | None |
| `address_title` | Address Title | Data | None |  |  |  | None | None |
| `address_line1` | Address Line 1 | Data | None |  |  |  | None | None |
| `address_line2` | Address Line 2 | Data | None |  |  |  | None | None |
| `city` | City | Data | None |  |  |  | None | None |
| `state` | State/Province | Data | None |  |  |  | None | None |
| `pincode` | Pincode | Data | None |  |  |  | None | None |
| `country` | Country | Data | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `phone` | Phone | Data | Phone |  |  |  | None | None |
| `email_id` | Email Id | Data | Email |  |  |  | None | None |
| `skype` | Skype | Data | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/contact_us_settings/contact_us_settings.js`
```javascript
frappe.ui.form.on("Contact Us Settings", {
	refresh: function (frm) {
		frm.sidebar
			.add_user_action(__("See on Website"))
			.attr("href", "/contact")
			.attr("target", "_blank");
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
