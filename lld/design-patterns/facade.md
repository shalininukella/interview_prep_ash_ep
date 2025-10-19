# Facade

Abstract a subsystem with a simpler interface.

```python
class Functionality1:
    def complex_stuff1(): ...

class Functionality2:
    def complex_stuff2(): ...

class Functionlityn:
    def complex_stuff3(): ...


class SimpleFacade:
    def __init__(self):
        self.fn1 = Functionality1()
        self.fn2 = Functionality2()
        self.fnn = Functionalityn()

    def functinon():
        self.fn1.complex_stuff1()
        self.fn2.complex_stuff2()
        self.fn3.complex_stuff3()
```
