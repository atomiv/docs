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

* Core Layer \(contains Domain and Application\)
* Infrastructure Layer \(contains third-party libraries and frameworks, integration with external systems\)
* Web Layer \(contains the REST API and Web UI\)
* Test Layer \(contains Unit, Integration and System tests\)
* IoC Layer \(contains dependency injection\)



The Core Layer contains the Domain Layer and Application Layer. The Domain Layer is based on Domain Driven Design \(DDD\) principles, containing entities and value objects which model the domain, implement the business logic, the "heart" of the system. The Application Layer consists of application services, which in turn execute use cases, these 





The key concept is the separation of concerns:

* Application Core contains application logic \(Application Layer\) and domain logic \(Domain Layer\)
* Presentation Layer contains GUI Views and Controllers, REST Controllers, SOAP Controllers, Console Commands
* Infrastructure Layer contains Databases, Email, Messaging, and any other external agencies

The dependencies are as follows:

* The Application Core is independent of everything else \(i.e. the Application Core does not know about the Presentation Layer nor the Infrastructure Layer\)
* The Presentation Layer sends commands to the Application Core
* The Infrastructure Layer contains implementation for communicating with the database \(e.g. via ORM, sending emails, sending messages to message queues, etc.\)

But, given the independence above, how do they communicate? The answer is: Inversion of Control \(IoC\) - Dependency Injection \(DI\). For example, the Application Core defines interfaces for communicating with a database \(i.e. Repository interfaces\), and inside the Infrastructure layer, the Repository interfaces are implemented \(e.g. using ORM frameworks or any other mechanisms\).

The core benefits is that due to the independence of the Application Core, it ensures separation of concerns and modulaity, swappability of databases, UIs and any frameworks, and also enables the system to be testable. These factors increase system quality and decreasing overall total development and maintenance cost.

