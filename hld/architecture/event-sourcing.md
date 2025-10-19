# Event Sourcing

A way to store distributed state.\
\
Storing events rather than hard facts, the events can be used to calculate current state.

* Get rid of concurrency problems
* Use versioning or event uid on events to avoid double writing. ( **Optimistic Concurrency** )

{% embed url="https://www.youtube.com/watch?t=1s&v=yFjzGRb8NOk" %}
