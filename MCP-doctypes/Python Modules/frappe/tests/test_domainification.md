# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_domainification.py`

## Classes

### `TestDomainification`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `add_active_domain` | `self, domain` | `` | add domain in active domain |
| `remove_from_active_domains` | `self, domain, remove_all` | `` | remove domain from domain settings |
| `new_domain` | `self, domain` | `` |  |
| `new_doctype` | `self, name` | `` |  |
| `test_active_domains` | `self` | `` |  |
| `test_doctype_and_role_domainification` | `self` | `` | test if doctype is hidden if the doctype's restrict to domain is not included
in active domains |
| `test_desktop_icon_for_domainification` | `self` | `` | desktop icon should be hidden if doctype's restrict to domain is not in active domains |
| `test_module_def_for_domainification` | `self` | `` | modules should be hidden if module def's restrict to domain is not in active domains |





## Functions

No top-level functions found in this file.
