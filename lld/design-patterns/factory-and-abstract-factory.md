# Factory and Abstract Factory

* **Factory -** Something that creates different types of objects
* **Abstract Factory -** A common definition ( interface ) for factories that create same type of objects.

```python
class AbstractFactory:
    def create_product1(): ...
    def create_product2(): ...


class Platform1Factory(AbstractFactory):
    def create_product1(): ...
    def create_product2(): ...

class Platform2Factory(AbstractFactory):
    def create_product1(): ...
    def create_product2(): ...


def use_factory(factory: AbstractFactory):
    ...

if config.platform == "platform1":
    use_factory(Platform1Factory())
elif config.platform == "platform2":
    use_factory(Platform2Factory())
```
