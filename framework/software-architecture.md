# Software Architects

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

The **Presentation Layer** presents the application to clients. The Web Layer **Web Layer** serves as a web-based presentation layer, whilst the **CLI Layer** serves as a console-based application layer. The Web Layer contains REST APIs \(controllers\), SOAP services, and also additionally Web UI clients \(views and controllers\) and JavaScript web clients \(Angular, React, Vue, etc.\). The CLI Layer contains the console application \(console commands\). The Presentation Layer is dependent only on the application service interfaces which are declared in the Application Layer, but is not dependent on Application Layer implementation nor the Domain Layer implementation. On the other hand, the Core Layer does _not_ depend on the Web Layer. This means that the presentation is easily replaceable \(e.g. choosing any frontend implementations\), and it also ensures that the Core Layer can be tested even without the Web Layer.

The **DI Layer** contains the dependency injection mechanism, whereby it binds together the implementations from the Infrastructure Layer with the interfaces that have been defined in the Core Layer. This is also known as the "composition root", because it is at this point, the entry point for the application execution, where the dependencies are composed. 

The **Test Layer** contains all the automated tests - Unit tests, Integration tests and System tests. Testing the Domain Layer is done exclusively through unit tests, because the Domain Layer contains exclusively business logic, and any interfaces to external systems are mocked. Testing the Application Layer is also able to be done via unit tests, to test the application logic. Furthermore, Integration tests can be made for the entire Core Layer, and System tests for the Web Layer.

### Dependencies

To summarize, the dependencies are as follows:

The **Core Layer** is self-contained and it does not dependent on any other layers. 

The Domain Layer does not have dependencies on other layers. The Application Layer interfaces do not contain dependencies on other layers. The Application Layer implementation depends both on Application Layer interfaces and the Domain Layer.

The **Infrastructure Layer** depends on the Core Layer, because it implements the interfaces defined in the Core Layer. Thus, it is an "implementation detail" with ORM's, frameworks and external systems.

The **Presentation Layer** depends on the Application Layer interfaces.

The **DI Layer** depends on the Core Layer and the Infrastructure Layer.

* 




The dependencies are as follows:

* The Application Core is independent of everything else \(i.e. the Application Core does not know about the Presentation Layer nor the Infrastructure Layer\)
* The Presentation Layer sends commands to the Application Core
* The Infrastructure Layer contains implementation for communicating with the database \(e.g. via ORM, sending emails, sending messages to message queues, etc.\)

But, given the independence above, how do they communicate? The answer is: Inversion of Control \(IoC\) - Dependency Injection \(DI\). For example, the Application Core defines interfaces for communicating with a database \(i.e. Repository interfaces\), and inside the Infrastructure layer, the Repository interfaces are implemented \(e.g. using ORM frameworks or any other mechanisms\).

The core benefits is that due to the independence of the Application Core, it ensures separation of concerns and modulaity, swappability of databases, UIs and any frameworks, and also enables the system to be testable. These factors increase system quality and decreasing overall total development and maintenance cost.

