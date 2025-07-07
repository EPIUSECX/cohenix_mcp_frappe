# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/item_variant.py`

## Classes

### `ItemVariantExistsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidItemAttributeValueError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ItemTemplateCannotHaveStock`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_variant`
**Arguments:** `template, args, variant, manufacturer, manufacturer_part_no`
**Decorators:** ``

**Docstring:**
```
Validates Attributes and their Values, then looks for an exactly
matching Item Variant

:param item: Template Item
:param args: A dictionary with "Attribute" as key and "Attribute Value" as value
```
### `make_variant_based_on_manufacturer`
**Arguments:** `template, manufacturer, manufacturer_part_no`
**Decorators:** ``

**Docstring:**
```
Make and return a new variant based on manufacturer and
manufacturer part no
```
### `validate_item_variant_attributes`
**Arguments:** `item, args`
**Decorators:** ``

**Docstring:**
```

```
### `validate_is_incremental`
**Arguments:** `numeric_attribute, attribute, value, item`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_attribute_value`
**Arguments:** `attributes_list, attribute, attribute_value, item, from_variant`
**Decorators:** ``

**Docstring:**
```

```
### `get_attribute_values`
**Arguments:** `item`
**Decorators:** ``

**Docstring:**
```

```
### `find_variant`
**Arguments:** `template, args, variant_item_code`
**Decorators:** ``

**Docstring:**
```

```
### `create_variant`
**Arguments:** `item, args, use_template_image`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_multiple_variant_creation`
**Arguments:** `item, args, use_template_image`
**Decorators:** ``

**Docstring:**
```

```
### `create_multiple_variants`
**Arguments:** `item, args, use_template_image`
**Decorators:** ``

**Docstring:**
```

```
### `generate_keyed_value_combinations`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
From this:

        args = {"attr1": ["a", "b", "c"], "attr2": ["1", "2"], "attr3": ["A"]}

To this:

        [
                {u'attr1': u'a', u'attr2': u'1', u'attr3': u'A'},
                {u'attr1': u'b', u'attr2': u'1', u'attr3': u'A'},
                {u'attr1': u'c', u'attr2': u'1', u'attr3': u'A'},
                {u'attr1': u'a', u'attr2': u'2', u'attr3': u'A'},
                {u'attr1': u'b', u'attr2': u'2', u'attr3': u'A'},
                {u'attr1': u'c', u'attr2': u'2', u'attr3': u'A'}
        ]
```
### `copy_attributes_to_variant`
**Arguments:** `item, variant`
**Decorators:** ``

**Docstring:**
```

```
### `make_variant_item_code`
**Arguments:** `template_item_code, template_item_name, variant`
**Decorators:** ``

**Docstring:**
```
Uses template's item code and abbreviations to make variant's item code
```
### `create_variant_doc_for_quick_entry`
**Arguments:** `template, args`
**Decorators:** ``

**Docstring:**
```

```

