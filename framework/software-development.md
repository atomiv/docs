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

* [Microsoft .NET Core SDK 2.2.104](https://dotnet.microsoft.com/download)
* [Visual Studio Community 2017 Version 15.9.4](https://visualstudio.microsoft.com/vs/community/) \(Visual Studio Installer: ASP.NET and web development\)
* [SQL Server 2017 Developer](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) and [SQL Server Management Studio 17.9.1](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017).

Within Visual Studio, use the Package Manager Console \(Tools &gt; NuGet Package Manager &gt; Package Manager Console\) to install the Optivem Template \(in the future you can also uninstall and re-install newer versions\):

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

Run the application in Debug mode. The application opens up automatically, e.g. [https://localhost:44315/api/values](https://localhost:44315/api/values). You can also execute API calls via [https://localhost:44315/swagger/index.html](https://localhost:44315/swagger/index.html). Finally, at the end you can stop debugging.

To run the automated tests, open up the Test Explorer \(Visual Studio main menu: Test &gt; Windows &gt; Test Explorer\) and rebuild the solution to discover all the tests. Click on “Run All” inside the Test Explorer \(all tests should pass\).

