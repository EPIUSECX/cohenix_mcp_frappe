# Master Control Plan: `Shareholder`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | None | Select | ACC-SH-.YYYY.- |  |  |  | None | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `folio_no` | Folio no. | Data | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `is_company` | Is Company | Check | None |  | ✅ | ✅ | 0 | None |
| `address_contacts` | Address and Contacts | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  | ✅ | None | None |
| `section_break_3` | Share Balance | Section Break | None |  |  |  | None | None |
| `share_balance` | Share Balance | Table | Share Balance |  |  | ✅ | None | None |
| `contact_list` | Contact List | Code | None |  | ✅ | ✅ | None | Hidden list maintaining the list of contacts linked to Shareholder |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/shareholder/shareholder.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Shareholder", {
	refresh: function (frm) {
		frm.toggle_display(["contact_html"], !frm.doc.__islocal);

		if (frm.doc.__islocal) {
			hide_field(["contact_html"]);
			frappe.contacts.clear_address_and_contact(frm);
		} else {
			if (frm.doc.is_company) {
				hide_field(["company"]);
			} else {
				unhide_field(["contact_html"]);
				frappe.contacts.render_address_and_contact(frm);
			}
		}

		if (frm.doc.folio_no != undefined) {
			frm.add_custom_button(__("Share Balance"), function () {
				frappe.route_options = {
					shareholder: frm.doc.name,
				};
				frappe.set_route("query-report", "Share Balance");
			});
			frm.add_custom_button(__("Share Ledger"), function () {
				frappe.route_options = {
					shareholder: frm.doc.name,
				};
				frappe.set_route("query-report", "Share Ledger");
			});
			let fields = ["title", "folio_no", "company"];
			fields.forEach((fieldname) => {
				frm.fields_dict[fieldname].df.read_only = 1;
				frm.refresh_fields(fieldname);
			});
			$(`.btn:contains("New Contact"):visible`).hide();
			$(`.btn:contains("Edit"):visible`).hide();
		}
	},
	validate: (frm) => {
		let contact_list = {
			contacts: [],
		};
		$("div[data-fieldname=contact_html] > .address-box").each((index, ele) => {
			contact_list.contacts.push(ele.innerText.replace(" Edit", ""));
		});
		frm.doc.contact_list = JSON.stringify(contact_list);
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
