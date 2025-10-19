# Clean Architecture





#### 3 Layered Architecture

1. **Presentation** - UI
2. **Logic** - API
3. **Data** - Database

#### Hexagonal Architecture

* Ports and Adapters
* Make ports for the external services and then connect with those services by writing adapters to those ports
* At the center is Entities and surrounding them are Repositories

#### Onion Architecture

1. Domain services
2. Application services
3. Interfaces and Adapters
4. Representation layer
5. Observability layer

#### Clean Architecture

1. Keep business logic separate from external services
2. Code in the inner layers doesn't have any information about the dependencies outside
3.  Hexagonal and Onion Architectures are ways to implement Clean Architecture

    1. Independent of Frameworks
    2. Testable
    3. Independent of UI
    4. Independent of Database
    5. Independent of Any


4. Domain -> Application -> Ports -> Adapters

{% embed url="https://github.com/JonathanM2ndoza/Hexagonal-Architecture-DDD" %}
