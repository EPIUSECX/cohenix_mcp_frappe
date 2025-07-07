# Master Control Plan: `Print Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Printing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `pdf_settings` | PDF Settings | Section Break | None |  |  |  | None | None |
| `send_print_as_pdf` | Send Print as PDF | Check | None |  |  |  | 1 | Send Email Print Attachments as PDF (Recommended) |
| `repeat_header_footer` | Repeat Header and Footer | Check | None |  |  |  | 1 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `pdf_page_size` | PDF Page Size | Select | A0
A1
A2
A3
A4
A5
A6
A7
A8
A9
B0
B1
B2
B3
B4
B5
B6
B7
B8
B9
B10
C5E
Comm10E
DLE
Executive
Folio
Ledger
Legal
Letter
Tabloid
Custom |  |  |  | A4 | None |
| `pdf_page_height` | PDF Page Height (in mm) | Float | None |  |  |  | None | None |
| `pdf_page_width` | PDF Page Width (in mm) | Float | None |  |  |  | None | None |
| `view_link_in_email` | Page Settings | Section Break | None |  |  |  | None | None |
| `with_letterhead` | Print with letterhead | Check | None |  |  |  | 1 | None |
| `compact_item_print` | Compact Item Print | Check | None |  |  |  | 1 | None |
| `print_uom_after_quantity` | Print UOM after Quantity | Check | None |  |  |  | 0 | None |
| `allow_print_for_draft` | Allow Print for Draft | Check | None |  |  |  | 1 | None |
| `add_draft_heading` | Always add "Draft" Heading for printing draft documents | Check | None |  |  |  | 1 | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `allow_page_break_inside_tables` | Allow page break inside tables | Check | None |  |  |  | 0 | None |
| `allow_print_for_cancelled` | Allow Print for Cancelled | Check | None |  |  |  | 0 | None |
| `print_taxes_with_zero_amount` | Print taxes with zero amount | Check | None |  |  |  | 0 | None |
| `server_printer` | Print Server | Section Break | None |  |  |  | None | None |
| `enable_print_server` | Enable Print Server | Check | None |  |  |  | 0 | None |
| `raw_printing_section` | Raw Printing | Section Break | None |  |  |  | None | None |
| `enable_raw_printing` | Enable Raw Printing | Check | None |  |  |  | 0 | None |
| `print_style_section` | Print Style | Section Break | None |  |  |  | None | None |
| `print_style` | Print Style | Link | Print Style |  |  |  | Redesign | None |
| `print_style_preview` | Print Style Preview | HTML | None |  |  |  | None | None |
| `section_break_8` | Fonts | Section Break | None |  |  |  | None | None |
| `font` | Font | Select | Default
Helvetica Neue
Arial
Helvetica
Inter
Verdana
Monospace |  |  |  | Default | None |
| `font_size` | Font Size | Float | None |  |  |  | None | In points. Default is 9. |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `print_taxes_with_zero_amount` | Print taxes with zero amount | Check | None |  |  |  | 0 | None |
| `print_uom_after_quantity` | Print UOM after Quantity | Check | None |  |  |  | 0 | None |
| `compact_item_print` | Compact Item Print | Check | None |  |  |  | 1 | None |



### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/printing/doctype/print_settings/print_settings.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Print Settings", {
	print_style: function (frm) {
		frappe.db.get_value("Print Style", frm.doc.print_style, "preview").then((r) => {
			if (r.message.preview) {
				frm.get_field("print_style_preview").$wrapper.html(
					`<img src="${r.message.preview}" class="img-responsive">`
				);
			} else {
				frm.get_field("print_style_preview").$wrapper.html(
					`<p style="margin: 60px 0px" class="text-center text-muted">${__(
						"No Preview"
					)}</p>`
				);
			}
		});
	},
	onload: function (frm) {
		frm.script_manager.trigger("print_style");
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
