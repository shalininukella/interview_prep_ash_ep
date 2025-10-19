# Distributed Transactions with SAGA

Saga pattern is a way to handle distributed transactions.

A distributed transaction in a microservice architecture is a transaction that spans across multiple microservices. eg. Money transfer (deduct from my account, credit to their account)

Saga says that you either complete the whole thing or run steps to undo what you have done.

**Types of Saga Implementations**

1. **Choreographed** - Multiple services handle invoking each other and undoing
2. **Orchestartor** - One service handles invocation and undoing

There can be cyclic dependencies in choreography and it will be hard to test as you need all services to be up. In Orchestrator we can mock all services to test and there are no cyclic dependencies.
