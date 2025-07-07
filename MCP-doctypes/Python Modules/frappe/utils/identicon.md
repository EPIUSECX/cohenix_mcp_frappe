# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/identicon.py`

## Classes

### `Identicon`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, str_, background` | `` | `str_` is the string used to generate the identicon.
`background` is the background of the identicon. |
| `digest` | `self, str_` | `` | Return an MD5 numeric hash. |
| `calculate` | `self` | `` | Creates the identicon.
First three bytes are used to generate the color,
remaining bytes are used to create the drawing |
| `generate` | `self` | `` | Save and show calculated identicon |
| `base64` | `self, format` | `` | Return the identicon's base64

Created by: liuzheng712
Bug report: https://github.com/liuzheng712/identicons/issues |





## Functions

No top-level functions found in this file.
