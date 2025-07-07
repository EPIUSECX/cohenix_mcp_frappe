# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/location/location.py`

## Classes

### `Location`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `calculate_location_area` | `self` | `` |  |
| `get_location_features` | `self` | `` |  |
| `set_location_features` | `self, features` | `` |  |
| `update_ancestor_location_features` | `self` | `` |  |
| `remove_ancestor_location_features` | `self` | `` |  |
| `add_child_property` | `self` | `` |  |
| `feature_seperator` | `self, child_feature` | `` |  |





## Functions

### `compute_area`
**Arguments:** `features`
**Decorators:** ``

**Docstring:**
```
Calculate the total area for a set of location features.
Reference from https://github.com/scisco/area.

Args:
        `features` (list of dict): Features marked on the map as
                GeoJSON data

Returns:
        float: The approximate signed geodesic area (in sq. meters)
```
### `_polygon_area`
**Arguments:** `coords`
**Decorators:** ``

**Docstring:**
```

```
### `_ring_area`
**Arguments:** `coords`
**Decorators:** ``

**Docstring:**
```

```
### `get_children`
**Arguments:** `doctype, parent, location, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `add_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

