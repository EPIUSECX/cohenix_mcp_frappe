# Master Control Plan: `User`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Represents a User in the system.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Desk User | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `user_details_tab` | User Details | Tab Break | None |  |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  | ✅ | 1 | None |
| `section_break_3` | Basic Info | Section Break | None |  |  |  | None | None |
| `email` | Email | Data | Email | ✅ |  |  | None | None |
| `first_name` | First Name | Data | None | ✅ |  |  | None | None |
| `middle_name` | Middle Name | Data | None |  |  |  | None | None |
| `last_name` | Last Name | Data | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `full_name` | Full Name | Data | None |  |  | ✅ | None | None |
| `username` | Username | Data | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `language` | Language | Link | Language |  |  |  | None | None |
| `time_zone` | Time Zone | Autocomplete | None |  |  |  | None | None |
| `send_welcome_email` | Send Welcome Email | Check | None |  |  |  | 1 | None |
| `unsubscribed` | Unsubscribed | Check | None |  | ✅ |  | 0 | None |
| `user_image` | User Image | Attach Image | None |  | ✅ |  | None | Get your globally recognized avatar from Gravatar.com |
| `roles_permissions_tab` | Roles & Permissions | Tab Break | None |  |  |  | None | None |
| `sb1` | Roles | Section Break | None |  |  | ✅ | None | None |
| `role_profile_name` | Role Profile | Link | Role Profile |  | ✅ |  | None | None |
| `role_profiles` | Role Profiles | Table MultiSelect | User Role Profile |  |  |  | None | None |
| `roles_html` | Roles HTML | HTML | None |  |  | ✅ | None | None |
| `roles` | Roles Assigned | Table | Has Role |  | ✅ | ✅ | None | None |
| `sb_allow_modules` | Allow Modules | Section Break | None |  |  |  | None | None |
| `module_profile` | Module Profile | Link | Module Profile |  |  |  | None | None |
| `modules_html` | Modules HTML | HTML | None |  |  |  | None | None |
| `block_modules` | Block Modules | Table | Block Module |  | ✅ |  | None | None |
| `home_settings` | Home Settings | Code | None |  | ✅ |  | None | None |
| `short_bio` | More Information | Tab Break | None |  |  |  | None | None |
| `gender` | Gender | Link | Gender |  |  |  | None | None |
| `birth_date` | Birth Date | Date | None |  |  |  | None | None |
| `interest` | Interests | Small Text | None |  |  |  | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `phone` | Phone | Data | Phone |  |  |  | None | None |
| `location` | Location | Data | None |  |  |  | None | None |
| `bio` | Bio | Small Text | None |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `mobile_no` | Mobile No | Data | Phone |  |  |  | None | None |
| `settings_tab` | Settings | Tab Break | None |  |  |  | None | None |
| `desk_settings_section` | Desk Settings | Section Break | None |  |  |  | None | None |
| `mute_sounds` | Mute Sounds | Check | None |  |  |  | 0 | None |
| `desk_theme` | Desk Theme | Select | Light
Dark
Automatic |  |  |  | None | None |
| `code_editor_type` | Code Editor Type | Select | vscode
vim
emacs |  |  |  | vscode | None |
| `banner_image` | Banner Image | Attach Image | None |  |  |  | None | None |
| `navigation_settings_section` | Navigation Settings | Section Break | None |  |  |  | None | None |
| `search_bar` | Search Bar | Check | None |  |  |  | 1 | None |
| `notifications` | Notifications | Check | None |  |  |  | 1 | None |
| `list_settings_section` | List Settings | Section Break | None |  |  |  | None | None |
| `list_sidebar` | Sidebar | Check | None |  |  |  | 1 | None |
| `bulk_actions` | Bulk Actions | Check | None |  |  |  | 1 | None |
| `view_switcher` | View Switcher | Check | None |  |  |  | 1 | None |
| `form_settings_section` | Form Settings | Section Break | None |  |  |  | None | None |
| `form_sidebar` | Sidebar | Check | None |  |  |  | 1 | None |
| `timeline` | Timeline | Check | None |  |  |  | 1 | None |
| `dashboard` | Dashboard | Check | None |  |  |  | 1 | None |
| `show_absolute_datetime_in_timeline` | Show Absolute Datetime in Timeline | Check | None |  |  |  | 0 | None |
| `change_password` | Change Password | Section Break | None |  |  |  | None | None |
| `new_password` | Set New Password | Password | None |  |  |  | None | None |
| `logout_all_sessions` | Logout From All Devices After Changing Password | Check | None |  |  |  | 1 | None |
| `reset_password_key` | Reset Password Key | Data | None |  | ✅ | ✅ | None | None |
| `last_reset_password_key_generated_on` | Last Reset Password Key Generated On | Datetime | None |  | ✅ | ✅ | None | Stores the datetime when the last reset password key was generated. |
| `last_password_reset_date` | Last Password Reset Date | Date | None |  | ✅ | ✅ | None | None |
| `redirect_url` | Redirect URL | Small Text | None |  | ✅ |  | None | None |
| `document_follow_notifications_section` | Document Follow | Section Break | None |  |  |  | None | None |
| `document_follow_notify` | Send Notifications For Documents Followed By Me | Check | None |  |  |  | 0 | None |
| `document_follow_frequency` | Frequency | Select | Hourly
Daily
Weekly |  |  |  | Daily | None |
| `column_break_75` | None | Column Break | None |  |  |  | None | None |
| `follow_created_documents` | Auto follow documents that you create | Check | None |  |  |  | 0 | None |
| `follow_commented_documents` | Auto follow documents that you comment on | Check | None |  |  |  | 0 | None |
| `follow_liked_documents` | Auto follow documents that you Like | Check | None |  |  |  | 0 | None |
| `follow_assigned_documents` | Auto follow documents that are assigned to you | Check | None |  |  |  | 0 | None |
| `follow_shared_documents` | Auto follow documents that are shared with you | Check | None |  |  |  | 0 | None |
| `email_settings` | Email | Section Break | None |  |  |  | None | None |
| `email_signature` | Email Signature | Text Editor | None |  |  |  | None | None |
| `thread_notify` | Send Notifications For Email Threads | Check | None |  |  |  | 1 | None |
| `send_me_a_copy` | Send Me A Copy of Outgoing Emails | Check | None |  |  |  | 0 | None |
| `allowed_in_mentions` | Allowed In Mentions | Check | None |  |  |  | 1 | None |
| `user_emails` | User Emails | Table | User Email |  |  |  | None | None |
| `workspace_section` | Workspace | Section Break | None |  |  |  | None | None |
| `default_workspace` | Default Workspace | Link | Workspace |  |  |  | None | If left empty, the default workspace will be the last visited workspace |
| `app_section` | App | Section Break | None |  |  |  | None | None |
| `default_app` | Default App | Select | None |  |  |  | None | Redirect to the selected app after login |
| `sb2` | Defaults | Section Break | None |  | ✅ | ✅ | None | These values will be automatically updated in transactions and also will be useful to restrict permissions for this user on transactions containing these values. |
| `defaults` | User Defaults | Table | DefaultValue |  | ✅ |  | None | Enter default value fields (keys) and values. If you add multiple values for a field, the first one will be picked. These defaults are also used to set "match" permission rules. To see list of fields, go to "Customize Form". |
| `sb3` | Security Settings | Section Break | None |  |  | ✅ | None | None |
| `simultaneous_sessions` | Simultaneous Sessions | Int | None |  |  |  | 2 | None |
| `restrict_ip` | Restrict IP | Small Text | None |  |  |  | None | Restrict user from this IP address only. Multiple IP addresses can be added by separating with commas. Also accepts partial IP addresses like (111.111.111) |
| `last_ip` | Last IP | Read Only | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `login_after` | Login After | Int | None |  |  |  | None | Allow user to login only after this hour (0-24) |
| `user_type` | User Type | Link | User Type |  |  |  | System User | If the user has any role checked, then the user becomes a "System User". "System User" has access to the desktop |
| `last_active` | Last Active | Datetime | None |  |  | ✅ | None | None |
| `section_break_63` | None | Column Break | None |  |  |  | None | None |
| `login_before` | Login Before | Int | None |  |  |  | None | Allow user to login only before this hour (0-24) |
| `bypass_restrict_ip_check_if_2fa_enabled` | Bypass Restricted IP Address Check If Two Factor Auth Enabled | Check | None |  |  |  | 0 | If enabled,  user can login from any IP Address using Two Factor Auth, this can also be set for all users in System Settings |
| `last_login` | Last Login | Read Only | None |  |  | ✅ | None | None |
| `last_known_versions` | Last Known Versions | Text | None |  | ✅ | ✅ | None | Stores the JSON of last known versions of various installed apps. It is used to show release notes. |
| `third_party_authentication` | Third Party Authentication | Section Break | None |  |  |  | None | None |
| `social_logins` | Social Logins | Table | User Social Login |  |  |  | None | None |
| `api_access` | API Access | Section Break | None |  |  |  | None | None |
| `api_key` | API Key | Data | None |  |  | ✅ | None | API Key cannot be regenerated |
| `generate_keys` | Generate Keys | Button | None |  |  |  | None | None |
| `column_break_65` | None | Column Break | None |  |  |  | None | None |
| `api_secret` | API Secret | Password | None |  |  | ✅ | None | None |
| `onboarding_status` | Onboarding Status | Small Text | None |  | ✅ |  | {} | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 6

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user/user.js`
```javascript
frappe.ui.form.on("User", {
	setup: function (frm) {
		frm.set_query("default_workspace", () => {
			return {
				filters: {
					for_user: ["in", [null, frappe.session.user]],
					title: ["!=", "Welcome Workspace"],
				},
			};
		});
	},
	before_load: function (frm) {
		let update_tz_options = function () {
			frm.fields_dict.time_zone.set_data(frappe.all_timezones);
		};

		if (!frappe.all_timezones) {
			frappe.call({
				method: "frappe.core.doctype.user.user.get_timezones",
				callback: function (r) {
					frappe.all_timezones = r.message.timezones;
					update_tz_options();
				},
			});
		} else {
			update_tz_options();
		}
	},

	time_zone: function (frm) {
		if (frm.doc.time_zone && frm.doc.time_zone.startsWith("Etc")) {
			frm.set_df_property(
				"time_zone",
				"description",
				__("Note: Etc timezones have their signs reversed.")
			);
		}
	},

	role_profiles: function (frm) {
		if (frm.doc.role_profiles && frm.doc.role_profiles.length) {
			frm.roles_editor.disable = 1;
			frm.call("populate_role_profile_roles").then(() => {
				frm.roles_editor.show();
			});
		} else {
			frm.roles_editor.disable = 0;
			frm.roles_editor.show();
		}
	},

	module_profile: function (frm) {
		if (frm.doc.module_profile) {
			frappe.call({
				method: "frappe.core.doctype.user.user.get_module_profile",
				args: {
					module_profile: frm.doc.module_profile,
				},
				callback: function (data) {
					frm.set_value("block_modules", []);
					$.each(data.message || [], function (i, v) {
						let d = frm.add_child("block_modules");
						d.module = v.module;
					});
					frm.module_editor && frm.module_editor.show();
				},
			});
		}
	},

	onload: function (frm) {
		frm.can_edit_roles = has_access_to_edit_user();

		if (frm.is_new() && frm.roles_editor) {
			frm.roles_editor.reset();
		}

		if (
			frm.can_edit_roles &&
			!frm.is_new() &&
			["System User", "Website User"].includes(frm.doc.user_type)
		) {
			if (!frm.roles_editor) {
				const role_area = $('<div class="role-editor">').appendTo(
					frm.fields_dict.roles_html.wrapper
				);

				frm.roles_editor = new frappe.RoleEditor(
					role_area,
					frm,
					frm.doc.role_profiles && frm.doc.role_profiles.length ? 1 : 0
				);

				if (frm.doc.user_type == "System User") {
					var module_area = $("<div>").appendTo(frm.fields_dict.modules_html.wrapper);
					frm.module_editor = new frappe.ModuleEditor(frm, module_area);
				}
			} else {
				frm.roles_editor.show();
			}
		}
	},
	refresh: function (frm) {
		let doc = frm.doc;

		frappe.xcall("frappe.apps.get_apps").then((r) => {
			let apps = r?.map((r) => r.name) || [];
			frm.set_df_property("default_app", "options", [" ", ...apps]);
		});

		if (frm.is_new()) {
			frm.set_value("time_zone", frappe.sys_defaults.time_zone);
		}

		if (
			["System User", "Website User"].includes(frm.doc.user_type) &&
			!frm.is_new() &&
			!frm.roles_editor &&
			frm.can_edit_roles
		) {
			frm.reload_doc();
			return;
		}

		frm.toggle_display(["sb1", "sb3", "modules_access"], false);
		frm.trigger("setup_impersonation");

		if (!frm.is_new()) {
			if (has_access_to_edit_user()) {
				frm.add_custom_button(
					__("Set User Permissions"),
					function () {
						frappe.route_options = {
							user: doc.name,
						};
						frappe.set_route("List", "User Permission");
					},
					__("Permissions")
				);

				frm.add_custom_button(
					__("View Permitted Documents"),
					() =>
						frappe.set_route("query-report", "Permitted Documents For User", {
							user: frm.doc.name,
						}),
					__("Permissions")
				);

				frm.add_custom_button(
					__("View Doctype Permissions"),
					() =>
						frappe.set_route("query-report", "User Doctype Permissions", {
							user: frm.doc.name,
						}),
					__("Permissions")
				);

				frm.toggle_display(["sb1", "sb3", "modules_access"], true);
			}

			frm.add_custom_button(
				__("Reset Password"),
				function () {
					frappe.call({
						method: "frappe.core.doctype.user.user.reset_password",
						args: {
							user: frm.doc.name,
						},
					});
				},
				__("Password")
			);

			if (frappe.user.has_role("System Manager")) {
				frappe.db.get_single_value("LDAP Settings", "enabled").then((value) => {
					if (value === 1 && frm.doc.name != "Administrator") {
						frm.add_custom_button(
							__("Reset LDAP Password"),
							function () {
								const d = new frappe.ui.Dialog({
									title: __("Reset LDAP Password"),
									fields: [
										{
											label: __("New Password"),
											fieldtype: "Password",
											fieldname: "new_password",
											reqd: 1,
										},
										{
											label: __("Confirm New Password"),
											fieldtype: "Password",
											fieldname: "confirm_password",
											reqd: 1,
										},
										{
											label: __("Logout All Sessions"),
											fieldtype: "Check",
											fieldname: "logout_sessions",
										},
									],
									primary_action: (values) => {
										d.hide();
										if (values.new_password !== values.confirm_password) {
											frappe.throw(__("Passwords do not match!"));
										}
										frappe.call(
											"frappe.integrations.doctype.ldap_settings.ldap_settings.reset_password",
											{
												user: frm.doc.email,
												password: values.new_password,
												logout: values.logout_sessions,
											}
										);
									},
								});
								d.show();
							},
							__("Password")
						);
					}
				});
			}

			if (
				cint(frappe.boot.sysdefaults.enable_two_factor_auth) &&
				(frappe.session.user == doc.name || frappe.user.has_role("System Manager"))
			) {
				frm.add_custom_button(
					__("Reset OTP Secret"),
					function () {
						frappe.call({
							method: "frappe.twofactor.reset_otp_secret",
							args: {
								user: frm.doc.name,
							},
						});
					},
					__("Password")
				);
			}

			frm.trigger("enabled");

			if (frm.roles_editor && frm.can_edit_roles) {
				frm.roles_editor.disable =
					frm.doc.role_profiles && frm.doc.role_profiles.length ? 1 : 0;
				frm.roles_editor.show();
			}

			frm.module_editor && frm.module_editor.show();

			if (frappe.session.user == doc.name) {
				// update display settings
				if (doc.user_image) {
					frappe.boot.user_info[frappe.session.user].image = frappe.utils.get_file_link(
						doc.user_image
					);
				}
			}
		}
		if (frm.doc.user_emails && frappe.model.can_create("Email Account")) {
			var found = 0;
			for (var i = 0; i < frm.doc.user_emails.length; i++) {
				if (frm.doc.email == frm.doc.user_emails[i].email_id) {
					found = 1;
				}
			}
			if (!found) {
				frm.add_custom_button(__("Create User Email"), function () {
					if (!frm.doc.email) {
						frappe.msgprint(__("Email is mandatory to create User Email"));
						return;
					}
					frm.events.create_user_email(frm);
				});
			}
		}

		if (frappe.route_flags.unsaved === 1) {
			delete frappe.route_flags.unsaved;
			for (let i = 0; i < frm.doc.user_emails.length; i++) {
				frm.doc.user_emails[i].idx = frm.doc.user_emails[i].idx + 1;
			}
			frm.dirty();
		}
		frm.trigger("time_zone");
	},
	validate: function (frm) {
		if (frm.roles_editor) {
			frm.roles_editor.set_roles_in_table();
		}
	},
	enabled: function (frm) {
		var doc = frm.doc;
		if (!frm.is_new() && has_access_to_edit_user()) {
			frm.toggle_display(["sb1", "sb3", "modules_access"], doc.enabled);
			frm.set_df_property("enabled", "read_only", 0);
		}

		if (frm.doc.name !== "Administrator") {
			frm.toggle_enable("email", frm.is_new());
		}
	},
	create_user_email: function (frm) {
		frappe.call({
			method: "frappe.core.doctype.user.user.has_email_account",
			args: {
				email: frm.doc.email,
			},
			callback: function (r) {
				if (!Array.isArray(r.message) || !r.message.length) {
					frappe.route_options = {
						email_id: frm.doc.email,
						awaiting_password: 1,
						enable_incoming: 1,
					};
					frappe.model.with_doctype("Email Account", function (doc) {
						doc = frappe.model.get_new_doc("Email Account");
						frappe.route_flags.linked_user = frm.doc.name;
						frappe.route_flags.delete_user_from_locals = true;
						frappe.set_route("Form", "Email Account", doc.name);
					});
				} else {
					frappe.route_flags.create_user_account = frm.doc.name;
					frappe.set_route("Form", "Email Account", r.message[0]["name"]);
				}
			},
		});
	},
	generate_keys: function (frm) {
		frappe.call({
			method: "frappe.core.doctype.user.user.generate_keys",
			args: {
				user: frm.doc.name,
			},
			callback: function (r) {
				if (r.message) {
					frappe.msgprint(__("Save API Secret: {0}", [r.message.api_secret]));
					frm.reload_doc();
				}
			},
		});
	},
	after_save: function (frm) {
		/**
		 * Checks whether the effective value has changed.
		 *
		 * @param {Array.<string>} - Tuple with new override, previous override,
		 *   and optionally fallback.
		 * @returns {boolean} - Whether the resulting value has effectively changed
		 */
		const has_effectively_changed = ([new_override, prev_override, fallback = undefined]) => {
			const prev_effective = prev_override || fallback;
			const new_effective = new_override || fallback;
			return new_override !== undefined && prev_effective !== new_effective;
		};

		const doc = frm.doc;
		const boot = frappe.boot;
		const attr_tuples = [
			[doc.language, boot.user.language, boot.sysdefaults.language],
			[doc.time_zone, boot.time_zone.user, boot.time_zone.system],
			[doc.desk_theme, boot.user.desk_theme], // No system default.
		];

		if (doc.name === frappe.session.user && attr_tuples.some(has_effectively_changed)) {
			frappe.msgprint(__("Refreshing..."));
			window.location.reload();
		}
	},
	setup_impersonation: function (frm) {
		if (
			frappe.session.user === "Administrator" &&
			frm.doc.name != "Administrator" &&
			!frm.is_new()
		) {
			frm.add_custom_button(__("Impersonate"), () => {
				if (frm.doc.restrict_ip) {
					frappe.msgprint({
						message:
							"There's IP restriction for this user, you can not impersonate as this user.",
						title: "IP restriction is enabled",
					});
					return;
				}
				frappe.prompt(
					[
						{
							fieldname: "reason",
							fieldtype: "Small Text",
							label: "Reason for impersonating",
							description: __("Note: This will be shared with user."),
							reqd: 1,
						},
					],
					(values) => {
						frappe
							.xcall("frappe.core.doctype.user.user.impersonate", {
								user: frm.doc.name,
								reason: values.reason,
							})
							.then(() => window.location.reload());
					},
					__("Impersonate as {0}", [frm.doc.name]),
					__("Confirm")
				);
			});
		}
	},
});

frappe.ui.form.on("User Email", {
	email_account(frm, cdt, cdn) {
		let child_row = locals[cdt][cdn];
		frappe.model.get_value(
			"Email Account",
			child_row.email_account,
			"auth_method",
			(value) => {
				child_row.used_oauth = value.auth_method === "OAuth";
				frm.refresh_field("user_emails", cdn, "used_oauth");
			}
		);
	},
});

function has_access_to_edit_user() {
	return has_common(frappe.user_roles, get_roles_for_editing_user());
}

function get_roles_for_editing_user() {
	return (
		frappe
			.get_meta("User")
			.permissions.filter((perm) => perm.permlevel >= 1 && perm.write)
			.map((perm) => perm.role) || ["System Manager"]
	);
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `User Doctype Permissions` | Script Report | Core |
| `Permitted Documents For User` | Script Report | Core |



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
