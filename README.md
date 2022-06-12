### 🧰 SOS
---
Shop Online Web
- `(Very Basic ) Shopping Cart Application/Shop Online Solution With Blazor Web Assembly & Web Api, Integrated with Payment gateway & powered by PayPal `
<img src="https://th.bing.com/th/id/R.291544c41c4e3a6a542f3f121001f63e?rik=nAC9%2bKfzsXG8GA&pid=ImgRaw&r=0" style="width:1200px;height:500px;">

### 🙌 START
---
`Blazor Web Assembly is a Single page app framework for building interective client side web apps with dot net. It uses open Web standard without plugin or recompiling code into other languages. This Course will teach you how to use balzor web assembly & web api on .Net 7 . You will Learn step by step how to build a shopping Cart Application. This Course also provide the guide on how to intigrate a payment gateway into your blazor web Assembly component so that a user able to pay for products through your application using a debit or credit card or in the paypal account.`

### SOS Technologies
| Logo | Technologies | 
| ----------- | ----------- |
|<img src="https://th.bing.com/th/id/OIP.V-EXykC2eWn7fHqPslAl2wHaHX?pid=ImgDet&rs=1" style="width:50px;height:50px;">|[Visual Studio 2022 version 17.2.3 (Enterprise Preview)](https://visualstudio.microsoft.com/vs/preview/) `https://docs.microsoft.com/en-us/visualstudio/releases/2022/release-notes`|
|<img src="https://th.bing.com/th/id/R.3d6504d22dce42b5f9c6cdd19c4f5c0b?rik=l4CnmJIt2wpQlw&pid=ImgRaw&r=0" style="width:50px;height:50px;">|[.Net 7 Prev 5](https://devblogs.microsoft.com/dotnet/dotnet-7-generic-math/)|
||[SQL Server 2022 (16.x) Preview community technology preview (CTP) 2.0.](https://docs.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16)||
|<img src="https://www.rlogical.com/wp-content/uploads/2020/10/Blazor.png" style="width:50px;height:50px;">|[Blazor WebAssembly](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-6.0) |
||[Bootstrap v5.2](https://getbootstrap.com/) for layout & styling purposes.|
| <img src="https://th.bing.com/th/id/OIP.v3itvY2BcYOwgZJNGfRFJwHaHa?pid=ImgDet&rs=1" style="width:50px;height:50px;">|[ASP.NET 4.x RESTful MVC Web API 2](https://docs.microsoft.com/en-us/aspnet/web-api/)  for handling database related funtionality & returning relavent data from the server to our client side blazor application.|
||[PayPal Payment Gateway](https://developer.paypal.com/api/nvp-soap/payflow/payflow-gateway/) so that a user can use their paypal acoount or a valid debit or credit card to pay for the items that all purchased through our online shopping cart application.|
|| [POSTMAN](https://www.postman.com/) To test web api funtionality.|
|<img src="https://th.bing.com/th/id/R.01e6f07f9add7f088c61cc86f3b8c9b2?rik=tleE7%2fpICszi%2fw&pid=ImgRaw&r=0" style="width:50px;height:50px;">|[Build database Using Entity Framework 7 Preview 4 Code First Migration](https://docs.microsoft.com/en-us/aspnet/entity-framework)|

`Blazor is a relatively new feature of asp dot net. It offers two hosting model. A server side hosting model &  a client side hosting model. We are going to use the client side hosting model for the development of our shopping cart application. The significanse of this hosting model is that the C# code runs directly within our browsers. What makes this possible is a technology named Web Assembly. In recent years the creation of SPA applications or single page applications have become very popular as web solutions. Recently Javascript frameworks like Angular or React have been the avilable choices for the creation of spa applications. With Blazor we are now able to create our single page applications using C#. We don't necessaryly need to depend on  javascript for the creation of our interective UI Code.
We can create this code using C#. In this appliaction however the payment gateway provided by paypal is coded in javascript. So we will use blazor into our probality funtionality with javascript to interect with the relavent javascript paypal code.`

### SOS Part-1 (Build Started)
---
-  Create Blazor Web Assembly Solution
-  Create Rest ful Web Api Project
-  Create Entities Related C# Clases. This is way the classes that represent out database entities will resign.
-  Entity Relatioship Diagram Link [Visit Here](https://lucid.app/lucidchart/969fa12e-1cb2-49bf-9e2d-3a89accc11ab/edit?viewport_loc=-65%2C-11%2C1707%2C872%2C0_0&invitationId=inv_534ffb26-27c6-4037-99ad-da8d6e9f0aa2#)
-  Using  ef7 to generate a database for our shopping cart application. The classes that we've just crated representing our entities will be used by ef7 to generate the corresponding database table within the database the ef7 create for us.
-  Insall Nuget Packages, `EntityFrameworkCore.SqlServer` `EntityFrameworkCore.Tools` for running migrations within visual studio.
-  Configuring Connection String in order to connect the application with the database that to create using ef7 code first migrations.
-  Create Database Context Class.
-  OnModelCreating Method Overriding
-  Using Entity Framework Core DbSet Generic Type 
-  Register ShopOnlineDbContext class for Dependency Injection
-  Generate To Migration Using EF Core
-  To run migration type update-database Command in PM console Window.
-  Check SSMS 19 Prev 2.

### SOS Part-2
---
- `Retrieving Product data from database & Returning data to client blazor component`

- [Diagram](https://lucid.app/lucidchart/4715f825-77f7-4867-bf6d-0b9c9961cf0f/edit?viewport_loc=-10%2C-11%2C1707%2C872%2C0_0&invitationId=inv_02814206-a40a-4c94-9087-ab773e457b69#) 

- `Develop Web API Component`

- `Create Data Transfer Object (DTO) Model` This type of model includes the data that needs to be passed between server & client. So a DTO is an object that defines how the data will be send over the network. Because that represant our entities that we create earlier directly maped to our crrespondent database table. This classes represant the structure of certain tables in our database. We can create `DTOS` data transfer objects that are based on the underline entity classes. but may be differntly shaped based on the data we needs to be passed between client & server. Now we create a standard library project to house of `dtos`.

- `Create ShopOnline.Model Class Library` for creating the classes that have representingour dtos.

- `Coding The Logic for first workflow` Starting with the web api component. This workflow simply involved retrieving product data from our database & returning the data to the client blazor application. The blazor application will contain code that displays the relavent product data to the user. So ShopOnlineDbContext class has been registered for dependency injection. We'll see in a bit how we are able to implement code to ensure that an object of type ShopOnlineDbContext is injected into relavent classes.

- `Repository design Pattern Implementation to abstract data handling layout` Repositories are classes or components that incapsulate the logic required to access data Sources. We can use repositories to centralized common data access funtinality. Which has the benefit of facilitating beta maintainbility easier Unit Testing, extensibility & Cleaner Code. The best way to Understand the repository pattern is to Implement the relavent code. So lets write the code for Product repository Funtionality.

- Create Interface that runs asyncronusly, Overturn Generic tasks objects. Our first method is named get items & returns an `IEnumerable` Collection of type product. So a IEnumerable collection is passed as a type argument to the tast object as discussed this is so the method implement this method defination can runs asycronusly.

- Now we've define the interface that we want to class name ProductRepository to implement. So lets create a class directly with in the repository directory named product repository & the first things we need to do is write the code to implement the `IProductRepository` Interface. 

- Visual Studio generates the relavent code stuffs for us. So Visual Studio generates default implementations for the rlavent method definations. So in this stage only want to ipmplement the code logic relavent to the web flow that is the focus of this Project. IE returning a collection of product data to the client side calling code in this case our Blazor component. We are going to new to use the ShopOnlineDnContext Object to interect with our ShopOnline Database. As u will recall earlier we registered the ShopOnlineDbContext object for dependency injection. This means that we're able to gain accessed to an object of type ShopOnlineDbContext by defining an appropriate parameterized constructor in our pruduct repository class.

- An Easy way to automaically generate a Constructor within visual studio is type `ctor` & then press the tab key twice. Then in order to indicate to .Net that we want an object of type ShopOnlineDbContext to be injected into this constructor only need to do is difine an parameter with in our constructor of type ShopOnlineDbContext.
  

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

###  📦 TIPS
---
- `Running Migrations Notes:` if u have one migration or more than one migration & not happy with the changes made to the database u can undo the changes made by running this command `update-database 0` To Remove migration run this command `remove-migration` if you Upadate a database with multiple migrations Like `Migration1 or Migration2 or Migration3 or Migration4 or Migration5`. if u wish to rollback the changes to before a particular migration was run you can Rollback your changes to that particular state by running the migration that was run directly before the migration that back contain the changes you wish to roll back `update-database Migration2`

- `Enable Open API Support:` by doing this the `Swashbuckle.AspNetCore` nuget package will be automatically installed And the appropriate Swaggwer middleware will be automatically configured appropriately with in our project. One of the advantage of this is when wen we run our web api project interectevly we eill be able to test our web api code through our browsers even before we've developed any front-end code. so a basic UI will automatically be created for this purpose for us. When we run Our application interectevly we be able to test each of action method through the relavent automatically cerated web based UI. 
 
- We are going to build our database using code first migrations & entity framework core. migration allow us to evolve our database without using data or database object. So by using plain all C# classes we can build the database entites that we wish to include within our Shopping Cart Application. Once we've created relavent entity related C# classes we're look at an entity related diagram that represent our shooping cart application database design. 

- `Generating Migration Using ef7` Open NuGet Package Manager Console Window. Follow with this Command `Add-Migration InitiaCreate` ShopOnline Api project Set as Startup Project. By generating this migration class this code generate our database & the relavent table. This method also contain code that seeds the relavent database table with the data that prepared prair to careate in this project.

- `Down` Method contains code to undo the changes made by code contain with the method.


### 🏆  RESEARCH 
- [Database Relationships]`https://www.sqlshack.com/learn-sql-types-of-relations/``https://code.tutsplus.com/articles/sql-for-beginners-part-3-database-relationships--net-8561` `https://www.tutorialsteacher.com/sqlserver/tables-relations`
- [Tutorial: Get Started with Entity Framework 6 Code First using MVC 5](https://docs.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)
- [ ASP.NET MVC 5.2.3 Beta](https://docs.microsoft.com/en-us/aspnet/mvc/)
- [WebAssembly 1.0 ](https://webassembly.org/)
- [C# 11 Preview documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)
- [awesome-blazor, Resources for Blazor, a .NET web framework using C#/Razor and HTML that runs in the browser with WebAssembly.](https://github.com/AdrienTorris/awesome-blazor)
- [Blazor University](https://blazor-university.com/)
- [https://blazor-university.com/](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oUJCA3DCzKT79Oe3kdKEceX)
- [Data Transfer Object (DTO)](https://docs.microsoft.com/en-us/aspnet/web-api/overview/data/using-web-api-with-entity-framework/part-5)(https://stackoverflow.com/questions/1051182/what-is-a-data-transfer-object-dto)
- [Constructors (C# programming guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors)
- [The C# type system](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)
- [Objects - create instances of types](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/objects)
- [Methods](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods)
- [Passing Parameters (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)
- [Access Modifiers (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)
- [Dependency injection in .NET](https://docs.microsoft.com/en-us/dotnet/core/extensions/dependency-injection)
- [Dependency injection in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-6.0)

# 👀 Business Enquiry

```Email 
debasispaul@outlook.in 
debasispaul@outlook.com
```
## 🚀 Contribution

Do you want to contribute? Check out our []() page to learn more about contribution and guidelines.

## 🌍 Roadmap

Read what we [plan for next iterations](), and feel free to ask questions.

Check out our [Wiki Page]) to learn more about updating your NuGet sources in Visual Studio, then you can also get pre-release packages of upcoming versions to try.

## 📄 Code of Conduct

This project has adopted the code of conduct defined by the [Contributor Covenant](http://contributor-covenant.org/) to clarify expected behavior in our community.
For more information see the []().

## 🏆 Contributors

Made with [DebasisPaul](https://sites.google.com/view/debasispaul).
