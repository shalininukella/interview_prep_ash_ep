# Garbage Collection

**Ref Counting Garbage Collection**

A count of how many references of an object are available if refcount for an object == 0 then its garbage collected **immediately**

Some immortal ( not to be confused with immutable ) objects have refcount == 2^32 - 1 by default eg. True, False, None, 1, 2, 3, tuple()

```python
import sys

class A: ...

a = A()

sys.getrefcount(a) # prints 2
```

It prints 2 because a temporary reference is created for a when calling getrefcount as its argument

To really see which objects are referencing to an object we can use gc module

```python
import gc

class A: ...

a = A()

gc.get_referrers(a)
```

**Weak Ref**

To not increase reference counts but keeping track of objects we may use weak references

```python
import weakref

class A: ...
a = A()

weakref.ref(a)
```

eg. \_\_subclasses\_\_ contains a list of weakrefs of subclassed class objects of a python class object

It can also be used for caching

**Cyclic Refs**

If a python object is pointing to itself or any references are making a cycle then the ref counts may never reach zero.

**Generational Garbage Collection**

Traces execution of a program and identifies reachable objects all remaining are considered unreachable and are moved to gen0 for garbage collection

There are 3 generations in python with size 700, 10, 10 by default

There is also a permanent generation where we can send an object by calling `gc.freeze` on it. A frozen object will never get garbage collected.
