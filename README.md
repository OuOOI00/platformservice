This is a small backend project I built to learn how microservices talk to each other.
It's a simple REST API for managing a list of "platforms" (just items with a name, publisher, and cost) . Data is stored in SQL Server using Entity Framework Core

When a new platform is created, the service also:
sends an event to RabbitMQ (so other services can react without waiting)
exposes the same data through gRPC, so other services can read it quickly

I wanted to try more than just plain REST so I added gRPC and RabbitMQ too, just to understand the difference between them
Tech I used: C#, ASP.NET Core, Entity Framework Core, SQL Server, AutoMapper, RabbitMQ, gRPC

How to run it:
1. Start SQL Server and RabbitMQ, update the connection strings in appsettings.json
2. Run `dotnet ef database update`
3. Run `dotnet run`

This was the first time I used gRPC and RabbitMQ so it took some time to figure out how they actually work. It's still a learning project not something production-ready . I want to add tests and Docker later
