# Descriptors

#### \_\_get\_\_(self, obj, obj\_type)

obj - if called on object else None.\
obj\_type - class of object if called on object else the class itself.

#### \_\_set\_\_(self, obj, value)

obj - object on which value is being set.\
value - the value we are trying to set on object at the descriptor.\
\
\&#xNAN;_DOESNT get called on classes. CLASS.descriptor = value will just replace the descriptor altogether_

#### \_\_delete\_\_(self, obj)

obj - the object from which the value is being deleted.\
\
\&#xNAN;_DOESNT get called on classes. del CLASS.descriptor will just delete the descriptor altogether_

#### Data Descriptor

Descriptor with get and atleast set or delete or both.

#### Non Data Descriptor

Descriptor with only get

**DATA DESCRIPTORS ALWAYS OVERRIDE THE ACCESS OF INSTANCE VARIABLES.**

```python
class DescriptorAttribute:
    def __init__(self, value, name):
        self._val = value
        self._name = name
    
    def __get__(self, obj, objtype):
	   # obj = the object on which its being tried to access
        return obj.__dict__[self._name] * 10
    
    def __set__(self, obj, val):
        self._val = val
        obj.__dict__[self._name] = val

class ABC:
    a = DescriptorAttribute(1, "name")


a = ABC()
a.a = 100
print(a.a)
```

#### Attribute Access Order

When we do `object.attribute` it calls `__getattribute__` on that object, this method in the `object` class implements the lookup algorithm

1. for class in \_\_mro\_\_ if attr found and attr is a data descriptor then call `__get__`
2. Object's `__dict__[attr]`
3. Class's `__dict__[attr]` is descriptor then call `__get__` on it else return the value
4. `__getattr__`
5. `raise AttributeError`

{% embed url="https://blog.peterlamut.com/2018/11/04/python-attribute-lookup-explained-in-detail/" %}

***
