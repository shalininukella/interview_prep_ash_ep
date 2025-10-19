# Chain of Responsibility

Forward a source event through inter related handlers and let them use or forward (or not) it to the next.

Classic example is how javascript does event bubbling.

```python
class BaseLink():
    def handle(): ...
    
    def link(other): ...

class Link1():
    def handle(): ...

class Link2():
    def handle(): ...

class Link3():
    def handle(): ...

this = Event()
Link1().link(Link2().link(Link3())).handle(this)
```
