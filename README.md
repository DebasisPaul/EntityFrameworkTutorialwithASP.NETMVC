# SOS


# Course In Details

#### Blazor Web Assembly is a Single page app framework for building interective client side web app with dot net. It used open standard without plugin or recompiling code into other languages. This Course will teach you how to balzor web assembly & web api on .Net 7 Prev. You will teach step by step how to build shopping Cart Application. This Course also provide the guide on how to intigrate a payment gateway into your blazor web Assembly component so that a user able to pay for products through your application using a debit or credit card or in the paypal account. Debasis Paul Teaches this course. Debasis is Software Developer Architect with over the years of experience.

# SCA
Shopping Cart Application With Blazor Web Assembly with Payment gateway.

# Technologies

1. Visual Studio Enterprise 2022 Prev
2. .Net 7 Prev
3. Sql Server 2022
4. Blazor WebAssembly
5. Bootstrap v5
6. REST ful MVC Web API
7. POSTMAN
8. Entitity Framework Core Code First Migration
9. Entity Relatioship Diagram Link [Visit Here](https://lucid.app/lucidchart/969fa12e-1cb2-49bf-9e2d-3a89accc11ab/edit?viewport_loc=-65%2C-11%2C1707%2C872%2C0_0&invitationId=inv_534ffb26-27c6-4037-99ad-da8d6e9f0aa2#)

# QA

- Problem: Add-Migration InitialCreate Not Working `Could not load assembly 'ShopOnline.Web'. Ensure it is referenced by the startup project 'ShopOnline.Api'.`
- Solution: `https://www.thecodebuzz.com/build-failed-efcore-scaffold-dbcontext-command-pmc/`

- Problem: `Add-Migration InitialCreate
Build started...
Build failed.`
- Solution: Open ShopOnlineDbContext.cs file Then Check the code & find the error. Two error found at UserName. Open User.cs Entities. Correct the int to string type.

# Part-1 (Initial SetUp)

-  Introduction
-  Tools
-  What is Blazor Web Assembly?
-  Create Blazor Project
-  Create Web Api Project
-  Create Entities
-  Create Connection String
-  Insall Nuget Packages
-  Create Database Context
-  OnModelCreating Method Overriding
-  Using Entity Framework Core DbSet Generic Type 
-  Register ShopOnlineDbContext class for Dependency Injection
-  Generate To Migration Using EF Core
-  update-database
-  Check SSMS 19 Prev.
-  Running Migrations Notes: if u have one migration or more than one migration & not happy with the changes made to the database u can undo the changes made by running this command `update-database 0` To Remove migration run this command `remove-migration` if you Upadate a database with multiple migrations Like Migration1 or Migration2 or Migration3 or Migration4 or Migration5. if u wish to rollback the changes to before a particular migration was run you can Rollback your changes to that particular state by running the migration that was run directly before the migration that back contain the changes you wish to roll back `update-database Migration2`

# Part-2 (Focus on building SCA Using Blazor WebAssembly & Rest ful Web Api)
- Retrieving Product data from database & Returning data to client blazor component
- [Diagram](https://lucid.app/lucidchart/4715f825-77f7-4867-bf6d-0b9c9961cf0f/edit?viewport_loc=-10%2C-11%2C1707%2C872%2C0_0&invitationId=inv_02814206-a40a-4c94-9087-ab773e457b69#) 
- Develop Web API Component
- Crete Data Transfer Object (DTO)
- Create ShopOnline.Model Claaa Library.
