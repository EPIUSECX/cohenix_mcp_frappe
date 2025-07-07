# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/exceptions.py`

## Classes

### `SiteNotSpecifiedError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |


### `DatabaseModificationError`
**Inherits:** `Exception`


**Docstring:**
```
Error raised when attempting to modify the database in a read-only document context.
```

**Methods:**
No methods found.

### `UrlSchemeNotSupported`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ValidationError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FrappeTypeError`
**Inherits:** `TypeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AuthenticationError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SessionExpired`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PermissionError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DoesNotExistError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |


### `PageDoesNotExistError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NameError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OutgoingEmailError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SessionStopped`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UnsupportedMediaType`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `RequestToken`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Redirect`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, http_status_code` | `` |  |


### `CSRFTokenError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `TooManyRequestsError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ImproperDBConfigurationError`
**Inherits:** `Exception`


**Docstring:**
```
Used when frappe detects that database or tables are not properly
configured
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, reason, msg` | `` |  |


### `DuplicateEntryError`
**Inherits:** `NameError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DataError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UnknownDomainError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `MappingMismatchError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidStatusError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `MandatoryError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NonNegativeError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidSignatureError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `RateLimitExceededError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CannotChangeConstantError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CharacterLengthExceededError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UpdateAfterSubmitError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LinkValidationError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CancelledLinkError`
**Inherits:** `LinkValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocstatusTransitionError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `TimestampMismatchError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmptyTableError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LinkExistsError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidEmailAddressError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidNameError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidPhoneNumberError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `TemplateNotFoundError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UniqueValidationError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AppNotInstalledError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `IncorrectSitePath`
**Inherits:** `NotFound`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ImplicitCommitError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `RetryBackgroundJobError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocumentLockedError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CircularLinkingError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SecurityException`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidColumnName`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `IncompatibleApp`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidDates`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DataTooLongException`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FileAlreadyAttachedException`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocumentAlreadyRestored`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AttachmentLimitReached`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QueryTimeoutError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QueryDeadlockError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InReadOnlyMode`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SessionBootFailed`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QueueOverloaded`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PrintFormatError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `TooManyWritesError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidAuthorizationHeader`
**Inherits:** `CSRFTokenError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidAuthorizationPrefix`
**Inherits:** `CSRFTokenError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidAuthorizationToken`
**Inherits:** `CSRFTokenError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidDatabaseFile`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ExecutableNotFound`
**Inherits:** `FileNotFoundError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidRoundingMethod`
**Inherits:** `FileNotFoundError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidRemoteException`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LinkExpired`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CommandFailedError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, message, out, err` | `` |  |





## Functions

No top-level functions found in this file.
