# Microservices vs Monolith vs SOA

#### Monolith

One big service that hosts all of the functionalities.

* Easy to maintain
* No service communication overhead
* Hard to scale
* Hard to parallelize work
* Frequent deployments
* Easy to debug

#### Microservices

Similar functionalities clubbed together and split into separate features

* Easy to scale
* Individual deployments
* Has communication overhead
* Hard to debug

**Inter Sevice Communication**

1. **API -** over HTTP or gRPC when Sync comm is required
2. **Message Broker -** Async eg. sending notifications
3. **Service Mesh -** Let a sidecar handle the discoverability and observability and communication

#### Service Oriented Architecture

Building reusable services that dont really have a usage scope from day 1.

eg. Having an IP locator service

**The Primary Difference Between SoA and Microservice Architecture is that in SoA we dont have the final intent when designing the services.**
