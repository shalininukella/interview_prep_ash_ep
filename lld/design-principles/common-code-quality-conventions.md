# Common Code Quality Conventions

**Names**

1. Searchable, Distinct and meaningful
2. Smaller the scope smaller the name eg. an iterator is fine to be called `i` but a global variable needs to be more verbose as it needs to be understandable across more namespaces
3. Derive the names from problem domain rather than solution (language specific) domain. eg. `patients = []` is better than `objects = []`

**Functions**

1. Keep number of arguments few. If there are way too many it often means functions is doing a lot of things.
2. Avoid using boolean flag arguments. It likely means you are combining two behaviours in the same function.
3. Avoid returning NULL. It leads to unexpected behaviour, raising corresponding exception is better.

**Function Side Effects**

One function mutation variables outside its scope. eg. In python mutable defaults cause a rather unexpected side effect.

**Command Query Separation**

Command means Mutation, Query means lookup, both should have separate functions, single function shouldn't do both.

**Exceptions vs Error Codes**

* **Exceptions**

1. Enforce handling
2. forcefully stops the flow of program.
3. Bubbles up automatically
4. Expensive as it creates objects

* **Error Codes**

1. Doesn't enforce handling
2. doesn't stop flow of program unless intended to
3. Manually needs to bubbled up
4. Cheap and fast
