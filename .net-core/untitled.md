# Getting started

## Some text

Some text

```
$ some code
```

{% hint style="info" %}
 Some text
{% endhint %}

Some text

```
// Some text
Some text
```





### Optivem Framework <a id="optivem-framework"></a>

[![Build Status](https://img.shields.io/appveyor/ci/optivem/framework-dotnetcore.svg)](https://ci.appveyor.com/project/optivem/framework-dotnetcore) [![MIT License](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)

Welcome to the Optivem Framework! The Optivem Framework was created to help you increase code quality, help you deliver products faster to customers and reduce your overall software development cost. This documentation page will show you how to get up-and-running with the Optivem Framework in your .NET Core 2.2 software projects.

### Table of Contents <a id="table-of-contents"></a>

* [Introduction](https://opensource.optivem.com/framework-dotnetcore/#introduction)
* [Getting Started](https://opensource.optivem.com/framework-dotnetcore/#getting-started)
* [Technical Reference](https://opensource.optivem.com/framework-dotnetcore/#technical-reference)
* [Getting support](https://opensource.optivem.com/framework-dotnetcore/#support)
* [License](https://opensource.optivem.com/framework-dotnetcore/#license)

### Introduction <a id="introduction"></a>

Optivem Framework was created to accelerate the development of enterprise applications, so that you can quickly create new projects for your customers.

The Optivem Framework is founded upon Clean Architecture principles and supports:

* Modularity & re-usability
* Extensibility & flexibility
* Maintainability & testibility
* Scalability and portability

The architecture consists of the following layers:

* Core Layer \(contains Domain and Application\)
* Infrastructure Layer \(contains third-party libraries and frameworks, integration with external systems\)
* Dependency Injection Layer \(used to setup the compostion root\)
* Web Layer \(contains the REST API and presentation\)
* Test Layer \(contains Unit, Integration and System tests\)

### Getting started <a id="getting-started"></a>

We are using Visual Studio 2019 and .NET Core 2.2.

#### Installation <a id="installation"></a>

To install the Optivem Template:

1. Run Visual Studio
2. Open the Package Manager Console \(Visual Studio main menu: Tools &gt; NuGet Package Manager &gt; Package Manager Console\)
3. Run the following command inside the Package Manager Console

```text
PM> dotnet new -i Optivem.Template
```

1. In the future, you can run this same command to get updated versions of the template

#### Create a new project <a id="create-a-new-project"></a>

To create a new project:

1. Run Visual Studio
2. Open the Package Manager Console \(Visual Studio main menu: Tools &gt; NuGet Package Manager &gt; Package Manager Console\)
3. Create the directory for your new project, for example:

```text
PM> mkdir C:\Users\Valentina.Cupac\source\repos\MyWebShop
```

1. Go inside the new directory:

```text
PM> cd C:\Users\Valentina.Cupac\source\repos\MyWebShop
```

1. Create the Visual Studio Solution based on the Optivem Template:

```text
PM> dotnet new optivem
```

1. Open the solution \(Visual Studio main menu: File &gt; Open Project/Solution, selecting the folder and inside it the solution MyWebShop.sln\)
2. Rebuild the solution
3. Set MyWebShop.Web.RestApi as the StartUp project
4. Inside MyWebShop.Web.RestApi, open up the file appsettings.Development.json, you can adjust the DefaultConnection to the location where the database should be created
5. Inside the Package Manager Console, run the command to create the database:

```text
PM> Update-Database
```

1. Run the application
2. Browser opens up https://localhost:44315/api/values
3. Go to the Swagger page https://localhost:44315/swagger/index.html where you can execute any API calls
4. Stop Debugging
5. Open up the Test Explorer \(Visual Studio main menu: Test &gt; Windows &gt; Test Explorer\)
6. Rebuild the solution to discover all the tests
7. Click on “Run All” inside the Test Explorer \(all tests should pass\)

### Technical Reference <a id="technical-reference"></a>

#### Optivem Framework Core <a id="optivem-framework-core"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Core.Common.svg)](https://www.nuget.org/packages/Optivem.Framework.Core.Common) Optivem.Framework.Core.Common
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Core.Domain.svg)](https://www.nuget.org/packages/Optivem.Framework.Core.Domain) Optivem.Framework.Core.Domain
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Core.Application.svg)](https://www.nuget.org/packages/Optivem.Framework.Core.Application) Optivem.Framework.Core.Application
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Core.Application.Interface.svg)](https://www.nuget.org/packages/Optivem.Framework.Core.Application.Interface) Optivem.Framework.Core.Application.Interface
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Core.All.svg)](https://www.nuget.org/packages/Optivem.Framework.Core.All) Optivem.Framework.Core.All

#### Optivem Framework Infrastructure <a id="optivem-framework-infrastructure"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.AspNetCore.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.AspNetCore) Optivem.Framework.Infrastructure.AspNetCore
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.AutoMapper.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.AutoMapper) Optivem.Framework.Infrastructure.AutoMapper
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.CsvHelper.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.CsvHelper) Optivem.Framework.Infrastructure.CsvHelper
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.EntityFrameworkCore.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.EntityFrameworkCore) Optivem.Framework.Infrastructure.EntityFrameworkCore
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.FluentValidation.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.FluentValidation) Optivem.Framework.Infrastructure.FluentValidation
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.MediatR.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.MediatR) Optivem.Framework.Infrastructure.MediatR
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.NewtonsoftJson.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.NewtonsoftJson) Optivem.Framework.Infrastructure.NewtonsoftJson
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.Selenium.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.Selenium) Optivem.Framework.Infrastructure.Selenium
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Infrastructure.System.svg)](https://www.nuget.org/packages/Optivem.Framework.Infrastructure.System) Optivem.Framework.Infrastructure.System

#### Optivem Framework Dependency Injection <a id="optivem-framework-dependency-injection"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Common.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Common) Optivem.Framework.DependencyInjection.Common
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Core.Domain.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Core.Domain) Optivem.Framework.DependencyInjection.Core.Domain
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Core.Application.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Core.Application) Optivem.Framework.DependencyInjection.Core.Application
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Infrastructure.AutoMapper.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Infrastructure.AutoMapper) Optivem.Framework.DependencyInjection.Infrastructure.AutoMapper
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Infrastructure.EntityFrameworkCore.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Infrastructure.EntityFrameworkCore) Optivem.Framework.DependencyInjection.Infrastructure.EntityFrameworkCore
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Infrastructure.FluentValidation.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Infrastructure.FluentValidation) Optivem.Framework.DependencyInjection.Infrastructure.FluentValidation
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Infrastructure.MediatR.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Infrastructure.MediatR) Optivem.Framework.DependencyInjection.Infrastructure.MediatR
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.DependencyInjection.Infrastructure.NewtonsoftJson.svg)](https://www.nuget.org/packages/Optivem.Framework.DependencyInjection.Infrastructure.NewtonsoftJson) Optivem.Framework.DependencyInjection.Infrastructure.NewtonsoftJson

#### Optivem Framework Web <a id="optivem-framework-web"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Web.AspNetCore.svg)](https://www.nuget.org/packages/Optivem.Framework.Web.AspNetCore) Optivem.Framework.Web.AspNetCore

#### Optivem Framework Test <a id="optivem-framework-test"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.AspNetCore.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.AspNetCore) Optivem.Framework.Test.AspNetCore
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.EntityFrameworkCore.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.EntityFrameworkCore) Optivem.Framework.Test.EntityFrameworkCore
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.FluentAssertions.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.FluentAssertions) Optivem.Framework.Test.FluentAssertions
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.MicrosoftExtensions.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.MicrosoftExtensions) Optivem.Framework.Test.MicrosoftExtensions
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.Selenium.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.Selenium) Optivem.Framework.Test.Selenium
* [![NuGet](https://img.shields.io/nuget/v/Optivem.Framework.Test.Xunit.svg)](https://www.nuget.org/packages/Optivem.Framework.Test.Xunit) Optivem.Framework.Test.Xunit

#### Optivem Template <a id="optivem-template"></a>

* [![NuGet](https://img.shields.io/nuget/v/Optivem.Template.svg)](https://www.nuget.org/packages/Optivem.Template) Optivem.Template

### Getting support <a id="getting-support"></a>

To report any issues and bugs, or if you have any suggestions for improvements and new features, please create a ticket using the Issue Tracker: [github.com/optivem/framework-dotnetcore/issues](https://github.com/optivem/framework-dotnetcore/issues).

### License <a id="license"></a>

Licensed under the [MIT license](http://opensource.org/licenses/mit-license.php). This means you’re free to use it for commercial and non-commercial purposes.

### Copyright <a id="copyright"></a>

Copyright © 2019 [Optivem](https://www.optivem.com/) All Rights Reserved.

