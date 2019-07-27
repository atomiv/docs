# New project



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

