# Software Development

## Challenges

As a software developer, you have likely faced the following challenges:

* How to meet project deadlines?
* How to write clean maintainable code?
* How to adopt TDD principles?
* How to minimize number of bugs?

## Principles

Optivem Framework is designed to help you in your everyday job, helping to to write less code for mundane tasks and providing a solid architecture so that you can get started quickly.

## Solutions

### .NET Core 2.2

Ensure you have the following installed:

* [https://dotnet.microsoft.com/download/dotnet-core](https://dotnet.microsoft.com/download/dotnet-core) \(we have used .NET Core SDK 2.2\)
* [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/) \(we have used Visual Studio Community 2019, and installed via the Visual Studio Installer: ASP.NET and web development\)
* [SQL Server 2017 Developer](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) and [SQL Server Management Studio 17.9.1](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017).

Run Visual Studio \(in the "Getting Started", select "Continue without code"\), use the Package Manager Console \(Tools &gt; NuGet Package Manager &gt; Package Manager Console\) to install the Optivem Template \(in the future you can also uninstall and re-install newer versions\):

```text
PM> dotnet new -i Optivem.Template
```

Create the directory for your new project \(MyWebShop\) and go inside that directory:

```text
PM> mkdir C:\Users\Valentina.Cupac\source\repos\MyWebShop
PM> cd C:\Users\Valentina.Cupac\source\repos\MyWebShop
```

Create a new solution \(MyWebShop.sln\) based on the template inside that directory:

```text
PM> dotnet new optivem
```

Open the solution \(MyWebShop.sln\) and set MyWebShop.Web.RestApi as the StartUp project, and build the solution.

Then adjust the database connection \(inside the project MyWebShop.Web.RestApi, open up the file appsettings.Development.json and ensure that DefaultConnection is appropriately set to your development database server, note that the database does not exist\) yet. Then from the Package Manager Console, run the command to create the database:

```text
PM> Update-Database
```

You can verify inside SQL Server Management Studio that the database has been created.

Then run the application in Debug mode. The application opens up automatically, e.g. [https://localhost:44315/](https://localhost:44315/api/values). You can also execute API calls via swagger, e.g. [https://localhost:44315/swagger/index.html](https://localhost:44315/swagger/index.html) and verify that the response is successful. \(Note that the port on your computer may differ from the port here.\) Finally, at the end you can stop debugging.

To run the automated tests, open up the Test Explorer \(Visual Studio main menu: Test &gt; Windows &gt; Test Explorer\) and rebuild the solution to discover all the tests. For Integration and System tests, you can set the database connection string \(opening up appsettings.Test.json inside the test projects and setting a value for DefaultConnection\). Click on “Run All” inside the Test Explorer \(all tests should pass\).

Then you can use this solution for your actual project needs. We recommend you firstly see the sample structure \(with customers, products and orders\), so that you can see the overall flow, then you can add your own classes and interfaces.

### Java 9

Optivem Framework is planned to be developed also for Java 9, using Spring Framework, Hibernate, etc. This section will be updated with instructions. 

