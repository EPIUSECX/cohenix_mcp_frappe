# Master Control Plan: `Currency Exchange Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `api_details_section` | API Details | Section Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `service_provider` | Service Provider | Select | frankfurter.app
exchangerate.host
Custom | ✅ |  |  | None | None |
| `api_endpoint` | API Endpoint | Data | None | ✅ |  |  | None | None |
| `use_http` | Use HTTP Protocol | Check | None |  |  |  | 0 | None |
| `access_key` | Access Key | Data | None |  |  |  | None | None |
| `url` | Example URL | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `help` | Help | HTML | <h3>Currency Exchange Settings Help</h3>
<p>There are 3 variables that could be used within the endpoint, result key and in values of the parameter.</p>
<p>Exchange rate between {from_currency} and {to_currency} on {transaction_date} is fetched by the API.</p>
<p>Example: If your endpoint is exchange.com/2021-08-01, then, you will have to input exchange.com/{transaction_date}</p> |  |  |  | None | None |
| `section_break_2` | Request Parameters | Section Break | None |  |  |  | None | None |
| `req_params` | Parameters | Table | Currency Exchange Settings Details | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `result_key` | Result Key | Table | Currency Exchange Settings Result | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/currency_exchange_settings/currency_exchange_settings.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Currency Exchange Settings", {
	service_provider: function (frm) {
		frm.call({
			method: "erpnext.accounts.doctype.currency_exchange_settings.currency_exchange_settings.get_api_endpoint",
			args: {
				service_provider: frm.doc.service_provider,
				use_http: frm.doc.use_http,
			},
			callback: function (r) {
				if (r && r.message) {
					if (frm.doc.service_provider == "exchangerate.host") {
						let result = ["result"];
						let params = {
							date: "{transaction_date}",
							from: "{from_currency}",
							to: "{to_currency}",
						};
						add_param(frm, r.message, params, result);
					} else if (frm.doc.service_provider == "frankfurter.app") {
						let result = ["rates", "{to_currency}"];
						let params = {
							base: "{from_currency}",
							symbols: "{to_currency}",
						};
						add_param(frm, r.message, params, result);
					}
				}
			},
		});
	},
	use_http: function (frm) {
		frm.trigger("service_provider");
	},
});

function add_param(frm, api, params, result) {
	var row;
	frm.clear_table("req_params");
	frm.clear_table("result_key");

	frm.doc.api_endpoint = api;

	$.each(params, function (key, value) {
		row = frm.add_child("req_params");
		row.key = key;
		row.value = value;
	});

	$.each(result, function (key, value) {
		row = frm.add_child("result_key");
		row.key = value;
	});

	frm.refresh_fields();
}

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
