# Metaclasses





Classes that define how other classes should be created.

Metaclasses are inheritable ie. if parent had a metaclass, child automatically gets it.

```python
class MyMeta(type):
    def __new__(cls, name, bases, attr):
        return super().__new__(cls, name, bases, attr) 
    
```

**Calling Sequence on doing Class()**

1. \_\_prepare\_\_ of Metaclass
2. \_\_new\_\_ of Metaclass
3. \_\_call\_\_ of Metaclass
4. \_\_new\_\_ of class
5. \_\_init\_\_ of class

{% embed url="https://www.youtube.com/watch?embeds_referring_euri=https://cdn.iframe.ly/&source_ve_path=MjM4NTE&v=yWzMiaqnpkI" %}
