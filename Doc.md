### 🙌 START
---

*Blazor Web Assembly is a Single page app framework for building interective client side web apps with dot net. It uses open Web standard without plugin or recompiling code into other languages. This Course will teach you how to use balzor web assembly & web api on .Net 7 . We will build step by step a shopping Cart Application. We also provide the guide on how to intigrate a payment gateway into our blazor web Assembly component so that a user able to pay for products through our application using a debit or credit card or in the paypal account.00:00 - 00:50*

*Blazor is a relatively new feature of asp dot net. It offers two hosting model. A server side hosting model &  a client side hosting model. We are going to use the client side hosting model for the development of our shopping cart application. The significanse of this hosting model is that the C# code runs directly within our browsers. What makes this possible is a technology named `Web Assembly`. In recent years the creation of SPA applications or single page applications have become very popular as web solutions. Recently Javascript frameworks like Angular or React have been the avilable choices for the creation of spa applications. With Blazor we are now able to create our single page applications using C#. We don't necessaryly need to depend on  javascript for the creation of our interective UI Code.
We can create this code using C#. In this appliaction however the payment gateway provided by paypal is coded in javascript. So we will use blazor into our probality funtionality with javascript to interect with the relavent javascript paypal code. 02:08 - 03:20*

*Add a new Blazor Web Assembly App Project. A project template for creating a Blazor app that runs on WebAssembly and is optionally hosted by an ASP.NET Core app. This template can be used for web apps with rich dynamic user interfaces (UIs) 03:20 - 04:16*

*Add a new ASP.NET Core Web API Project Template (A project template for creating an ASP.NET Core application with an example Controller for a RESTful HTTP service. This template can also be used for ASP.NET Core MVC Views & Controllers) *

*We Enable `OpenAPI` support. By doing this the `Swashbuckle` NuGet Package will be automatically installed & the appropriate swagger middleware will be automatically configured appropiately within our project. One of the advatages of this is when we run our Web Api project interectively we'll be able to test our web Api code through our browsers even before we've developed any front-end code. So the basic UI will automatically be created for this purpose for us. When we run our application interectevly we'll be able  to test each of our action methods through the relavent automatically created web based UI. 04:17- 05:52*

*We are going to build our database using code first migrations & entity framework core [2]. Migration allow us to evolve our database without using data or database object. So by using plain all C# classes we can build the database entites that we wish to include within our Shopping Cart Application. Once we've created relavent entity related C# classes we're look at an entity relationship diagram that represent our shopping cart application database design. 6.16 - 6.43* 

*Create Entities Related C# Clases. This is way the classes that represent out database entities will resign.*

*Entity Relatioship Diagram Link [Visit Here](https://lucid.app/lucidchart/969fa12e-1cb2-49bf-9e2d-3a89accc11ab/edit?viewport_loc=-65%2C-11%2C1707%2C872%2C0_0&invitationId=inv_534ffb26-27c6-4037-99ad-da8d6e9f0aa2#)*

-  Using  ef7 to generate a database for our shopping cart application. The classes that we've just crated representing our entities will be used by ef7 to generate the corresponding database table within the database that ef7 create for us.

-  In order to generate our database with the relavent tables through Visual Studio Let's Install Nuget Packages, `EntityFrameworkCore.SqlServer` `EntityFrameworkCore.Tools` for running migrations within visual studio. The reason for installing `EntityFrameworkCore.Tools` this package is because we want to run our migration with in the visual studio as supposed to using .Net CLI for this purpose. We can use different commands when running migration commands using the .Net CLI. As supposed to the command we run when using Visual Studio.

-  Configuring Connection String in order to connect the application with the database that we wish to create using ef7 code first migrations.

-  Create Database Context Class. So in order to make this class represant our ef7 databse context we need to implement code so that our `ShopOnlineDbContext` Class inherits from ef7 DbContext class. An red sqigly line under `DbContext` this is because we've an important `Microsoft.EntityFramewokCore` Namespace. An easy way to include the appropriate using directive through visual studio is to press `Ctr+Period` & then select the appropriate menu item from the menu that is presented to us through Visual Studio. Let's Create the Constructor for our `ShopOnlineDbContext` Class. We must add a parameter to to the constructor that we've just generated. The parameter is name `Options` & is of the generic type `DbContextOptions` which has the data type `ShopOnlineDbContext` Passed as an argument to it. We can then write code to pass the argument that will be passed to our `ShopOnlineDbContext` Class Constructor to the base class from which Inherit IE. the DbContext class. Now because We want to focus on the shopping cart workflow at the stage & don't want us to distructed by the implementation of administrative CRUD operation functionality. We are going to seed our database with certain data. This is data that we already prepared. So we're not going to include Create Read Update & delete Funtionality regarding the creation & maintenance of product data. At the stage we are going to seed our database with product related data. We're going to seed our database with the relavent data so that we can move directly to the creation of our shopping cart functionality. So in order to seed database appropriately wen can override a method that exist  within a

-  OnModelCreating Method Overriding

-  Using Entity Framework Core DbSet Generic Type 

-  Register ShopOnlineDbContext class for Dependency Injection

-  Generate To Migration Using EF Core

-  To run migration type update-database Command in PM console Window.

-  Check SSMS 19 Prev 2.

- `Retrieving Product data from database & Returning data to client blazor component`

- [Diagram](https://lucid.app/lucidchart/4715f825-77f7-4867-bf6d-0b9c9961cf0f/edit?viewport_loc=-10%2C-11%2C1707%2C872%2C0_0&invitationId=inv_02814206-a40a-4c94-9087-ab773e457b69#) 

- `Develop Web API Component`

- `Create Data Transfer Object (DTO) Model` This type of model includes the data that needs to be passed between server & client. So a DTO is an object that defines how the data will be send over the network. Because that represant our entities that we create earlier directly maped to our crrespondent database table. This classes represant the structure of certain tables in our database. We can create `DTOS` data transfer objects that are based on the underline entity classes. but may be differntly shaped based on the data we needs to be passed between client & server. Now we create a standard library project to house of `dtos`.

- `Create ShopOnline.Model Class Library` for creating the classes that have representingour dtos.

- `Coding The Logic for first workflow` Starting with the web api component. This workflow simply involved retrieving product data from our database & returning the data to the client blazor application. The blazor application will contain code that displays the relavent product data to the user. So ShopOnlineDbContext class has been registered for dependency injection. We'll see in a bit how we are able to implement code to ensure that an object of type ShopOnlineDbContext is injected into relavent classes.

- `Repository design Pattern Implementation to abstract data handling layout` Repositories are classes or components that incapsulate the logic required to access data Sources. We can use repositories to centralized common data access funtinality. Which has the benefit of facilitating beta maintainbility easier Unit Testing, extensibility & Cleaner Code. The best way to Understand the repository pattern is to Implement the relavent code. So lets write the code for Product repository Funtionality.

- Create Interface that runs asyncronusly, Overturn Generic tasks objects. Our first method is named get items & returns an `IEnumerable` Collection of type product. So a IEnumerable collection is passed as a type argument to the task object as discussed this is so the method implement this method defination can runs asycronusly.

- Now we've define the interface that we want to class name ProductRepository to implement. So lets create a class directly with in the repository directory named product repository & the first things we need to do is write the code to implement the `IProductRepository` Interface. 

- Visual Studio generates the relavent code stuffs for us. So Visual Studio generates default implementations for the rlavent method definations. So in this stage only want to ipmplement the code logic relavent to the web flow that is the focus of this Project. IE returning a collection of product data to the client side calling code in this case our Blazor component. We are going to new to use the ShopOnlineDnContext Object to interect with our ShopOnline Database. As u will recall earlier we registered the ShopOnlineDbContext object for dependency injection. This means that we're able to gain accessed to an object of type ShopOnlineDbContext by defining an appropriate parameterized constructor in our pruduct repository class.

- An Easy way to automaically generate a Constructor within visual studio is type `ctor` & then press the tab key twice. Then in order to indicate to .Net that we want an object of type ShopOnlineDbContext to be injected into this constructor only need to do is difine an parameter with in our constructor of type ShopOnlineDbContext.
  

###  📦 TIPS
---
- `Running Migrations Notes:` if u have one migration or more than one migration & not happy with the changes made to the database u can undo the changes made by running this command `update-database 0` To Remove migration run this command `remove-migration` if you Upadate a database with multiple migrations Like `Migration1 or Migration2 or Migration3 or Migration4 or Migration5`. if u wish to rollback the changes to before a particular migration was run you can Rollback your changes to that particular state by running the migration that was run directly before the migration that back contain the changes you wish to roll back `update-database Migration2`

- `Generating Migration Using ef7` Open NuGet Package Manager Console Window. Follow with this Command `Add-Migration InitiaCreate` ShopOnline Api project Set as Startup Project. By generating this migration class this code generate our database & the relavent table. This method also contain code that seeds the relavent database table with the data that prepared prair to careate in this project.

- `Down` Method contains code to undo the changes made by code contain with the method.


### 🏆  RESEARCH & STUDY

- 1[Database Relationships]`https://www.sqlshack.com/learn-sql-types-of-relations/``https://code.tutsplus.com/articles/sql-for-beginners-part-3-database-relationships--net-8561` `https://www.tutorialsteacher.com/sqlserver/tables-relations`

- 2[Tutorial: Get Started with Entity Framework 6 Code First using MVC 5](https://docs.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)

- 3[ ASP.NET MVC 5.2.3 Beta](https://docs.microsoft.com/en-us/aspnet/mvc/)

- 4[WebAssembly 1.0 ](https://webassembly.org/)

- 5[C# 11 Preview documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)

- 6[awesome-blazor, Resources for Blazor, a .NET web framework using C#/Razor and HTML that runs in the browser with WebAssembly.](https://github.com/AdrienTorris/awesome-blazor)

- 7[Blazor University](https://blazor-university.com/)

- 8[https://blazor-university.com/](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oUJCA3DCzKT79Oe3kdKEceX)

- [Data Transfer Object (DTO)](https://docs.microsoft.com/en-us/aspnet/web-api/overview/data/using-web-api-with-entity-framework/part-5)(https://stackoverflow.com/questions/1051182/what-is-a-data-transfer-object-dto)

- 9[Constructors (C# programming guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors)

- 10[The C# type system](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)

- 11[Objects - create instances of types](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/objects)

- 12[Methods](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods)

- 13[Passing Parameters (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)

- 14[Access Modifiers (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)

- 15[Dependency injection in .NET](https://docs.microsoft.com/en-us/dotnet/core/extensions/dependency-injection)

- 16[Dependency injection in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-6.0)

- 17[Server-side website programming](https://developer.mozilla.org/en-US/docs/Learn/Server-side)

- 18[HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

- 19[SPA (Single-page application)](https://developer.mozilla.org/en-US/docs/Glossary/SPA)

- 20[Open Api](https://www.openapis.org/)

- 21[ASP.NET Core Middleware](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/middleware/?view=aspnetcore-6.0)

- 22[WEB Api](https://www.geeksforgeeks.org/what-is-web-api-and-why-we-use-it/)

- 23[Strings and string literals](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)

- 24[Integral numeric types (C# reference)](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types)

- 25[Microsoft identity platform documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/)

- 26[Properties (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties)

- 27[ASP.NET Identity](https://docs.microsoft.com/en-us/aspnet/identity/)

- 28[.NET CLI overview](https://docs.microsoft.com/en-us/dotnet/core/tools/)

- 29[Connection Strings](https://docs.microsoft.com/en-us/ef/core/miscellaneous/connection-strings)

- 30[DbContext Class](https://docs.microsoft.com/en-us/dotnet/api/system.data.entity.dbcontext?view=entity-framework-6.2.0, https://docs.microsoft.com/en-us/ef/ef6/fundamentals/working-with-dbcontext)

- 31[using (C# Reference)](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/using)

- 32[Inheritance in C# and .NET](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/tutorials/inheritance)

- 33[Generic type parameters (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/generic-type-parameters, https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/generics)

- 34[Passing Parameters (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)

- 35[C# Keywords](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/)

- 36[C# programming guide](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/)

- 37[C# reference](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/)

- 38[Creating and configuring a model](https://docs.microsoft.com/en-us/ef/core/modeling/)

- 39[Data Seeding](https://docs.microsoft.com/en-us/ef/core/modeling/data-seeding)

### QA
---
- Problem: Add-Migration InitialCreate Not Working `Could not load assembly 'ShopOnline.Web'. Ensure it is referenced by the startup project 'ShopOnline.Api'.`
- Solution: `https://www.thecodebuzz.com/build-failed-efcore-scaffold-dbcontext-command-pmc/`

- Problem: `Add-Migration InitialCreate
Build started...
Build failed.`
- Solution: Open ShopOnlineDbContext.cs file Then Check the code & find the error. Two error found at UserName. Open User.cs Entities. Correct the int to string type.

- [Q]  Why We Use Migrations?
- [A]  ```Migration Allow us to evolve our database without loosing data or database object.```
