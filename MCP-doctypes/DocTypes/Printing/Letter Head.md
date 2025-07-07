# Master Control Plan: `Letter Head`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Printing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:letter_head_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `letter_head_name` | Letter Head Name | Data | None | ✅ |  |  | None | None |
| `source` | Letter Head Based On | Select | Image
HTML |  |  |  | None | None |
| `footer_source` | Footer Based On | Select | Image
HTML |  |  |  | HTML | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `is_default` | Default Letter Head | Check | None |  |  |  | 0 | None |
| `letter_head_image_section` | Letter Head Image | Section Break | None |  |  |  | None | None |
| `image` | Image | Attach Image | None |  |  |  | None | None |
| `image_height` | Image Height | Float | None |  |  |  | None | None |
| `image_width` | Image Width | Float | None |  |  |  | None | None |
| `align` | Align | Select | Left
Right
Center |  |  |  | Left | None |
| `header_section` | Header | Section Break | None |  |  |  | None | None |
| `content` | Header HTML | HTML Editor | None |  |  |  | None | Letter Head in HTML |
| `footer_section` | Footer | Section Break | None |  |  |  | None | None |
| `footer` | Footer HTML | HTML Editor | None |  |  |  | None | Footer will display correctly only in PDF |
| `footer_image_section` | Footer Image | Section Break | None |  |  |  | None | None |
| `footer_image` | Image | Attach Image | None |  |  |  | None | None |
| `footer_image_height` | Image Height | Float | None |  |  |  | None | None |
| `footer_image_width` | Image Width | Float | None |  |  |  | None | None |
| `footer_align` | Align | Select | Left
Right
Center |  |  |  | None | None |
| `scripts_section` | Scripts | Section Break | None |  |  |  | None | None |
| `header_script` | Header Script | Code | Javascript |  |  |  | None | None |
| `footer_script` | Footer Script | Code | Javascript |  |  |  | None | None |
| `instructions` | Instructions | HTML | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/printing/doctype/letter_head/letter_head.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Letter Head", {
	setup(frm) {
		frm.get_field("instructions").html(INSTRUCTIONS);
	},

	refresh: function (frm) {
		frm.flag_public_attachments = true;
	},

	validate: (frm) => {
		["header_script", "footer_script"].forEach((field) => {
			if (!frm.doc[field]) return;

			try {
				eval(frm.doc[field]);
			} catch (e) {
				frappe.throw({
					title: __("Error in Header/Footer Script"),
					indicator: "orange",
					message: '<pre class="small"><code>' + e.stack + "</code></pre>",
				});
			}
		});
	},
});

const INSTRUCTIONS = `<h4>${__("Letter Head Scripts")}</h4>
<p>${__("Header/Footer scripts can be used to add dynamic behaviours.")}</p>
<pre>
<code>
// ${__(
	"The following Header Script will add the current date to an element in 'Header HTML' with class 'header-content'"
)}
var el = document.getElementsByClassName("header-content");
if (el.length > 0) {
	el[0].textContent += " " + new Date().toGMTString();
}
</code>
</pre>
<p>${__("You can also access wkhtmltopdf variables (valid only in PDF print):")}</p>
<pre>
<code>
// ${__("Get Header and Footer wkhtmltopdf variables")}
// ${__("Snippet and more variables:  {0}", ["https://wkhtmltopdf.org/usage/wkhtmltopdf.txt"])}
var vars = {};
var query_strings_from_url = document.location.search.substring(1).split('&');
for (var query_string in query_strings_from_url) {
	if (query_strings_from_url.hasOwnProperty(query_string)) {
		var temp_var = query_strings_from_url[query_string].split('=', 2);
		vars[temp_var[0]] = decodeURI(temp_var[1]);
	}
}
var el = document.getElementsByClassName("header-content");
if (el.length > 0 && vars["page"] == 1) {
	el[0].textContent += " : " + vars["date"];
}
</code>
</pre>`;

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
