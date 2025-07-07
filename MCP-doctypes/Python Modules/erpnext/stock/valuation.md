# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/valuation.py`

## Classes

### `BinWiseValuation`
**Inherits:** `ABC`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `add_stock` | `self, qty, rate` | `abstractmethod` |  |
| `remove_stock` | `self, qty, outgoing_rate, rate_generator, is_return_purchase_entry` | `abstractmethod` |  |
| `state` | `self` | `abstractproperty` |  |
| `get_total_stock_and_value` | `self` | `` |  |
| `__repr__` | `self` | `` |  |
| `__iter__` | `self` | `` |  |
| `__eq__` | `self, other` | `` |  |


### `FIFOValuation`
**Inherits:** `BinWiseValuation`


**Docstring:**
```
Valuation method where a queue of all the incoming stock is maintained.

New stock is added at end of the queue.
Qty consumption happens on First In First Out basis.

Queue is implemented using "bins" of [qty, rate].

ref: https://en.wikipedia.org/wiki/FIFO_and_LIFO_accounting
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, state` | `` |  |
| `state` | `self` | `property` | Get current state of queue. |
| `add_stock` | `self, qty, rate` | `` | Update fifo queue with new stock.

args:
        qty: new quantity to add
        rate: incoming rate of new quantity |
| `remove_stock` | `self, qty, outgoing_rate, rate_generator, is_return_purchase_entry` | `` | Remove stock from the queue and return popped bins.

args:
        qty: quantity to remove
        rate: outgoing rate
        rate_generator: function to be called if queue is not found and rate is required. |


### `LIFOValuation`
**Inherits:** `BinWiseValuation`


**Docstring:**
```
Valuation method where a *stack* of all the incoming stock is maintained.

New stock is added at top of the stack.
Qty consumption happens on Last In First Out basis.

Stack is implemented using "bins" of [qty, rate].

ref: https://en.wikipedia.org/wiki/FIFO_and_LIFO_accounting
Implementation detail: appends and pops both at end of list.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, state` | `` |  |
| `state` | `self` | `property` | Get current state of stack. |
| `add_stock` | `self, qty, rate` | `` | Update lifo stack with new stock.

args:
        qty: new quantity to add
        rate: incoming rate of new quantity.

Behaviour of this is same as FIFO valuation. |
| `remove_stock` | `self, qty, outgoing_rate, rate_generator, is_return_purchase_entry` | `` | Remove stock from the stack and return popped bins.

args:
        qty: quantity to remove
        rate: outgoing rate - ignored. Kept for backwards compatibility.
        rate_generator: function to be called if stack is not found and rate is required. |





## Functions

### `round_off_if_near_zero`
**Arguments:** `number, precision`
**Decorators:** ``

**Docstring:**
```
Rounds off the number to zero only if number is close to zero for decimal
specified in precision. Precision defaults to 7.
```

