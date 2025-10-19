# Mediator Pattern

Bi directional communication between multiple incompatible interfaces.

```python
class Mediator:
    def notify(self, sender: Type["Mediated"], event: Any):
        ...

class Mediated:
    def __init__(self):
        self._mediator = None
    
    @property
    def mediator(self):
        return self._mediator
    
    @mediator.setter
    def mediator(self, mediator):
        self._mediator = mediator
```
