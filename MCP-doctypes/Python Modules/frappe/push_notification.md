# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/push_notification.py`

## Classes

### `PushNotification`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, project_name` | `` | :param project_name: (str) The name of the project. |
| `add_token` | `self, user_id, token` | `` | Add a token for a user.

:param user_id: (str) The ID of the user. This should be user's unique identifier.
:param token: (str) The token to be added.
:return: tuple[bool, str] First element is the success status, second element is the message. |
| `remove_token` | `self, user_id, token` | `` | Remove a token for a user.

:param user_id: (str) The ID of the user. This should be user's unique identifier.
:param token: (str) The token to be removed.
:return: tuple[bool, str] First element is the success status, second element is the message. |
| `add_topic` | `self, topic_name` | `` | Add a notification topic.

:param topic_name: (str) The name of the topic.
:return: bool True if successful, False otherwise. |
| `remove_topic` | `self, topic_name` | `` | Remove a notification topic.

:param topic_name: (str) The name of the topic.
:return: bool True if successful, False otherwise. |
| `subscribe_topic` | `self, user_id, topic_name` | `` | Subscribe a user to a topic.

:param user_id: (str) The ID of the user. This should be user's unique identifier.
:param topic_name: (str) The name of the topic. This topic should be already created.
:return: bool True if successful, False otherwise. |
| `unsubscribe_topic` | `self, user_id, topic_name` | `` | Unsubscribe a user from a topic.

:param user_id: (str) The ID of the user. This should be user's unique identifier.
:param topic_name: (str) The name of the topic. This topic should be already created.
:return: bool True if successful, False otherwise. |
| `send_notification_to_user` | `self, user_id, title, body, link, icon, data, truncate_body, strip_html` | `` | Send notification to a user.

:param user_id: (str) The ID of the user. This should be user's unique identifier.
:param title: (str) The title of the notification.
:param body: (str) The body of the notification. At max 1000 characters.
:param link: (str) The link to be opened when the notification is clicked.
:param icon: (str) The icon to be shown in the notification.
:param data: (dict) The data to be sent with the notification. This can be used to provide extra information while dealing with in-app notifications.
:param truncate_body: (bool) Whether to truncate the body or not. If True, the body will be truncated to 1000 characters.
:param strip_html: (bool) Whether to strip HTML tags from the body or not.
:return: bool True if the request queued successfully, False otherwise. |
| `send_notification_to_topic` | `self, topic_name, title, body, link, icon, data, truncate_body, strip_html` | `` | Send notification to a notification topic.

:param topic_name: (str) The name of the topic. This topic should be already created.
:param title: (str) The title of the notification.
:param body: (str) The body of the notification. At max 1000 characters.
:param link: (str) The link to be opened when the notification is clicked.
:param icon: (str) The icon to be shown in the notification.
:param data: (dict) The data to be sent with the notification. This can be used to provide extra information while dealing with in-app notifications.
:param truncate_body: (bool) Whether to truncate the body or not. If True, the body will be truncated to 1000 characters.
:param strip_html: (bool) Whether to strip HTML tags from the body or not.
:return: bool True if the request queued successfully, False otherwise. |
| `is_enabled` | `self` | `` | Check whether the push notification relay is enabled or not.

:return: bool True if enabled, False otherwise. |
| `_get_credential` | `self` | `` | Register & Get the API key and secret from the central relay server.
Also store the API key and secret in the database for future use.

NOTE: This method is private and should not be called directly.

:return: tuple[str, str] The API key and secret. |
| `_send_post_request` | `self, method, params, use_authentication` | `` | Send a POST request to the central relay server.

NOTE: This method is private and should not be called directly.

:param method: (str) The method to be called on the central relay server.
:param params: (dict) The parameters to be sent with the request.
:param use_authentication: (bool) Whether to use authentication or not.
:return: (dict) Response data of the request. |
| `_site_name` | `self` | `property` |  |
| `_site_protocol` | `self` | `property` |  |
| `_site_port` | `self` | `property` |  |





## Functions

### `auth_webhook`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `subscribe`
**Arguments:** `fcm_token, project_name`
**Decorators:** ``

**Docstring:**
```

```
### `unsubscribe`
**Arguments:** `fcm_token, project_name`
**Decorators:** ``

**Docstring:**
```

```

