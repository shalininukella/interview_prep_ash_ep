# MRO



Method resolution order.

Done using C3 Linearization.

`__mro__` is immutable attribute on classes which stores the value returned by `mro` method. In order to modify mro of a subclass we may override `mro` in a metaclass. `mro` method of a class is called on class's instantiation ( not class's object's instantiation )

#### C3 Linearization

L(Z) = Z + merge( L(0), L(1)..... L(n), \[0, 1, ... n] )

merge(0, 1, ... n ) = recursively pick a head from any list thats not in any other list's tail.

If multiple heads are valid pick the left most.

L(\[A, B], \[A, B, C], \[A, B, C, D])\
\=> A + L(\[B], \[B, C], \[B, C, D])\
\=> A, B + L(\[C], \[C, D])\
\=> A, B, C + L(\[D])\
\=> A, B, C, D \\

{% embed url="https://en.wikipedia.org/wiki/C3_linearization" %}
