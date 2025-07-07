# Master Control Plan: `System Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
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
| `localization` | None | Section Break | None |  |  |  | None | None |
| `app_name` | Application Name | Data | None |  | ✅ |  | Frappe | The application name will be used in the Login page. |
| `country` | Country | Link | Country |  |  |  | None | None |
| `language` | Language | Link | Language | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `time_zone` | Time Zone | Select | None | ✅ |  | ✅ | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | Default display currency |
| `enable_onboarding` | Enable Onboarding | Check | None |  |  |  | 0 | None |
| `setup_complete` | Setup Complete | Check | None |  | ✅ | ✅ | 0 | None |
| `disable_document_sharing` | Disable Document Sharing | Check | None |  |  |  | 0 | None |
| `date_and_number_format` | Date and Number Format | Section Break | None |  |  |  | None | None |
| `date_format` | Date Format | Select | yyyy-mm-dd
dd-mm-yyyy
dd/mm/yyyy
dd.mm.yyyy
mm/dd/yyyy
mm-dd-yyyy | ✅ |  |  | None | None |
| `time_format` | Time Format | Select | HH:mm:ss
HH:mm | ✅ |  |  | HH:mm:ss | None |
| `number_format` | Number Format | Select | #,###.##
#.###,##
# ###.##
# ###,##
#'###.##
#, ###.##
#,##,###.##
#,###.###
#.###
#,### | ✅ |  |  | None | None |
| `use_number_format_from_currency` | Use Number Format from Currency | Check | None |  |  |  | 0 | None |
| `first_day_of_the_week` | First Day of the Week | Select | Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday |  |  |  | Sunday | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `float_precision` | Float Precision | Select | 
2
3
4
5
6
7
8
9 |  |  |  | None | None |
| `currency_precision` | Currency Precision | Select | 
0
1
2
3
4
5
6
7
8
9 |  |  |  | None | If not set, the currency precision will depend on number format |
| `rounding_method` | Rounding Method | Select | Banker's Rounding (legacy)
Banker's Rounding
Commercial Rounding |  |  |  | Banker's Rounding (legacy) | None |
| `show_absolute_datetime_in_timeline` | Show Absolute Datetime in Timeline | Check | None |  |  |  | 0 | None |
| `permissions` | Permissions | Section Break | None |  |  |  | None | None |
| `apply_strict_user_permissions` | Apply Strict User Permissions | Check | None |  |  |  | 0 | If Apply Strict User Permission is checked and User Permission is defined for a DocType for a User, then all the documents where value of the link is blank, will not be shown to that User |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `allow_older_web_view_links` | Allow Older Web View Links (Insecure) | Check | None |  |  |  | 0 | None |
| `security_tab` | Login | Tab Break | None |  |  |  | None | None |
| `security` | None | Section Break | None |  |  |  | None | None |
| `session_expiry` | Session Expiry (idle timeout) | Data | None |  |  |  | 170:00 | Example: Setting this to 24:00 will log out a user if they are not active for 24:00 hours. |
| `document_share_key_expiry` | Document Share Key Expiry (in Days) | Int | None |  |  |  | 30 | Number of days after which the document Web View link shared on email will be expired |
| `column_break_txqh` | None | Column Break | None |  |  |  | None | None |
| `deny_multiple_sessions` | Allow only one session per user | Check | None |  |  |  | 0 | Note: Multiple sessions will be allowed in case of mobile device |
| `disable_user_pass_login` | Disable Username/Password Login | Check | None |  |  |  | 0 | Make sure to configure a Social Login Key before disabling to prevent lockout |
| `login_methods_section` | Login Methods | Section Break | None |  |  |  | None | None |
| `allow_login_using_mobile_number` | Allow Login using Mobile Number | Check | None |  |  |  | 0 | User can login using Email id or Mobile number |
| `allow_login_using_user_name` | Allow Login using User Name | Check | None |  |  |  | 0 | User can login using Email id or User Name |
| `column_break_uhqk` | None | Column Break | None |  |  |  | None | None |
| `login_with_email_link` | Login with email link | Check | None |  |  |  | 1 | Allow users to log in without a password, using a login link sent to their email |
| `login_with_email_link_expiry` | Login with email link expiry (in minutes) | Int | None |  |  |  | 10 | None |
| `rate_limit_email_link_login` | Rate limit for email link login | Int | None |  |  |  | None | You can set a high value here if multiple users will be logging in from the same network. |
| `brute_force_security` | Brute Force Security | Section Break | None |  |  |  | None | None |
| `allow_consecutive_login_attempts` | Allow Consecutive Login Attempts  | Int | None |  |  |  | 10 | None |
| `column_break_34` | None | Column Break | None |  |  |  | None | None |
| `allow_login_after_fail` | Allow Login After Fail | Int | None |  |  |  | 60 | In seconds |
| `two_factor_authentication` | Two Factor Authentication | Section Break | None |  |  |  | None | None |
| `enable_two_factor_auth` | Enable Two Factor Auth | Check | None |  |  |  | 0 | None |
| `bypass_2fa_for_retricted_ip_users` | Bypass Two Factor Auth for users who login from restricted IP Address | Check | None |  |  |  | 0 | If enabled, users who login from Restricted IP Address, won't be prompted for Two Factor Auth |
| `bypass_restrict_ip_check_if_2fa_enabled` | Bypass restricted IP Address check If Two Factor Auth Enabled | Check | None |  |  |  | 0 | If enabled, all users can login from any IP Address using Two Factor Auth. This can also be set only for specific user(s) in User Page |
| `two_factor_method` | Two Factor Authentication method | Select | OTP App
SMS
Email |  |  |  | OTP App | Choose authentication method to be used by all users |
| `lifespan_qrcode_image` | Expiry time of QR Code Image Page | Int | None |  |  |  | None | Time in seconds to retain QR code image on server. Min:<strong>240</strong> |
| `otp_issuer_name` | OTP Issuer Name | Data | None |  |  |  | Frappe Framework | None |
| `password_tab` | Password | Tab Break | None |  |  |  | None | None |
| `password_settings` | Password | Section Break | None |  |  |  | None | None |
| `logout_on_password_reset` | Logout All Sessions on Password Reset | Check | None |  |  |  | 1 | None |
| `force_user_to_reset_password` | Force User to Reset Password | Int | None |  |  |  | None | In Days |
| `reset_password_link_expiry_duration` | Reset Password Link Expiry Duration | Duration | None |  |  |  | 1200 | None |
| `password_reset_limit` | Password Reset Link Generation Limit | Int | None |  |  |  | 3 | Hourly rate limit for generating password reset links |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `enable_password_policy` | Enable Password Policy | Check | None |  |  |  | 1 | If enabled, the password strength will be enforced based on the Minimum Password Score value. A value of 1 being very weak and 4 being very strong. |
| `minimum_password_score` | Minimum Password Score | Select | 1
2
3
4 |  |  |  | 2 | None |
| `email_tab` | Email | Tab Break | None |  |  |  | None | None |
| `email` | None | Section Break | None |  |  |  | None | None |
| `email_footer_address` | Email Footer Address | Small Text | None |  |  |  | None | Your organization name and address for the email footer. |
| `email_retry_limit` | Email Retry Limit | Int | None |  |  |  | 3 | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `disable_standard_email_footer` | Disable Standard Email Footer | Check | None |  |  |  | 0 | None |
| `hide_footer_in_auto_email_reports` | Hide footer in auto email reports | Check | None |  |  |  | 0 | None |
| `attach_view_link` | Include Web View Link in Email | Check | None |  |  |  | 1 | None |
| `store_attached_pdf_document` | Store Attached PDF Document | Check | None |  |  |  | 1 | When sending document using email, store the PDF on Communication. Warning: This can increase your storage usage. |
| `welcome_email_template` | Welcome Email Template | Link | Email Template |  |  |  | None | None |
| `reset_password_template` | Reset Password Template | Link | Email Template |  |  |  | None | None |
| `files_tab` | Files | Tab Break | None |  |  |  | None | None |
| `files_section` | None | Section Break | None |  |  |  | None | None |
| `max_file_size` | Max File Size (MB) | Int | None |  |  |  | None | None |
| `allow_guests_to_upload_files` | Allow Guests to Upload Files | Check | None |  |  |  | 0 | When enabled this will allow guests to upload files to your application, You can enable this if you wish to collect files from user without having them to log in, for example in job applications web form. |
| `force_web_capture_mode_for_uploads` | Force Web Capture Mode for Uploads | Check | None |  |  |  | 0 | When uploading files, force the use of the web-based image capture. If this is unchecked, the default behavior is to use the mobile native camera when use from a mobile is detected. |
| `strip_exif_metadata_from_uploaded_images` | Strip EXIF tags from uploaded images | Check | None |  |  |  | 1 | None |
| `column_break_uqma` | None | Column Break | None |  |  |  | None | None |
| `allowed_file_extensions` | Allowed File Extensions | Small Text | None |  |  |  | None | Provide a list of allowed file extensions for file uploads. Each line should contain one allowed file type. If unset, all file extensions are allowed. Example: <br>CSV<br>JPG<br>PNG |
| `app_tab` | App | Tab Break | None |  |  |  | None | None |
| `default_app` | Default App | Select | None |  |  |  | None | Redirect to the selected app after login |
| `updates_tab` | Display | Tab Break | None |  |  |  | None | None |
| `system_updates_section` | None | Section Break | None |  |  |  | None | None |
| `disable_system_update_notification` | Disable System Update Notification | Check | None |  |  |  | 0 | None |
| `disable_change_log_notification` | Disable Change Log Notification | Check | None |  |  |  | 0 | None |
| `hide_empty_read_only_fields` | Hide Empty Read-Only Fields | Check | None |  |  |  | 1 | None |
| `backups_tab` | Backups | Tab Break | None |  |  |  | None | None |
| `sec_backup_limit` | None | Section Break | None |  |  |  | None | None |
| `backup_limit` | Number of Backups | Int | None |  |  |  | 3 | Older backups will be automatically deleted |
| `encrypt_backup` | Encrypt Backups | Check | None |  |  |  | 0 | None |
| `advanced_tab` | Advanced | Tab Break | None |  |  |  | None | None |
| `prepared_report_section` | Reports | Section Break | None |  |  |  | None | None |
| `max_auto_email_report_per_user` | Max auto email report per user | Int | None |  |  |  | 20 | None |
| `max_report_rows` | Max Report Rows | Int | None |  |  |  | 100000 | This value specifies the max number of rows that can be rendered in report view.  |
| `background_workers` | Background Workers | Section Break | None |  |  |  | None | None |
| `enable_scheduler` | Enable Scheduled Jobs | Check | None |  | ✅ |  | 0 | Run scheduled jobs only if checked |
| `dormant_days` | Run Jobs only Daily if Inactive For (Days) | Int | None |  |  |  | 4 | Will run scheduled jobs only once a day for inactive sites. Set it to 0 to avoid automatically disabling the scheduler. |
| `telemetry_section` | Telemetry | Section Break | None |  |  |  | None | None |
| `allow_error_traceback` | Show Full Error and Allow Reporting of Issues to the Developer | Check | None |  |  |  | 1 | None |
| `enable_telemetry` | Allow Sending Usage Data for Improving Applications | Check | None |  |  |  | 1 | None |
| `search_section` | Search | Section Break | None |  |  |  | None | None |
| `link_field_results_limit` | Link Field Results Limit | Int | None |  |  |  | 10 | None |
| `api_logging_section` | API Logging | Section Break | None |  |  |  | None | None |
| `log_api_requests` | Log API Requests | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/system_settings/system_settings.js`
```javascript
frappe.ui.form.on("System Settings", {
	refresh: function (frm) {
		frappe.call({
			method: "frappe.core.doctype.system_settings.system_settings.load",
			callback: function (data) {
				frappe.all_timezones = data.message.timezones;
				frm.set_df_property("time_zone", "options", frappe.all_timezones);

				$.each(data.message.defaults, function (key, val) {
					frm.set_value(key, val, null, true);
					frappe.sys_defaults[key] = val;
				});
				if (frm.re_setup_moment) {
					frappe.app.setup_moment();
					delete frm.re_setup_moment;
				}
			},
		});

		frappe.xcall("frappe.apps.get_apps").then((r) => {
			let apps = r?.map((r) => r.name) || [];
			frm.set_df_property("default_app", "options", [" ", ...apps]);
		});

		frm.trigger("set_rounding_method_options");
	},
	enable_password_policy: function (frm) {
		if (frm.doc.enable_password_policy == 0) {
			frm.set_value("minimum_password_score", "");
		} else {
			frm.set_value("minimum_password_score", "2");
		}
	},
	enable_two_factor_auth: function (frm) {
		if (frm.doc.enable_two_factor_auth == 0) {
			frm.set_value("bypass_2fa_for_retricted_ip_users", 0);
			frm.set_value("bypass_restrict_ip_check_if_2fa_enabled", 0);
		}
	},
	after_save: function (frm) {
		/**
		 * Checks whether the effective value has changed.
		 *
		 * @param {Array.<string>} - Tuple with new fallback, previous fallback and
		 *   optionally an override value.
		 * @returns {boolean} - Whether the resulting value has effectively changed
		 */
		const has_effectively_changed = ([new_fallback, prev_fallback, override = undefined]) =>
			!override && prev_fallback !== new_fallback;

		const attr_tuples = [
			[frm.doc.language, frappe.boot.sysdefaults.language, frappe.boot.user.language],
			[frm.doc.rounding_method, frappe.boot.sysdefaults.rounding_method], // no user override.
		];

		if (attr_tuples.some(has_effectively_changed)) {
			frappe.msgprint(__("Refreshing..."));
			window.location.reload();
		}
	},
	first_day_of_the_week(frm) {
		frm.re_setup_moment = true;
	},

	rounding_method: function (frm) {
		if (frm.doc.rounding_method == frappe.boot.sysdefaults.rounding_method) return;
		let msg = __(
			"Changing rounding method on site with data can result in unexpected behaviour."
		);
		msg += "<br>";
		msg += __("Do you still want to proceed?");

		frappe.confirm(
			msg,
			() => {},
			() => {
				frm.set_value("rounding_method", frappe.boot.sysdefaults.rounding_method);
			}
		);
	},

	set_rounding_method_options: function (frm) {
		if (frm.doc.rounding_method != "Banker's Rounding (legacy)") {
			let field = frm.fields_dict.rounding_method;

			field.df.options = field.df.options
				.split("\n")
				.filter((o) => o != "Banker's Rounding (legacy)")
				.join("\n");

			field.refresh();
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
