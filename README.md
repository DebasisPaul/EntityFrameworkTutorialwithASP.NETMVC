### SOS
---
- `(Very Basic ) Shopping Cart Application/Shop Online Solution With Blazor Web Assembly & Web Api with Payment gateway powered by PayPal `


### START
---
`Blazor Web Assembly is a Single page app framework for building interective client side web apps with dot net. It uses open Web standard without plugin or recompiling code into other languages. This Course will teach you how to use balzor web assembly & web api on .Net 7 . You will Learn step by step how to build a shopping Cart Application. This Course also provide the guide on how to intigrate a payment gateway into your blazor web Assembly component so that a user able to pay for products through your application using a debit or credit card or in the paypal account.`

### SOS Technologies
---
1. [Visual Studio 2022 version 17.2.3 (Enterprise Preview)](https://visualstudio.microsoft.com/vs/preview/) `https://docs.microsoft.com/en-us/visualstudio/releases/2022/release-notes`
2. [.Net 7 Prev 5](https://devblogs.microsoft.com/dotnet/dotnet-7-generic-math/)
3. [SQL Server 2022 (16.x) Preview community technology preview (CTP) 2.0.](https://docs.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16)
4. [Blazor WebAssembly V2](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-6.0)
5. [Bootstrap v5.2](https://getbootstrap.com/) for layout & styling purposes.
6. [ASP.NET 4.x RESTful MVC Web API 2](https://docs.microsoft.com/en-us/aspnet/web-api/) for handling database related funtionality & returning relavent data from the server to our client side blazor application.
7. [PayPal Payment Gateway](https://developer.paypal.com/api/nvp-soap/payflow/payflow-gateway/) so that a user can use their paypal acoount or a valid debit or credit card to pay for the items that all purchased through our online shopping cart application.
8. [POSTMAN](https://www.postman.com/)
9. [Build database Using Entitity Framework Core 6 Code First Migration](https://docs.microsoft.com/en-us/aspnet/entity-framework)

`Blazor is a relatively new feature of asp dot net. It offers two hosting model. A server side hosting model &  a client side hosting model. We are going to use the client side hosting model for the development of our shopping cart application. The significanse of this hosting model is that the C# code runs directly within our browsers. What makes this possible is a technology named Web Assembly. In recent years the creation of SPA applications or single page applications have become very popular as web solutions. Recently Javascript frameworks like Angular or React have been the avilable choices for the creation of spa applications. With Blazor we are now able to create our single page applications using C#. We don't necessaryly need to depend on  javascript for the creation of our interective UI Code.
We can create this code using C#. In this appliaction however the payment gateway provided by paypal is coded in javascript. So we will use blazor into our probality funtionality with javascript to interect with the relavent javascript paypal code.`

### SOS Part-1 (Build Started)
---

-  Create Blazor Web Assembly Solution
-  Create Rest ful Web Api Project
-  Create Entities Related C# Clases
-  Entity Relatioship Diagram Link [Visit Here](https://lucid.app/lucidchart/969fa12e-1cb2-49bf-9e2d-3a89accc11ab/edit?viewport_loc=-65%2C-11%2C1707%2C872%2C0_0&invitationId=inv_534ffb26-27c6-4037-99ad-da8d6e9f0aa2#)
-  Insall Nuget Packages
-  Configuring Connection String
-  Create Database Context
-  OnModelCreating Method Overriding
-  Using Entity Framework Core DbSet Generic Type 
-  Register ShopOnlineDbContext class for Dependency Injection
-  Generate To Migration Using EF Core
-  update-database
-  Check SSMS 19 Prev.

### Part-2 (Dediacted To building a SOS Using Blazor & Rest ful Web Api)
---
- Retrieving Product data from database & Returning data to client blazor component
- [Diagram](https://lucid.app/lucidchart/4715f825-77f7-4867-bf6d-0b9c9961cf0f/edit?viewport_loc=-10%2C-11%2C1707%2C872%2C0_0&invitationId=inv_02814206-a40a-4c94-9087-ab773e457b69#) 
- Develop Web API Component
- Create Data Transfer Object (DTO)
- Create ShopOnline.Model Class Library.
- coding The Logic for first workflow.
- Repository design Pattern Implementation to abstract data handling layout.
- Create Interface that runs asyncronusly, overturn Generic tasks objects. returns an IEnumerable Collection of type.



### QA
---
- Problem: Add-Migration InitialCreate Not Working `Could not load assembly 'ShopOnline.Web'. Ensure it is referenced by the startup project 'ShopOnline.Api'.`
- Solution: `https://www.thecodebuzz.com/build-failed-efcore-scaffold-dbcontext-command-pmc/`

- Problem: `Add-Migration InitialCreate
Build started...
Build failed.`
- Solution: Open ShopOnlineDbContext.cs file Then Check the code & find the error. Two error found at UserName. Open User.cs Entities. Correct the int to string type.

- [Q]  Why We Use Migrations?
- [A]  Migration Allow us to evolve our database without loosing data or database object.

### TIPS
---
- Running Migrations Notes: if u have one migration or more than one migration & not happy with the changes made to the database u can undo the changes made by running this command `update-database 0` To Remove migration run this command `remove-migration` if you Upadate a database with multiple migrations Like Migration1 or Migration2 or Migration3 or Migration4 or Migration5. if u wish to rollback the changes to before a particular migration was run you can Rollback your changes to that particular state by running the migration that was run directly before the migration that back contain the changes you wish to roll back `update-database Migration2`

### RESEARCH 
- [Database Relationships]`https://www.sqlshack.com/learn-sql-types-of-relations/``https://code.tutsplus.com/articles/sql-for-beginners-part-3-database-relationships--net-8561` `https://www.tutorialsteacher.com/sqlserver/tables-relations`
- [Tutorial: Get Started with Entity Framework 6 Code First using MVC 5](https://docs.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)
- [ ASP.NET MVC 5.2.3 Beta](https://docs.microsoft.com/en-us/aspnet/mvc/)
