# Enterprise module (C# branch)

### ASP.NET Core, WCF

#### What Is the difference between .NET Core and .NET Standard? How do they relate to “classic” .NET?

The .NET Standard is a formal specification of .NET APIs that are intended to be available on all .NET implementations.
.NET Core is a free and open-source, managed computer software framework for Windows, Linux, and macOS operating systems.

#### What is ASP.NET MVC?

It is a web application framework.
Based on ASP.NET, ASP.NET MVC allows software developers to build a web application as a composition of three roles: Model, View and Controller. The MVC model defines web applications with 3 logic layers:

- Model (business layer)
- View (display layer)
- Controller (input control)

#### Can you explain Model, Controller and View in MVC?

A Model represents an object, or a data carrier. It can also hold logic for updating the controller.
A View represents the visualization of said data and logic.
The Controller acts on both model and view, by controlling the data flow into model objects and updating the view whenever said data changes.
It also keeps the view and model separate.

#### Explain the page lifecycle of MVC.

- An instance of the RouteTable class is created on application start. This happens only once when the application is requested for the first time.

- The UrlRoutingModule intercepts each request, finds a matching RouteData from a RouteTable and instantiates a MVCHandler (an HttpHandler).

- The MVCHandler creates a DefaultControllerFactory (you can create your own controller factory also). It processes the RequestContext and gets a specific controller (from the controllers you have written). Creates a ControllerContext, the controller a ControllerContext and executes the controller.

- Gets the ActionMethod from the RouteData based on the URL. The Controller Class then builds a list of parameters (to to the ActionMethod) from the request.

- The ActionMethod returns an instance of a class inherited from the ActionResult class and the View Engine renders a view as a web page.

#### What is Razor View Engine?

Razor View engine is a markup syntax which helps us to write HTML and server-side code in web pages using C# or VB.NET. It is server-side markup language however it is not at all a programming language.
Razor is a templating engine and ASP.NET MVC has implemented a view engine which allows us to use Razor inside of an MVC application to produce HTML. However, Razor does not have any ties with ASP.NET MVC.
Now, Razor Syntax is compact which minimizes the characters to be used, however it is also easy to learn.

#### What do you mean by Routing in MVC?

ASP.NET introduced Routing to eliminate needs of mapping each URL with a physical file. Routing enable us to define URL pattern that maps to the request handler.

[Routing in MVC](https://www.tutorialsteacher.com/mvc/routing-in-mvc)

#### What is Layout in MVC?

Usually a layout is a common view pattern which can be inherited by other views. For example, a header and a footer.

#### What ConfigureServices() method does in Startup.cs?

It configures the app's services, which are reusable components that provide functionality.
Services are registered within ConfigureServices and consumed accross the app via dependency injection, or
Application Services.

- Optional
- Called by the host before the Configure() method, to configure services.
- Where configuration options are set by convention.

#### What Configure() method does in Startup.cs?

It is used to specify how the app responds to HTTP requests. The request pipeline is configured by adding middleware
components to an IApplicationBuilder instance. IApplicationBuilder is available to the Configure method, but it isn't
registered in the service container. Hosting creates said Builder and passes it to Configure.
Most services are not available until the Configure method is called.

[Startup Class](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/startup?view=aspnetcore-3.1)

#### What is wwwroot folder in ASP.NET Core?

By default, the wwwroot folder in the ASP.NET Core project is treated as a web root folder. Static files can be stored in any folder under the web root and accessed with a relative path to that root.
In the standard ASP.NET application, static files can be served from the root folder of an application or any other folder under it. This has been changed in ASP.NET Core. Now, only those files that are in the web root - wwwroot folder can be served over an http request. All other files are blocked and cannot be served by default.

[WWWRoots](https://www.tutorialsteacher.com/core/aspnet-core-wwwroot)

#### What’s the usage of [InternalsVisibleTo] attribute? What are pros and cons of it?

It makes visible the internal methods of an assembly to the test project. This allows you to test
those internal methods without using reflection, so your tests are more maintainable.

Pros:

- Allows your test libraries to access internal classes and methods for additional testing and coverage
- Keeps your public API limited to what you want to publish
- Provides greater flexibility for internal refactoring and backwards compatibility
- Reduces the surface area of your public API

Cons:

- Easily abused, so things usually marked “private” are now marked “internal”
- Potential loss of encapsulation
- Decision about what should be public could be wrong
- Essentially two levels of “public” visibility that have to be managed
- Enforces bi-directional dependencies between assemblies

#### Explain what is WCF?

Windows Communication Foundation (WCF) is a framework for building service-oriented applications.
Using WCF, you can send data as asynchronous messages from one service endpoint to another.
A service endpoint can be part of a continuously available service hosted by IIS, or it can be a service hosted in an application.
An endpoint can be a client of a service that requests data from a service endpoint.
The messages can be as simple as a single character or word sent as XML, or as complex as a stream of binary data.

[WCF Wiki](https://en.wikipedia.org/wiki/Windows_Communication_Foundation)<br>
[Ms Docs](https://docs.microsoft.com/en-us/dotnet/framework/wcf/whats-wcf)

#### Mention what is the endpoint in WCF and what are the three major points in WCF?

Endpoint:

- Messages are sent between endpoints. Endpoints are places where messages are sent or received (or both), and they define all the information required for the message exchange.
  A service exposes one or more application endpoints (as well as zero or more infrastructure endpoints).
  A service can expose this information in the form of metadata that clients process to generate the appropriate WCF clients and communication stacks.
  When needed, the client generates an endpoint that is compatible with one of the service's endpoints.
  A WCF service endpoint has an address, a binding, and a service contract (sometimes referred to as WCF ABCs).

Three Major Points:

- Address: Specifies the location of the service, which the clients will use to communicate with

- Binding: Specifies the communication properties such as data transport, encoding, protocols

- Contract: The interface specification between client and server.

[Points](https://subscription.packtpub.com/book/application_development/9781784391041/1/ch01lvl1sec08/the-basic-wcf-concepts)<br>
[Ms Docs](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts)

### Object Relational Mapping, Entity Framework

#### What is an ORM? What are benefits, when to use?

ORM - Object Relational Mapping, is a programming technique for converting data between incompatible type systems using object-oriented programming languages.
This creates, in effect, a "virtual object database" that can be used from within the programming language. There are both free and commercial packages available that perform object-relational mapping, although some programmers opt to construct their own ORM tools.

Entity Framework (EF) is an open source[3] object-relational mapping (ORM) framework for ADO.NET. It was a part of .NET Framework, but since Entity framework version 6 it is separated from .NET framework.

EF Core can serve as an object-relational mapper (O/RM), enabling .NET developers to work with a database using .NET objects, and eliminating the need for most of the data-access code they usually need to write.

[EF](https://en.wikipedia.org/wiki/Entity_Framework)<br>
[Ms Docs](https://docs.microsoft.com/en-us/ef/#pivot=entityfmwk&panel=entityfmwk1)

#### What is Entity Framework? What are the advantages, limitations?

For the first part, see above.

Code First:

- Easier for a software developer
- Can use all EF features
- EF migrations can be difficult
- Can't access all SQL features

Database First:

- Easy for a software developer
- Creates poor entity classes
- Can't use all EF features

SQL First:

- Can use all EF and SQL features
- Easy to update / use
- Developer needs to know SQL

EF:

- Steep learning curve
- Great payoff
- Convenience features

[Adv-Disadv SO](https://stackoverflow.com/questions/8793590/ef-codefirst-advantages-and-disadvantages)<br>
[Model-Code-DB First](https://forums.asp.net/t/1789430.aspx?what+are+advantages+in+model+first+and+code+first+as+compare+to+Database+First+approach+in+EF+)<br>
[Pros and Cons](https://www.thereformedprogrammer.net/ef-core-taking-full-control-of-the-database-schema/)

#### What is lazy loading?

Lazy loading is the delaying of related data, until it is specifically requested. It is the opposite of eager loading.

[Lazy Loading](https://www.tutorialspoint.com/entity_framework/entity_framework_lazy_loading.htm)

#### What is the difference between code first and DB first approach?

Code First:

- Very popular because hardcore programmers don't like any kind of designers and defining mapping in EDMX xml is too complex.
- Full control over the code (no autogenerated code which is hard to modify).
- General expectation is that you do not bother with DB. DB is just a storage with no logic. EF will handle creation and you don't want to know how it does the job.
- Manual changes to database will be most probably lost because your code defines the database.

Database First:

- Very popular if you have DB designed by DBAs, developed separately or if you have existing DB.
- You will let EF create entities for you and after modification of mapping you will generate POCO entities.
- If you want additional features in POCO entities you must either modify template or use partial classes.
- Manual changes to the database are possible because the database defines your domain model. You can always update model from database.

[Adv-Disadv SO](https://stackoverflow.com/questions/8793590/ef-codefirst-advantages-and-disadvantages)<br>
[Differing Approaches](https://stackoverflow.com/questions/5446316/code-first-vs-model-database-first)<br>
[POCO](https://stackoverflow.com/questions/16075245/what-is-poco-in-entity-framework)

#### What is a migration script?

It is a script that contains relevant migration data, changes and updates made to the database schema.
A migration script provides a way for developers to change a data model and change it in a database without the loss of data.

[Ms Docs Migrations](https://docs.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli)

#### What is a navigation property?

Navigation properties provide a way to navigate an association between two entity types. Every object can have a navigation property for every relationship in which it participates.
Navigation properties allow you to navigate and manage relationships in both directions, returning either a reference object (if the multiplicity is either one or zero-or-one) or a collection (if the multiplicity is many).
You may also choose to have one-way navigation, in which case you define the navigation property on only one of the types that participates in the relationship and not on both.

[Ms Docs - Relationships in EF](https://docs.microsoft.com/en-us/ef/ef6/fundamentals/relationships)

#### Name 3 different attributes used in EF Core, what can they do for you?

ForeignKey, Key, TimeStamp, Required, MaxLength, NotMapped
