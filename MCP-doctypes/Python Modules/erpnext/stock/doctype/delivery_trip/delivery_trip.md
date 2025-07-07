# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/delivery_trip/delivery_trip.py`

## Classes

### `DeliveryTrip`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_stop_addresses` | `self` | `` |  |
| `validate_delivery_note_not_draft` | `self` | `` |  |
| `update_status` | `self` | `` |  |
| `update_delivery_notes` | `self, delete` | `` | Update all connected Delivery Notes with Delivery Trip details
(Driver, Vehicle, etc.). If `delete` is `True`, then details
are removed.

Args:
        delete (bool, optional): Defaults to `False`. `True` if driver details need to be emptied, else `False`. |
| `process_route` | `self, optimize` | `` | Estimate the arrival times for each stop in the Delivery Trip.
If `optimize` is True, the stops will be re-arranged, based
on the optimized order, before estimating the arrival times.

Args:
        optimize (bool): True if route needs to be optimized, else False |
| `form_route_list` | `self, optimize` | `` | Form a list of address routes based on the delivery stops. If locks
are present, and the routes need to be optimized, then they will be
split into sublists at the specified lock position(s).

Args:
        optimize (bool): `True` if route needs to be optimized, else `False`

Returns:
        (list of list of str): List of address routes split at locks, if optimize is `True` |
| `rearrange_stops` | `self, optimized_order, start` | `` | Re-arrange delivery stops based on order optimized
for vehicle routing problems.

Args:
        optimized_order (list of int): The index-based optimized order of the route
        start (int): The index at which to start the rearrangement |
| `get_directions` | `self, route, optimize` | `` | Retrieve map directions for a given route and departure time.
If optimize is `True`, Google Maps will return an optimized
order for the intermediate waypoints.

NOTE: Google's API does take an additional `departure_time` key,
but it only works for routes without any waypoints.

Args:
        route (list of str): Route addresses (origin -> waypoint(s), if any -> destination)
        optimize (bool): `True` if route needs to be optimized, else `False`

Returns:
        (dict): Route legs and, if `optimize` is `True`, optimized waypoint order |





## Functions

### `get_contact_and_address`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_contact`
**Arguments:** `out, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_address`
**Arguments:** `out, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_contact_display`
**Arguments:** `contact`
**Decorators:** ``

**Docstring:**
```

```
### `sanitize_address`
**Arguments:** `address`
**Decorators:** ``

**Docstring:**
```
Remove HTML breaks in a given address

Args:
        address (str): Address to be sanitized

Returns:
        (str): Sanitized address
```
### `notify_customers`
**Arguments:** `delivery_trip`
**Decorators:** ``

**Docstring:**
```

```
### `get_attachments`
**Arguments:** `delivery_stop`
**Decorators:** ``

**Docstring:**
```

```
### `get_driver_email`
**Arguments:** `driver`
**Decorators:** ``

**Docstring:**
```

```

