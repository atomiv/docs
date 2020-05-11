# Layers

## Core

At the system center, we have the Core Layer, composed of the Domain Layer and Application Layer. The Domain Layer implements the business logic. The Application Layer contains thin application services, which execute use cases \(and use cases delegate execution to the domain\). Inside the Core Layer, any external dependencies are interfaces \(e.g. Domain Layer contains repository interfaces for data persistence\).

The Core Layer contains the Domain Layer and Application Layer. The Domain Layer is based on Domain Driven Design \(DDD\) principles, containing entities and aggregate roots, value objects and repository interfaces. There model the domain, implement the business logic, the “heart” of the system. The Application Layer consists of application services, which in turn execute use cases, these manage the flow, for example, calling repositories to retrieve aggregate roots, executing some actions, and then persisting the aggregate roots. The Application Layer consists of the Application Layer interfaces \(application service interfaces\) and Application Layer implementation \(application service implementation, use case implementation\). The Domain Layer is self-contained, and the Application Layer depends only on the Domain Layer.

## Infrastructure

The Infrastructure Layer contains the implementations for the interfaces defined in the Core Layer. For example, it contains implementations using ORM’s for data persistence, file system access implementation, email notification implementation.

The Infrastructure Layer contains third-party libraries and frameworks, as well as integration with external systems. The infrastructure contains the implementation for any interfaces which have been declared in the Core Layer. For example, inside the Infrastructure Layer contains repository implementations \(e.g. using ORMs, SQL, NoSQL, etc.\), implementations for messaging and notifications \(e.g. integration with message queues, sending emails, sending SMS’s\), and implementations for integration with any external systems \(e.g. integration with ERP, CRM, any external web services, databases, etc.\). The Infrastructure Layer depends on the Core Layer, but the Core Layer does not depend on the Infrastructure Layer. This means that infrastructural concerns are replaceable \(e.g. switching to a different database system, switching to a different messaging system, switching to other frameworks, etc.\).

## Web Service

The Web Service Layer contains the implementations for web services which exposed the application services in a web based way. We provide REST API implementations - thin controllers which delegate to the application services, which also forms the microservice boundary. Aside from REST API, SOAP could also be used.

## UI

The UI Layer contains implementations for various clients - web clients, mobile clients, CLI clients, desktop clients. Examples of web clients are: ASP.NET Core MVC apps, Angular apps, react apps, Vue apps, etc.

The Presentation Layer presents the application to clients. It is the external interface to the software system. The Web Layer Web Layer serves as a web-based presentation layer, whilst the CLI Layer serves as a console-based application layer. The Web Layer contains REST APIs \(controllers\), SOAP services, and also additionally Web UI clients \(views and controllers\) and JavaScript web clients \(Angular, React, Vue, etc.\). The CLI Layer contains the console application \(console commands\). The Presentation Layer is dependent only on the application service interfaces which are declared in the Application Layer, but is not dependent on Application Layer implementation nor the Domain Layer implementation. On the other hand, the Core Layer does not depend on the Web Layer. This means that the presentation is easily replaceable \(e.g. choosing any frontend implementations\), and it also ensures that the Core Layer can be tested even without the Web Layer.

## DI

The DI Layer contains the dependency injection mechanism, whereby it binds together the implementations from the Infrastructure Layer with the interfaces that have been defined in the Core Layer. This is also known as the “composition root”, because it is at this point, the entry point for the application execution, where the dependencies are composed.

## Test

The Test Layer contains all the tests - unit tests, integration tests, e2e system tests, for testing the layers mentioned above.

The Test Layer contains all the automated tests - Unit tests, Integration tests and System tests. Testing the Domain Layer is done exclusively through unit tests, because the Domain Layer contains exclusively business logic, and any interfaces to external systems are mocked. Testing the Application Layer is also able to be done via unit tests, to test the application logic. Furthermore, Integration tests can be made for the entire Core Layer, and System tests for the Web Layer.

### 



