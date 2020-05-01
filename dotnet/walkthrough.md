# Walkthrough

## Introduction

In this walkthrough, you will familiarize yourself with the template structure, and will be able to implement additional functionality. The template already contains Customers, Products and Orders, so therefore for the purposes of this walkthrough, we will be implementing Suppliers.

## Structure

The template project contains the following layers:

* Core
* Infrastructure
* Web
* Test

## Core

### Domain

Domain entities and associated business logic are implemented in the project MyWebShop.Core.Domain.



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





