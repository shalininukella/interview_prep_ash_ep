# Slots

```python
class Point:
    __slots__ = ("x", "y")
```

1. Reduce memory footprint of objects so its useful if we want to create millions of objects of a class
2. Disallows creation of `__dict__`
3. Can't declare extra attributes at run time if slots are defined
4. Disallows creation of weakrefs by default ( because weakrefs to an object are stored in `__weakref__` which is an extra property, so if we want to allow weakrefs we must declare `__weakref__` property in the slots
5. for each slot variable a descriptor is created
6. On **inheritance** slots are also inherited but the child will have dict and weakref unless child also explicitly defines slots
7. In **multiple inheritance** only one parent can have slots
8. To give a doc string for slot variables we can also pass a dictionary with values being doc
