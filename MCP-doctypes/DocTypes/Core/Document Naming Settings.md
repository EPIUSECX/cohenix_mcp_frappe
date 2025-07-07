# Master Control Plan: `Document Naming Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Configure various aspects of how document naming works like naming series, current counter.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series_tab` | Naming Series | Tab Break | None |  |  |  | None | None |
| `setup_series` | Setup Series for transactions | Section Break | None |  |  |  | None | Set Naming Series options on your transactions. |
| `transaction_type` | Select Transaction | Autocomplete | None |  |  |  | None | None |
| `naming_series_options` | Series List for this Transaction | Text | None |  |  |  | None | None |
| `user_must_always_select` | User must always select | Check | None |  |  |  | 0 | Check this if you want to force the user to select a series before saving. There will be no default if you check this. |
| `update` | Update | Button | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `try_naming_series` | Try a Naming Series | Data | None |  |  |  | None | Get a preview of generated names with a series. |
| `series_preview` | Preview of generated names | Text | None |  |  | ✅ | None | None |
| `help_html` | Help HTML | HTML | <div class="well">
    Edit list of Series in the box. Rules:
    <ul>
        <li>Each Series Prefix on a new line.</li>
        <li>Allowed special characters are "/" and "-"</li>
        <li>
            Optionally, set the number of digits in the series using dot (.)
            followed by hashes (#). For example, ".####" means that the series
            will have four digits. Default is five digits.
        </li>
        <li>
            You can also use variables in the series name by putting them
            between (.) dots
            <br>
            Supported Variables:
            <ul>
                <li><code>.YYYY.</code> - Year in 4 digits</li>
                <li><code>.YY.</code> - Year in 2 digits</li>
                <li><code>.MM.</code> - Month</li>
                <li><code>.DD.</code> - Day of month</li>
                <li><code>.WW.</code> - Week of the year</li>
                <li>
                    <code>.{fieldname}.</code> - fieldname on the document e.g.
                    <code>branch</code>
                </li>
                <li><code>.FY.</code> - Fiscal Year (requires ERPNext to be installed)</li>
                <li><code>.ABBR.</code> - Company Abbreviation (requires ERPNext to be installed)</li>
            </ul>
        </li>
    </ul>
    Examples:
    <ul>
        <li>INV-</li>
        <li>INV-10-</li>
        <li>INVK-</li>
        <li>INV-.YYYY.-.{branch}.-.MM.-.####</li>
    </ul>
</div>
<br>
 |  |  |  | None | None |
| `update_series` | Update Series Counter | Section Break | None |  |  |  | None | Change the starting / current sequence number of an existing series. <br>

Warning: Incorrectly updating counters can prevent documents from getting created.  |
| `prefix` | Prefix | Autocomplete | None |  |  |  | None | None |
| `current_value` | Current Value | Int | None |  |  |  | None | This is the number of the last created transaction with this prefix |
| `update_series_start` | Update Series Number | Button | update_series_start |  |  |  | None | None |
| `amended_documents_section` | Amended Documents | Section Break | None |  |  |  | None | Configure how amended documents will be named.<br>

Default behaviour is to follow an amend counter which adds a number to the end of the original name indicating the amended version. <br>

Default Naming will make the amended document to behave same as new documents. |
| `default_amend_naming` | Default Amendment Naming | Select | Amend Counter
Default Naming | ✅ |  |  | Amend Counter | None |
| `amend_naming_override` | Amendment Naming Override | Table | Amended Document Naming Settings |  |  |  | None | None |
| `update_amendment_naming` | Update Amendment Naming | Button | update_amendment_rule |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/document_naming_settings/document_naming_settings.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Document Naming Settings", {
	setup: function (frm) {
		frm.set_query("document_type", "amend_naming_override", () => {
			return {
				filters: {
					is_submittable: 1,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.trigger("setup_transaction_autocomplete");
		frm.disable_save();
	},

	setup_transaction_autocomplete: function (frm) {
		frappe.call({
			method: "get_transactions_and_prefixes",
			doc: frm.doc,
			callback: function (r) {
				frm.fields_dict.transaction_type.set_data(r.message.transactions);
				frm.fields_dict.prefix.set_data(r.message.prefixes);
			},
		});
	},

	transaction_type: function (frm) {
		frm.set_value("user_must_always_select", 0);
		frappe.call({
			method: "get_options",
			doc: frm.doc,
			callback: function (r) {
				frm.set_value("naming_series_options", r.message);
				if (r.message && r.message.split("\n")[0] == "")
					frm.set_value("user_must_always_select", 1);
			},
		});
	},

	prefix: function (frm) {
		frappe.call({
			method: "get_current",
			doc: frm.doc,
			callback: function (r) {
				frm.refresh_field("current_value");
			},
		});
	},

	update: function (frm) {
		frappe.call({
			method: "update_series",
			doc: frm.doc,
			freeze: true,
			freeze_msg: __("Updating naming series options"),
			callback: function (r) {
				frm.trigger("setup_transaction_autocomplete");
				frm.trigger("transaction_type");
			},
		});
	},

	try_naming_series(frm) {
		frappe.call({
			method: "preview_series",
			doc: frm.doc,
			callback: function (r) {
				if (!r.exc) {
					frm.set_value("series_preview", r.message);
				} else {
					frm.set_value("series_preview", __("Failed to generate preview of series"));
				}
			},
		});
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
