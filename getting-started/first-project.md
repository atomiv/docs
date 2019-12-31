# First Project



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





## 

## 

## Getting Super Powers

Becoming a super hero is a fairly straight forward process:

```
$ give me super-powers
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

{% code title="hello.sh" %}
```bash
# Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```
{% endcode %}



