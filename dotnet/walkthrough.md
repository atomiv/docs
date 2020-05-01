# Walkthrough

## Introduction

In this walkthrough, you will familiarize yourself with the template structure, which contains Customers, Products and Orders. We recommend for you to add additional functionality, e.g. Suppliers, to famiarilize yourself with the template.

## Structure

The template project contains the following layers:

* Core
* Infrastructure
* Web
* Test

## Core

### Domain

Domain entities and associated business logic are implemented in the project MyWebShop.Core.Domain.

#### Define an entity and its identity

Customer is an Entity:

```csharp
    public class Customer : Entity<CustomerIdentity>
    {
        public Customer(CustomerIdentity id, string firstName, string lastName)
            : base(id)
        {
            FirstName = firstName;
            LastName = lastName;
        }

        public string FirstName { get; set; }

        public string LastName { get; set; }
    }
```

CustomerIdentity is used to identify the customer, and the underlying type is Guid:

```csharp
    public class CustomerIdentity : Identity<Guid>
    {
        public CustomerIdentity(Guid value) : base(value)
        {
        }
    }
```

#### Define a factory for the entity

Firstly we define the interface for the factory:

```csharp
    public interface ICustomerFactory : IFactory
    {
        Customer Create(string firstName, string lastName);
    }
```

Then we define the factory implementation:

```csharp
    public class CustomerFactory : ICustomerFactory
    {
        private readonly IIdentityGenerator<CustomerIdentity> _customerIdentityGenerator;

        public CustomerFactory(IIdentityGenerator<CustomerIdentity> customerIdentityGenerator)
        {
            _customerIdentityGenerator = customerIdentityGenerator;
        }

        public Customer Create(string firstName, string lastName)
        {
            var id = _customerIdentityGenerator.Next();

            return new Customer(id, firstName, lastName);
        }
    }
```

#### Define repositories for the entity

This is a mutable repository:

```csharp
    public interface ICustomerRepository : IRepository
    {
        Task AddAsync(Customer customer);

        Task<Customer> FindAsync(CustomerIdentity customerId);

        Task RemoveAsync(CustomerIdentity customerId);

        Task UpdateAsync(Customer customer);
    }
```

This is a readonly repository:

```csharp
    public interface ICustomerReadonlyRepository : IRepository
    {
        Task<bool> ExistsAsync(Guid customerId);

        Task<long> CountAsync();
    }
```







Optivem.Northwind.Core.Domain.Entity. For example, we have the Supplier entity:

 Interfaces for repositories are declared in the project Optivem.Northwind.Core.Domain.Repository. For example, we have ISupplierRepository, which is the repository interface for working with suppliers:

Aside from adding the repository in Optivem.Northwind.Core.Domain.Repository, we also register it in the unit of work INorthwindUnitOfWork. For example, we register ISupplierRepository as a property below:

### Application

Dtos are referenced in the project Optivem.Northwind.Core.Application.Dto. For example, we have the SupplierRequest:

In that same project, we also have the SupplierResponse:

 We declare the interfaces for services in the project Optivem.Northwind.Core.Application.Service. For example, we have the interface ISupplierService:

Then we need to implement the services in the project Optivem.Northwind.Core.Application.Service.Default. For example, we have implemented SupplierService:

### Infrastructure

Domain We implement repositories using the EntityFrameworkCore implementation in the project Optivem.Northwind.Infrastructure.Repository.EntityFrameworkCore \(note: we could have used other providers\). For example, we have implemented SupplierRepository:

Inside that same project, we also add the repository SupplierRepository to the unit of work class NorthwindUnitOfWork:

 \#\#\# Application We implement request mapping using AutoMapper in the project Optivem.Northwind.Infrastructure.Application.Mapping. For example, we have implemented SupplierRequestMapping:

Furthermore, inside that same project we also implement the response mapping. For example, we have implemented SupplierResponseMapping:

 \#\# Web \#\#\# AspNetCore Inside the project Optivem.Northwind.Web.AspNetCore.Rest, we register the services and the mappings inside Startup. For example, we have registered SupplierService, SupplierRequestMapping and SupplierResponseMapping:

Furthermore, in that project, inside the folder Controllers we also need to implement the controllers. For example, we have implemented SuppliersController:

#### Test

Pending documentation.





