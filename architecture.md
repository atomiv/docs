# Software Architecture

## Challenges

As a software architect, your faced with challenges in design software architectures with the following characteristics:

* Modularity & re-usability
* Extensibility & flexibility
* Maintainability & testibility
* Scalability and portability

## Principles

Optivem Framework was envisioned to help you design and implement high quality architectures for software projects and products. Optivem Framework provides a templated solution architecture based on well-known best practices in clean architecture:

* [Hexagonal Architecture, aka. Ports and Adapters \(Alistair Cockburn, 2005\)](https://dzone.com/articles/hexagonal-architecture-is-powerful) 
* [Onion Architecture \(Jeffrey Palermo, 2008\)](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/)
* [Clean Architecture \(Robert C. Martin, 2012\)](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)

## Solutions

The Optivem Template provides a ready-made project with the following layers:

* Core Layer
* Infrastructure Layer
* Presentation Layer
* DI Layer
* Test Layer

### Layers

The **Core Layer** contains the **Domain Layer** and **Application Layer**. The Domain Layer is based on Domain Driven Design \(DDD\) principles, containing entities and aggregate roots, value objects and repository interfaces. There model the domain, implement the business logic, the "heart" of the system. The Application Layer consists of application services, which in turn execute use cases, these manage the flow, for example, calling repositories to retrieve aggregate roots, executing some actions, and then persisting the aggregate roots. The Application Layer consists of the Application Layer interfaces \(application service interfaces\) and Application Layer implementation \(application service implementation, use case implementation\). The Domain Layer is self-contained, and the Application Layer depends only on the Domain Layer.

The **Infrastructure Layer** contains third-party libraries and frameworks, as well as integration with external systems. The infrastructure contains the implementation for any interfaces which have been declared in the Core Layer. For example, inside the Infrastructure Layer contains repository implementations \(e.g. using ORMs, SQL, NoSQL, etc.\), implementations for messaging and notifications \(e.g. integration with message queues, sending emails, sending SMS's\), and implementations for integration with any external systems \(e.g. integration with ERP, CRM, any external web services, databases, etc.\). The Infrastructure Layer depends on the Core Layer, but the Core Layer does _not_ depend on the Infrastructure Layer. This means that infrastructural concerns are replaceable \(e.g. switching to a different database system, switching to a different messaging system, switching to other frameworks, etc.\).

The **Presentation Layer** presents the application to clients. It is the external interface to the software system. The Web Layer **Web Layer** serves as a web-based presentation layer, whilst the **CLI Layer** serves as a console-based application layer. The Web Layer contains REST APIs \(controllers\), SOAP services, and also additionally Web UI clients \(views and controllers\) and JavaScript web clients \(Angular, React, Vue, etc.\). The CLI Layer contains the console application \(console commands\). The Presentation Layer is dependent only on the application service interfaces which are declared in the Application Layer, but is not dependent on Application Layer implementation nor the Domain Layer implementation. On the other hand, the Core Layer does _not_ depend on the Web Layer. This means that the presentation is easily replaceable \(e.g. choosing any frontend implementations\), and it also ensures that the Core Layer can be tested even without the Web Layer.

The **DI Layer** contains the dependency injection mechanism, whereby it binds together the implementations from the Infrastructure Layer with the interfaces that have been defined in the Core Layer. This is also known as the "composition root", because it is at this point, the entry point for the application execution, where the dependencies are composed.

The **Test Layer** contains all the automated tests - Unit tests, Integration tests and System tests. Testing the Domain Layer is done exclusively through unit tests, because the Domain Layer contains exclusively business logic, and any interfaces to external systems are mocked. Testing the Application Layer is also able to be done via unit tests, to test the application logic. Furthermore, Integration tests can be made for the entire Core Layer, and System tests for the Web Layer.

### Dependencies

To summarize, the dependencies are as follows:

The **Core Layer** is self-contained and it does not dependent on any other layers.

* The **Domain Layer** does not have dependencies on other layers. 
* The **Application Layer Interface** do not contain dependencies on other layers. 
* The **Application Layer Implementation** depends both on Application Layer interfaces and the Domain Layer.

Other layers contain dependencies as follows:

* The **Infrastructure Layer** depends on the Core Layer, because it implements the interfaces defined in the Core Layer. Thus, it is an "implementation detail" with ORM's, frameworks and external systems.
* The **Presentation Layer** depends on the Application Layer interfaces. 
* The **DI Layer** depends on the Core Layer and the Infrastructure Layer.
* The **Test Layer** depends on the layers it is testing.

The core benefits is that due to the independence of the Application Core, it ensures separation of concerns and modularity, swappability of databases, UIs and any frameworks, and also enables the system to be testable. These factors increase system quality and decreasing overall total development and maintenance cost.

### Flow

The flow is as follows:

1. Client sends a request to the **Presentation Layer**.
2. The **Presentation Layer** sends the _**Request**_ to the **Application Layer Interface**, by calling a method in one of the _**Application Service Interfaces**_.
3. The **DI Layer** resolves the application service interface based on actual service implementation in the **Application Layer Implementation**. Furthermore, if the application service interface has dependencies on other interfaces which are in the Application Layer, then those are resolved too.
4. The application service implementation in the **Application Layer Implementation** handles the request by executing a use case which handles that request, whereby the use case is implemented in the Application Layer Implementation.  The **DI Layer** resolves any dependencies that the use case has, e.g. the **DI Layer** resolves the repository interfaces based on implementations in the **Infrastructure Layer**.
5. The _**Use Case**_ reads / interprets the _**Request**_, and then it handles the request as follows in order to produce a _**Response**_:
   1. In cases of _**Query Use Cases**_, i.e. use cases which only retrieve data but do not do modifications, the Query Use Case will likely call the _**Repository Interfaces**_ in the Domain Layer to get the aggregate roots \(based on some query\), and then it will generate the _**Response.**_
   2. In cases of _**Command Use Cases**_, i.e. use cases which execute a change on the system, then the Command Use Case will likely call the _**Repository Interfaces**_ in the Domain Layer to retrieve the aggregate root\(s\), execute some action on the aggregate root \(which internally contains business logic, which is encapsulated\), and then it will add or update or delete the aggregate root via the Repository Interface. Finally, it will generate a _**Response**_.
6. The **Application Layer** returns the _**Response**_ to the Presentation Layer.
7. The **Presentation Layer** presents the _**Response**_ to the client.

