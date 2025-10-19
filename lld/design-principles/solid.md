# SOLID

**Single Responsibility**

The class should only have one reason to change.

* It doesn't mean that a class should only do one thing.
* It means that whatever it does should be closely related.
* Like in FastAPI class although `add_router` and `exception_handler` are quite _different_ types of functionalities its still fine to have them in the same class as they are still defining application level behaviour.

**Open Closed**

Open for extension but closed for modification.

* We shouldn't have to change the main code for extending the utility of a class.
* eg. in FastAPI class get, post, delete, patch's functionalities can be extended easily using `decorator` pattern
* Similarly `strategy` pattern also helps in implementing the same.

**Liskov Substitution**

A child class should be able to substitute a parent class.

* Different code should depend on an interface rather than concrete
* eg. in SQLAlchemy `Dialect` class is extended by different drivers which is then used by SQLAlchemy's ORM

**Interface Segregation**

No code should be forced to implement methods that it doesn't use.

* Make smaller interfaces
* Most often violated in dynamically typed languages by raising a NotImplementedException
* eg. The `Dialect` interface is huge in SQLAlchemy and can potentially be broken down to smaller chunks
* Most often seen in Repository pattern where we end up implementing the writer, reader functionalities in one whereas there should be RepositoryReader and RepositoryWriter two separate interfaces.

**Dependency Inversion**

Higher level code should not be directly dependent on lower level code.

* Make an interface -> Implement that interface -> use that interface in all places
* Abstractions should not depend on details, details should depend on abstractions
* _In Python its better to use Protocols to define interfaces as it checks for signatures as well_

[![Logo](https://ashish-shukla.gitbook.io/notes/~gitbook/image?url=https%3A%2F%2Fgithub.com%2Ffluidicon.png\&width=20\&dpr=4\&quality=100\&sign=795e9297\&sv=2)fastapi/fastapi/applications.py at master · fastapi/fastapiGitHub](https://github.com/tiangolo/fastapi/blob/master/fastapi/applications.py#L48)FastAPI App class

[![Logo](https://ashish-shukla.gitbook.io/notes/~gitbook/image?url=https%3A%2F%2Fgithub.com%2Ffluidicon.png\&width=20\&dpr=4\&quality=100\&sign=795e9297\&sv=2)sqlalchemy/lib/sqlalchemy/engine/interfaces.py at 800932af467109f06c0196c42ae86272a5d7f96a · zzzeek/sqlalchemyGitHub](https://github.com/zzzeek/sqlalchemy/blob/800932af467109f06c0196c42ae86272a5d7f96a/lib/sqlalchemy/engine/interfaces.py#L628)SQLAlchemy Dialect
