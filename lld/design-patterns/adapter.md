# Adapter

Call incompatible code through an adapter class.

Adapter is a middle man which translates one interface to other.

```python
class IncompatibleClass:
     def incompatible_function():
          ...

class CompatibilityAdapter(ABC):
     @abstractmethod
     def compatible_function():
          ...

class IncompatibleClassAdapter(IncompatibleClass, CompatibilityAdapter):
     def compatible_function():
          return self.incompatible_function()

if __name__ == "__main__":
     IncompatibleClassAdapter().compatible_function()
```
