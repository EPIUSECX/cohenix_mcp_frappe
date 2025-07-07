# Master Control Plan: `Website Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Webshop`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Naming Series | Select | WEB-ITM-.#### |  | ✅ |  | WEB-ITM-.#### | None |
| `web_item_name` | Website Item Name | Data | None | ✅ |  |  | None | Website display name |
| `route` | Route | Small Text | None |  |  |  | None | None |
| `has_variants` | Has Variants | Check | None |  |  | ✅ | 0 | None |
| `variant_of` | Variant Of | Link | Item |  |  | ✅ | None | None |
| `published` | Published | Check | None |  |  |  | 1 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `description` | Item Description | Text Editor | None |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  |  | None | None |
| `display_section` | Display Images | Section Break | None |  |  |  | None | None |
| `website_image` | Website Image | Attach Image | None |  | ✅ |  | None | Item Image (if not slideshow) |
| `website_image_alt` | Image Description | Data | None |  |  |  | None | Image Alternative Text |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `slideshow` | Slideshow | Link | Website Slideshow |  |  |  | None | Show a slideshow at the top of the page |
| `thumbnail` | Thumbnail | Data | None |  |  | ✅ | None | None |
| `stock_information_section` | Stock Information | Section Break | None |  |  |  | None | None |
| `website_warehouse` | Website Warehouse | Link | Warehouse |  |  |  | None | Show Stock availability based on this warehouse. |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `on_backorder` | On Backorder | Check | None |  |  |  | 0 | Indicate that Item is available on backorder and not usually pre-stocked |
| `section_break_17` | Display Information | Section Break | None |  |  |  | None | None |
| `short_description` | Short Website Description | Small Text | None |  |  |  | None | Short Description for List View |
| `web_long_description` | Website Description | Text Editor | None |  |  |  | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `website_specifications` | Website Specifications | Table | Item Website Specification |  |  |  | None | None |
| `copy_from_item_group` | Copy From Item Group | Button | None |  |  |  | None | None |
| `display_additional_information_section` | Display Additional Information | Section Break | None |  |  |  | None | None |
| `show_tabbed_section` | Add Section with Tabs | Check | None |  |  |  | 0 | None |
| `tabs` | Tabs | Table | Website Item Tabbed Section |  |  |  | None | None |
| `recommended_items_section` | Recommended Items | Section Break | None |  |  |  | None | None |
| `recommended_items` | Recommended/Similar Items | Table | Recommended Items |  |  |  | None | None |
| `offers_section` | Offers | Section Break | None |  |  |  | None | None |
| `offers` | Offers to Display | Table | Website Offer |  |  |  | None | None |
| `section_break_6` | Search and SEO | Section Break | None |  |  |  | None | None |
| `ranking` | Ranking | Int | None |  |  |  | None | Items with higher ranking will be shown higher |
| `set_meta_tags` | Set Meta Tags | Button | None |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `website_item_groups` | Website Item Groups | Table | Website Item Group |  |  |  | None | List this Item in multiple groups on the website. |
| `advanced_display_section` | Advanced Display Content | Section Break | None |  |  |  | None | None |
| `website_content` | Website Content | HTML Editor | None |  |  |  | None | You can use any valid Bootstrap 4 markup in this field. It will be shown on your Item Page. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 5

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/website_item/website_item.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on('Website Item', {
	onload: (frm) => {
		// should never check Private
		frm.fields_dict["website_image"].df.is_private = 0;
	},

	refresh: (frm) => {
		frm.add_custom_button(__("Prices"), function() {
			frappe.set_route("List", "Item Price", {"item_code": frm.doc.item_code});
		}, __("View"));

		frm.add_custom_button(__("Stock"), function() {
			frappe.route_options = {
				"item_code": frm.doc.item_code
			};
			frappe.set_route("query-report", "Stock Balance");
		}, __("View"));

		frm.add_custom_button(__("Webshop Settings"), function() {
			frappe.set_route("Form", "Webshop Settings");
		}, __("View"));
	},

	copy_from_item_group: (frm) => {
		return frm.call({
			doc: frm.doc,
			method: "copy_specification_from_item_group"
		});
	},

	set_meta_tags: (frm) => {
		frappe.utils.set_meta_tag(frm.doc.route);
	}
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
