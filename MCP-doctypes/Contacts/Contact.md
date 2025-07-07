# Master Control Plan: `Contact`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Contacts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Maintenance Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Maintenance User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `contact_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `first_name` | First Name | Data | None |  |  |  | None | None |
| `middle_name` | Middle Name | Data | None |  |  |  | None | None |
| `last_name` | Last Name | Data | None |  |  |  | None | None |
| `full_name` | Full Name | Data | None |  | ✅ | ✅ | None | None |
| `email_id` | Email Address | Data | Email |  |  | ✅ | None | None |
| `user` | User Id | Link | User |  |  |  | None | None |
| `address` | Address | Link | Address |  |  |  | None | None |
| `sync_with_google_contacts` | Sync with Google Contacts | Check | None |  |  |  | 0 | None |
| `cb00` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Passive
Open
Replied |  |  |  | Passive | None |
| `salutation` | Salutation | Link | Salutation |  |  |  | None | None |
| `designation` | Designation | Data | None |  |  |  | None | None |
| `gender` | Gender | Link | Gender |  |  |  | None | None |
| `phone` | Phone | Data | Phone |  |  | ✅ | None | None |
| `mobile_no` | Mobile No | Data | Phone |  |  | ✅ | None | None |
| `company_name` | Company Name | Data | None |  |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `sb_00` | Google Contacts | Section Break | None |  |  |  | None | None |
| `google_contacts` | Google Contacts | Link | Google Contacts |  |  |  | None | None |
| `google_contacts_id` | Google Contacts Id | Data | None |  |  | ✅ | None | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `pulled_from_google_contacts` | Pulled from Google Contacts | Check | None |  |  | ✅ | 0 | None |
| `sb_01` | Contact Details | Section Break | None |  |  |  | None | None |
| `email_ids` | Email IDs | Table | Contact Email |  |  |  | None | None |
| `phone_nos` | Contact Numbers | Table | Contact Phone |  |  |  | None | None |
| `contact_details` | Reference | Section Break | fa fa-pushpin |  |  |  | None | None |
| `links` | Links | Table | Dynamic Link |  |  |  | None | None |
| `is_primary_contact` | Is Primary Contact | Check | None |  |  |  | 0 | None |
| `is_billing_contact` | Is Billing Contact | Check | None |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `department` | Department | Data | None |  |  |  | None | None |
| `unsubscribed` | Unsubscribed | Check | None |  |  |  | 0 | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_billing_contact` | Is Billing Contact | Check | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/contacts/doctype/contact/contact.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Contact", {
	onload(frm) {
		frm.email_field = "email_id";
	},
	refresh: function (frm) {
		if (frm.doc.__islocal) {
			const last_doc = frappe.contacts.get_last_doc(frm);
			if (
				frappe.dynamic_link &&
				frappe.dynamic_link.doc &&
				frappe.dynamic_link.doc.name == last_doc.docname
			) {
				frm.set_value("links", "");
				frm.add_child("links", {
					link_doctype: frappe.dynamic_link.doctype,
					link_name: frappe.dynamic_link.doc[frappe.dynamic_link.fieldname],
				});
			}
		}

		if (
			!frm.doc.user &&
			!frm.is_new() &&
			frm.perm[0].write &&
			frappe.boot.user.can_create.includes("User")
		) {
			frm.add_custom_button(__("Invite as User"), function () {
				return frappe.call({
					method: "frappe.contacts.doctype.contact.contact.invite_user",
					args: {
						contact: frm.doc.name,
					},
					callback: function (r) {
						frm.set_value("user", r.message);
					},
				});
			});
		}
		frm.set_query("link_doctype", "links", function () {
			return {
				query: "frappe.contacts.address_and_contact.filter_dynamic_link_doctypes",
				filters: {
					fieldtype: "HTML",
					fieldname: "contact_html",
				},
			};
		});
		frm.refresh_field("links");

		let numbers = frm.doc.phone_nos;
		if (numbers && numbers.length && frappe.phone_call.handler) {
			frm.add_custom_button(__("Call"), () => {
				numbers = frm.doc.phone_nos
					.sort((prev, next) => next.is_primary_mobile_no - prev.is_primary_mobile_no)
					.map((d) => d.phone);
				frappe.phone_call.handler(numbers);
			});
		}

		if (frm.doc.links && frm.doc.links.length > 0) {
			const filtered_links = frm.doc.links.filter(
				(link) => link.link_doctype && link.link_name
			);

			if (filtered_links.length > 0) {
				frappe.call({
					method: "frappe.contacts.doctype.contact.contact.address_query",
					args: { links: filtered_links },
					callback: function (r) {
						if (r && r.message) {
							frm.set_query("address", function () {
								return {
									filters: {
										name: ["in", r.message],
									},
								};
							});
						}
					},
				});
			}

			for (const link of filtered_links) {
				frm.add_custom_button(
					__("{0}: {1}", [__(link.link_doctype), __(link.link_name)]),
					function () {
						frappe.set_route("Form", link.link_doctype, link.link_name);
					},
					__("Links")
				);
			}
		}

		if (!frm.is_dirty()) {
			frm.page.add_menu_item(__("Download vCard"), function () {
				window.open(
					`/api/method/frappe.contacts.doctype.contact.contact.download_vcard?contact=${encodeURIComponent(
						frm.doc.name
					)}`,
					"_blank"
				);
			});
		}
	},
	validate: function (frm) {
		// clear linked customer / supplier / sales partner on saving...
		if (frm.doc.links) {
			frm.doc.links.forEach(function (d) {
				frappe.model.remove_from_locals(d.link_doctype, d.link_name);
			});
		}
	},
	after_save: function (frm) {
		frappe.run_serially([
			() => frappe.timeout(1),
			() => {
				const last_doc = frappe.contacts.get_last_doc(frm);
				if (
					frappe.dynamic_link &&
					frappe.dynamic_link.doc &&
					frappe.dynamic_link.doc.name == last_doc.docname
				) {
					for (let i in frm.doc.links) {
						let link = frm.doc.links[i];
						if (
							last_doc.doctype == link.link_doctype &&
							last_doc.docname == link.link_name
						) {
							frappe.set_route("Form", last_doc.doctype, last_doc.docname);
						}
					}
				}
			},
		]);
	},
	sync_with_google_contacts: function (frm) {
		if (frm.doc.sync_with_google_contacts) {
			frappe.db.get_value(
				"Google Contacts",
				{ email_id: frappe.session.user },
				"name",
				(r) => {
					if (r && r.name) {
						frm.set_value("google_contacts", r.name);
					}
				}
			);
		}
	},
});

frappe.ui.form.on("Dynamic Link", {
	link_name: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (child.link_name) {
			frappe.model.with_doctype(child.link_doctype, function () {
				var title_field = frappe.get_meta(child.link_doctype).title_field || "name";
				frappe.model.get_value(
					child.link_doctype,
					child.link_name,
					title_field,
					function (r) {
						frappe.model.set_value(cdt, cdn, "link_title", r[title_field]);
					}
				);
			});
		}
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
