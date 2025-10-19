# Decorator

Enhance a functionality by wrapping it in a closure.

```python
def decorator(arg1, arg2):
    def outer(func):
        @wraps(func)
        def inner(*args, **kwargs):
            res = func(*args, **kwrags)
            return res
        return inner
    return outer


@decorator(1, 2)
def decorated_fn():
    ...
```
