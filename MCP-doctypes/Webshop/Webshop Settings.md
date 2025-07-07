# Master Control Plan: `Webshop Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Webshop`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `products_per_page` | Products per Page | Int | None |  |  |  | 6 | None |
| `filter_categories_section` | Filters and Categories | Section Break | None |  |  |  | None | None |
| `enable_field_filters` | Enable Field Filters (Categories) | Check | None |  |  |  | 0 | The field filters will also work as categories in the <b>Shop by Category</b> page. |
| `filter_fields` | Website Item Fields | Table | Website Filter Field |  |  |  | None | None |
| `enable_attribute_filters` | Enable Attribute Filters | Check | None |  |  |  | 0 | None |
| `filter_attributes` | Attributes | Table | Website Attribute |  |  |  | None | None |
| `display_settings_section` | Display Settings | Section Break | None |  |  |  | None | None |
| `hide_variants` | Hide Variants | Check | None |  |  |  | 0 | None |
| `enable_variants` | Enable Variant Selection | Check | None |  |  |  | 0 | None |
| `show_price` | Show Price | Check | None |  |  |  | 0 | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `login_required_to_view_products` | Login Required to View Products | Check | None |  |  |  | 0 | None |
| `show_stock_availability` | Show Stock Availability | Check | None |  |  |  | 0 | None |
| `show_quantity_in_website` | Show Stock Quantity | Check | None |  |  |  | 0 | None |
| `allow_items_not_in_stock` | Allow items not in stock to be added to cart | Check | None |  |  |  | 0 | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `show_apply_coupon_code_in_website` | Show Apply Coupon Code | Check | None |  |  |  | 0 | None |
| `show_contact_us_button` | Show Contact Us Button | Check | None |  |  |  | 0 | None |
| `show_attachments` | Show Public Attachments | Check | None |  |  |  | 0 | None |
| `section_break_18` | Shopping Cart | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `price_list` | Price List | Link | Price List |  |  |  | None | Prices will not be shown if Price List is not set |
| `enabled` | Enable Shopping Cart | Check | None |  |  |  | 0 | None |
| `store_page_docs` | None | HTML | None |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `default_customer_group` | Default Customer Group | Link | Customer Group |  |  |  | None | None |
| `quotation_series` | Quotation Series | Select | None |  |  |  | None | None |
| `allow_non_website_items_in_cart_quotation` | Allow Non Website Items in Cart Quotation | Check | None |  |  |  | 0 | None |
| `checkout_settings_section` | Checkout Settings | Section Break | None |  |  |  | None | None |
| `enable_checkout` | Enable Checkout | Check | None |  |  |  | 0 | None |
| `show_price_in_quotation` | Show Price in Quotation | Check | None |  |  |  | 0 | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `save_quotations_as_draft` | Save Quotations as Draft | Check | None |  |  |  | 0 | None |
| `payment_gateway_account` | Payment Gateway Account | Link | Payment Gateway Account |  |  |  | None | None |
| `payment_success_url` | Payment Success Url | Select | 
Orders
Invoices
My Account |  |  |  | Orders | After payment completion redirect user to selected page. |
| `add_ons_section` | Add-ons | Section Break | None |  |  |  | None | None |
| `enable_wishlist` | Enable Wishlist | Check | None |  |  |  | 0 | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `enable_reviews` | Enable Reviews and Ratings | Check | None |  |  |  | 0 | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `enable_recommendations` | Enable Recommendations | Check | None |  |  |  | 0 | None |
| `item_search_settings_section` | Item Search Settings | Section Break | None |  |  |  | None | None |
| `redisearch_warning` | Redisearch Warning | HTML | <p class="alert alert-warning">Redisearch is not loaded. If you want to use the advanced product search feature, refer <a class="alert-link" href="https://docs.erpnext.com/docs/v13/user/manual/en/setting-up/articles/installing-redisearch" target="_blank">here</a>.</p> |  |  |  | None | None |
| `search_index_fields` | Search Index Fields | Small Text | None |  |  |  | None | None |
| `is_redisearch_enabled` | Enable Redisearch | Check | None |  |  |  | 0 | None |
| `is_redisearch_loaded` | Is Redisearch Loaded | Check | None |  | ✅ |  | 0 | None |
| `shop_by_category_section` | Shop by Category | Section Break | None |  |  |  | None | None |
| `slideshow` | Slideshow | Link | Website Slideshow |  |  |  | None | None |
| `guest_display_settings_section` | Guest Display Settings | Section Break | None |  |  |  | None | None |
| `hide_price_for_guest` | Hide Price for Guest | Check | None |  |  |  | 0 | None |
| `redirect_on_action` | Redirect on Action | Data | None |  |  |  | None | Link to redirect Guest on actions that need login such as add to cart, wishlist, etc. <b>E.g.: /login</b> |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/webshop_settings/webshop_settings.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Webshop Settings", {
	onload: function(frm) {
		if(frm.doc.__onload && frm.doc.__onload.quotation_series) {
			frm.fields_dict.quotation_series.df.options = frm.doc.__onload.quotation_series;
			frm.refresh_field("quotation_series");
		}

		frm.set_query('payment_gateway_account', function() {
			return { 'filters': { 
				'payment_channel': ['in', ["Email", "Phone"]] 
			 } };
		});
	},
	refresh: function(frm) {
		if (frm.doc.enabled) {
			frm.get_field('store_page_docs').$wrapper.removeClass('hide-control').html(
				`<div>${__("Follow these steps to create a landing page for your store")}:
					<a href="https://docs.erpnext.com/docs/user/manual/en/website/store-landing-page"
						style="color: var(--gray-600)">
						docs/store-landing-page
					</a>
				</div>`
			);
		}

		frappe.model.with_doctype("Website Item", () => {
			const web_item_meta = frappe.get_meta('Website Item');

			const valid_fields = web_item_meta.fields.filter(df =>
				["Link", "Table MultiSelect"].includes(df.fieldtype) && !df.hidden
			).map(df =>
				({ label: df.label, value: df.fieldname })
			);

			frm.get_field("filter_fields").grid.update_docfield_property(
				'fieldname', 'options', valid_fields
			);
		});
	},
	enabled: function(frm) {
		if (frm.doc.enabled === 1) {
			frm.set_value('enable_variants', 1);
		}
		else {
			frm.set_value('company', '');
			frm.set_value('price_list', '');
			frm.set_value('default_customer_group', '');
			frm.set_value('quotation_series', '');
		}
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
