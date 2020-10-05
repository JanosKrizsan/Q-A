# General enterprise questions

## Software engineering

### Architectures

#### What is n-tier (or multi-tier) architecture?

N-tier architecture is also called multi-tier architecture because the software is engineered to have the processing, data management, and presentation functions physically and logically separated.  
That means that these different functions are hosted on several machines or clusters, ensuring that services are provided without resources being shared and, as such, these services are delivered at top capacity.  
The “N” in the name n-tier architecture refers to any number from 1.
Not only does your software gain from being able to get services at the best possible rate, but it’s also easier to manage.  
This is because when you work on one section, the changes you make will not affect the other functions.  
And if there is a problem, you can easily pinpoint where it originates.

[N-Tier](https://stackify.com/n-tier-architecture/)

#### What are microservices? Advantages and disadvantages?

Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are:<br>

- Highly maintainable and testable
- Loosely coupled
- Independently deployable
- Organized around business capabilities
- Owned by a small team

The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications.
It also enables an organization to evolve its technology stack.

Pros:<br>

- Improved fault isolation
- Eliminate vendor or technology lock-in
- Ease of understanding
- Smaller and faster development
- Scalability

Cons:<br>

- Communication between services is complex
- More services equals more resources
- Global testing is difficult
- Debugging problems can be harder
- Deployment challanges
- Large vs small product companies

[Microservices](https://microservices.io/)<br>
[Primer](https://cloudacademy.com/blog/microservices-architecture-challenge-advantage-drawback/)

#### What is Separation of Concerns?

A design principle for separating a computer program into distinct sections such that each section addresses a separate concern.
A concern is a set of information that affects the code of a computer program.

[Example](https://softwareengineering.stackexchange.com/questions/32581/how-do-you-explain-separation-of-concerns-to-others)

#### What is a layered design and why is it important in enterprise applications?

A layered pattern architecture organizes a system into a set of layers each of which provide a set of services to the layer “above”.
Some of the layers of a general information system are as follows:

- Presentation layer: It’s also known as UI layer.
- Application layer: It’s also known as service layer.
- Business logic layer: It’s also known as domain layer.
- Data access layer: It’s also known as persistence layer.

It is mainly used for general desktop applications and ecommerce web applications.

It is characterised by:

- A loosely coupled system
- Teams can work on different layers, in parrallel, with minimal dependencies on other teams
- Changes to any layer in terms of technology or business logic have little impact on other layers
- Testing can be performed easily

[Architectural Patterns](https://www.topcoder.com/architectural-patterns-to-consider-for-building-enterprise-applications/)<br>
[Why?](https://subscription.packtpub.com/book/application_development/9781786468888/6/ch06lvl1sec40/layers-in-layered-architecture)

#### What is Dependency Injection?

Dependency Injection is passing dependency to other objects or framework(dependency injector).
It makes testing easier, and can be done via a constructor.

It can also be done via setters, or interfaces which the class must implement in order for the dependencies to be injected.

[SO Example](https://stackoverflow.com/questions/130794/what-is-dependency-injection)<br>
[Interface Example](https://stackify.com/dependency-injection/)

#### What is the DAO pattern? When and how to implement?

It is the Data Access Object pattern.

Following are the participants in Data Access Object Pattern:

- Data Access Object Interface - This interface defines the standard operations to be performed on a model object(s).
- Data Access Object concrete class - This class implements above interface. This class is responsible to get data from a data source which can be database / xml or any other storage mechanism.
- Model Object or Value Object - This object is simple POJO containing get/set methods to store data retrieved using DAO class.

The functionality of this API is to hide from the application all the complexities involved in performing CRUD operations in the underlying storage mechanism.
This permits both layers to evolve separately without knowing anything about each other.

[DAO TutorialsPoint](https://www.tutorialspoint.com/design_pattern/data_access_object_pattern.htm)<br>
[DAO Why and How](https://www.baeldung.com/java-dao-pattern)

#### What is SOA? When to use?

Service-oriented architecture (SOA) is a style of software design where services are provided to the other components by application components, through a communication protocol over a network.
The basic principles of service-oriented architecture are independent of vendors, products and technologies.
A service is a discrete unit of functionality that can be accessed remotely and acted upon and updated independently, such as retrieving a credit card statement online.

A service has four properties according to one of many definitions of SOA:

- It logically represents a business activity with a specified outcome.
- It is self-contained.
- It is a black box for its consumers.
- It may consist of other underlying services.

[SOA Wiki](https://en.wikipedia.org/wiki/Service-oriented_architecture)<br>
[SOA DZone](https://dzone.com/refcardz/soa-patterns?chapter=1)

### Testing

#### What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?

Unit Test:<br>
It focuses on the smallest unit of a software design. In this we test an individual unit or group of inter related units.
It is often done by a programmer by using sample input and observing its corresponding outputs.

Integration Test:<br>
The objective is to take unit tested components and build a program structure that has been dictated by design.
Integration testing is testing in which a group of components are combined to produce the output.
Integration testing is of four types: Top down, Bottom up, Sandwich, Big-Bang

System Test:<br>
In this, software is tested on the basis that it works fine for different operating systems.
It is covered under the black box testing technique.
In this we just focus on the required inputs and outputs without focusing on any internal working.
In this we have security testing, recovery testing , stress testing and performance testing

Regression Test:<br>
Every time a new module leads to changes in a program.
This type of testing makes sure that the whole component works properly even after new additions to the complete program.

Acceptance Test:<br>
Acceptance Testing is a method of software testing where a program is tested for acceptability.
The major aim of this test is to evaluate the compliance of the application with the business requirements and assess whether it is acceptable for delivery or not.
Acceptance Testing is the last phase of software testing performed after System Testing and before making the system available for actual use.

[Testing](https://hackr.io/blog/types-of-software-testing)

#### What is code coverage? Why is it used? How you can measure?

Code coverage is a measurement of how many lines/blocks/arcs of your code are executed while the automated tests are running.
Code coverage is collected by using a specialized tool to instrument the binaries to add tracing calls and run a full set of automated tests against the instrumented product.<br>
A good tool will give you not only the percentage of the code that is executed, but also will allow you to drill into the data and see exactly which lines of code were executed during a particular test.

[CC](https://stackoverflow.com/questions/195008/what-is-code-coverage-and-how-do-you-measure-it)<br>
[Calculation](https://www.atlassian.com/continuous-delivery/software-testing/code-coverage)

#### What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?

Mocking is make a replica or imitation of something.<br>
We use mocking in unit testing. A object that you want to test may have dependencies on other complex objects. To isolate the behavior of the object you want to test you replace the other objects by mocks that simulate the behavior of the real objects.
So in simple words, mocking is creating objects that simulate the behavior of real objects.

In unit testing we want to test methods of one class in isolation. But classes are not isolated.<br>
They are using services and methods from other classes. So in that situation, we mock the services and methods from other classes and simulate the real behavior of them using some mocking frameworks and use that mocked methods and services to do unit testing in isolation.
This is where Mocking frameworks come into play.

[Mocking](https://medium.com/@piraveenaparalogarajah/what-is-mocking-in-testing-d4b0f2dbe20a)

#### What is a test case? What is an assertion? Give examples!

A test case is, in other words, a unit of testing wherein we test a certain behaviour our code generates, throws etc.

An assertion is the expected and produced outcome of our test case, which either could be false or true (fail or pass).

For a very easy example, we could test if 3 \* 3 equals 9. If our method NumByNum(3, 3) includes a line which adds +1 to the outcome,
and returns that, then our assertion will fail. The assertion and it's parent, the test case shows us that there is something amiss in
our function.

#### What is TDD? What are the benefits?

TDD is test-driver-development.<br>
Test-driven development (TDD) is a software development process that relies on the repetition of a very short development cycle: requirements are turned into very specific test cases, then the software is improved so that the tests pass.
This is opposed to software development that allows software to be added that is not proven to meet requirements.

Benefits:

- Acceptance criteria
- Focus
- Tidier code
- Integration
- Dependencies
- Safer refactoring
- Fewer bugs
- Increased returns
- Living documentation

[Benefits](https://www.madetech.com/blog/9-benefits-of-test-driven-development)

#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

How should they be?

- Fast
- Isolated
- Repeatable
- Self-Checking
- Timely

What are the best practices?

- Naming: name of the method being tested, the scenario, the expected behaviour
- Arrange, Act, Assert: arrange your objects by creating and setting them up, act on an object, assert that something is as expected
- Minimally Passing
- Avoid Magic Strings
- Avoid Logic
- Prefer Helper Methods for Setup and Teardown
- Avoid Multiple Asserts
- Validate Private by Unit Testing Public
- Stub Static References

[Best](https://dzone.com/articles/unit-testing-best-practices-how-to-get-the-most-ou)<br>
[Practices](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices)

#### What is arrange/act/assert pattern?

Please see above.

### DevOps

#### What is continuous integration? Why is CI important?

Continuous Integration is a software development practice where members of a team integrate their work frequently, usually each person integrates at least daily - leading to multiple integrations per day.
Each integration is verified by an automated build (including test) to detect integration errors as quickly as possible.
Many teams find that this approach leads to significantly reduced integration problems and allows a team to develop cohesive software more rapidly.
This article is a quick overview of Continuous Integration summarizing the technique and its current usage.

[CI Summary](https://martinfowler.com/articles/continuousIntegration.html)<br>
[Primer](https://www.thoughtworks.com/continuous-integration)

#### Why are tests important in the CI workflow?

- Developers check out code into their private workspaces
- When done, commit the changes to the repository
- The CI server monitors the repository and checks out changes when they occur
- The CI server builds the system and runs unit and integration tests
- The CI server releases deployable artefacts for testing
- The CI server assigns a build label to the version of the code it just built
- The CI server informs the team of the successful build
- If the build or tests fail, the CI server alerts the team
- The team fixes the issue at the earliest opportunity
- Continue to continually integrate and test throughout the project

Tests are the wall of defence between a non-functional and functional build. A bad test, thus, could break features or the whole application.

#### Name some software that help the CI workflow!

Jenkins, Travis, TeamCity, CircleCI, CodeShip, Gitlab CI

[Tools](https://stackify.com/top-continuous-integration-tools/)

#### What is Continuous Delivery?

Continuous Delivery is the ability to get changes of all types—including new features, configuration changes, bug fixes and experiments—into production, or into the hands of users, safely and quickly in a sustainable way.

Our goal is to make deployments—whether of a large-scale distributed system, a complex production environment, an embedded system, or an app—predictable, routine affairs that can be performed on demand.

We achieve all this by ensuring our code is always in a deployable state, even in the face of teams of thousands of developers making changes on a daily basis. We thus completely eliminate the integration, testing and hardening phases that traditionally followed “dev complete”, as well as code freezes.

[CD](https://continuousdelivery.com/)

#### What is Continuous Deployment?

Continuous deployment is a strategy for software releases wherein any code commit that passes the automated testing phase is automatically released into the production environment, making changes that are visible to the software's users.
Continuous deployment eliminates the human safeguards against unproven code in live software.
It should only be implemented when the development and IT teams rigorously adhere to production-ready development practices and thorough testing, and when they apply sophisticated, real-time monitoring in production to discover any issues with new releases.

[CD](https://searchitoperations.techtarget.com/definition/continuous-deployment)

#### What is DevOps?

DevOps is a set of practices that automates the processes between software development and IT teams, in order that they can build, test, and release software faster and more reliably. The concept of DevOps is founded on building a culture of collaboration between teams that historically functioned in relative siloes.
The promised benefits include increased trust, faster software releases, ability to solve critical issues quickly, and better manage unplanned work.

DevOps is a set of practices that combines software development (Dev) and information-technology operations (Ops) which aims to shorten the systems development life cycle and provide continuous delivery with high software quality.

[DevOps](https://en.wikipedia.org/wiki/DevOps)

### Software Methodologies

#### What kind of software-lifecycle models do you know?

Waterfall, Agile

[Models](https://existek.com/blog/sdlc-models/)

#### What is a UML diagram? What kind of diagram types do you know?

UML (Unified Modeling Language) is a standard language for specifying, visualizing, constructing, and documenting the artifacts of software systems.
UML was created by the Object Management Group (OMG) and UML 1.0 specification draft was proposed to the OMG in January 1997.
It was initially started to capture the behavior of complex software and non-software system and now it has become an OMG standard.

Object, Class, Deployment, Component Diagram

[UML Tutorial](https://www.tutorialspoint.com/uml/index.htm)

#### What is a UML class diagram? What are the typical elements?

Class diagram is a static diagram. It represents the static view of an application.
Class diagram is not only used for visualizing, describing, and documenting different aspects of a system but also for constructing executable code of the software application.
Class diagram describes the attributes and operations of a class and also the constraints imposed on the system.
The class diagrams are widely used in the modeling of objectoriented systems because they are the only UML diagrams, which can be mapped directly with object-oriented languages.
Class diagram shows a collection of classes, interfaces, associations, collaborations, and constraints. It is also known as a structural diagram.

#### What kind of design patterns do you know? Bring at least 3 examples.

Singleton, Abstract Factory, Object Pool, Prototype, Facade

[Meme Site about Patterns](https://medium.com/educative/the-7-most-important-software-design-patterns-d60e546afb0e)<br>
[Good Site](https://sourcemaking.com/design_patterns)

#### What is the purpose of the Iterator Pattern?

Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
The C++ and Java standard library abstraction that makes it possible to decouple collection classes and algorithms.
Promote to "full object status" the traversal of a collection.
Polymorphic traversal

[Iterator](https://sourcemaking.com/design_patterns/iterator)

#### What do you know about the SOLID principles?

- Single Responsibility Principle
- Open-Close Principle
- Liskov Substitution Principle
- Interface Segregation Principle
- Dependency Inversion Principle

[SOLID Wiki](https://en.wikipedia.org/wiki/SOLID)<br>
[More SOLID](https://itnext.io/solid-principles-explanation-and-examples-715b975dcad4)

#### How would you separate data storage code and business logic code (which uses stored data) in an application?

I would separate them to a Logic Tier and a Database Tier, most likely on top of that would be a Presentation Tier which would
take care of the visualisation of said data. The Logic tear would communicate with the Presentation and Database, but these two would not
be able to directly access one another. The Logic would be a bridge of sorts. Of course, to me, it would mean a different folder and file
structure as well, with on-point and descriptive naming of classes and methods, fields, properties. Depending on the data stored, the Database is
just an example.

## Computer science

### Data Structures

#### What is the difference between Stack and Queue data structure?

Stack:<br>
A stack is a linear data structure in which elements can be inserted and deleted only from one side of the list, called the top.
A stack follows the LIFO (Last In First Out) principle, i.e., the element inserted at the last is the first element to come out.
The insertion of an element into a stack is called a push operation, and deletion of an element from the stack is called a pop operation.
In a stack we always keep track of the last element present in the list with a pointer called top.

Queue:<br>
A queue is a linear data structure in which elements can only be inserted from one side of the list called the rear, and the elements can only be deleted from the other side called the front.
The queue data structure follows the FIFO (First In First Out) principle, i.e. the element inserted at first into the list, is the first element to be removed from the list.
The insertion of an element in a queue is called an enqueue operation and the deletion of an element is called a dequeue operation.
In a queue we always maintain two pointers, one pointing to the element which was inserted at the first and still present in the list with the front pointer and the second pointer pointing to the element inserted at the last with the rear pointer.

#### What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?

Graph:<br>
A graph is a structure amounting to a set of objects in which some pairs of the objects are in some sense "related".
The objects correspond to mathematical abstractions called vertices (also called nodes or points) and each of the related pairs of vertices is called an edge (also called link or line).
Typically, a graph is depicted in diagrammatic form as a set of dots or circles for the vertices, joined by lines or curves for the edges.
Graphs are one of the objects of study in discrete mathematics.

Simple Graph:<br>
A graph (sometimes called undirected graph for distinguishing from a directed graph, or simple graph for distinguishing from a multigraph).

Directed Graph:<br>
A directed graph or digraph is a graph in which edges have orientations.

Weighted Graph:<br>
A weighted graph or a network is a graph in which a number (the weight) is assigned to each edge. Such weights might represent for example costs, lengths or capacities, depending on the problem at hand.
Such graphs arise in many contexts, for example in shortest path problems such as the traveling salesman problem.

[Graphs](<https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)>)

#### What are trees? What are binary trees? What are binary search trees?

Tree:<br>
A tree is an undirected graph in which any two vertices are connected by exactly one path, or equivalently a connected acyclic undirected graph.
A forest is an undirected graph in which any two vertices are connected by at most one path, or equivalently an acyclic undirected graph, or equivalently a disjoint union of trees.

Binary Tree:<br>
A binary tree is a tree data structure in which each node has at most two children, which are referred to as the left child and the right child.
A recursive definition using just set theory notions is that a (non-empty) binary tree is a tuple.

Binary Search Tree:

[Tree](<https://en.wikipedia.org/wiki/Tree_(graph_theory)>)<br>
[Binary Tree](https://en.wikipedia.org/wiki/Binary_tree)<br>
[Binary Search Tree](https://en.wikipedia.org/wiki/Binary_search_tree)

#### How can you store graphs in programs? What are the advantages/disadvantages per each?

[Graph Primer](https://ijarcce.com/upload/2016/june-16/IJARCCE%2057.pdf)

#### What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?

Graph traversal means visiting all the nodes of the graph.
A structured system is required by many application of
graph to examine the vertices and edges of a graph. There
are two graph traversal methods as follows:

1. Breadth First Search (BFS)
2. Depth First Search (DFS)

BFS:<br>
an algorithm for traversing or searching tree or graph data structures.
It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key'), and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

DFS:<br>
An algorithm for traversing or searching tree or graph data structures.
The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

[BFS](https://en.wikipedia.org/wiki/Breadth-first_search)<br>
[DFS](https://en.wikipedia.org/wiki/Depth-first_search)

#### How does dictionary work?

A dictionary is a general-purpose data structure for storing a group of objects. A dictionary has a set of keys and each key has a single associated value. When presented with a key, the dictionary will return the associated value.
A dictionary is also called a hash, a map, a hashmap in different programming languages (and an Object in JavaScript). They're all the same thing: a key-value store.

Typically, the keys in a dictionary must be simple types (such as integers or strings) while the values can be of any type. Different languages enforce different type restrictions on keys and values in a dictionary. Dictionaries are often implemented as hash tables.
Keys in a dictionary must be unique; an attempt to create a duplicate key will typically overwrite the existing value for that key.
Note that there is a difference (which may be important) between a key not existing in a dictionary, and the key existing but with its corresponding value being null.

#### Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)

If immutable, the object's hashcode wont change and it allows caching the hashcode of different keys which makes the overall retrieval process very fast.
Also for mutable objects ,the hashCode() might be dependent on fields that could change, if this happens you wont be able to find the key (and its value) in the HashMap since hashCode() returns different value.

### Algorithms

#### What is QuickSort? Describe the main logic of this sorting algorithm.

Quicksort (sometimes called partition-exchange sort) is an efficient sorting algorithm, serving as a systematic method for placing the elements of a random access file or an array in order.

- Pick an element, a pivot, from the array.
- Partitioning: reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it (equal values can go either way). After this partitioning, the pivot is in its final position. This is called the partition operation.
- Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.

[QuickSort](https://en.wikipedia.org/wiki/Quicksort)

## Software design

### Security

#### What is OAuth2?

The OAuth 2.0 authorization framework enables a third-party
application to obtain limited access to an HTTP service, either on
behalf of a resource owner by orchestrating an approval interaction
between the resource owner and the HTTP service, or by allowing the
third-party application to obtain access on its own behalf. This
specification replaces and obsoletes the OAuth 1.0 protocol described
in RFC 5849.

[OAuth2.0](https://tools.ietf.org/html/rfc6749)

#### What is Basic Authentication?

Basic authentication is a simple authentication scheme built into the HTTP protocol.
The client sends HTTP requests with the Authorization header that contains the word Basic word followed by a space and a base64-encoded string username:password.
For example, to authorize as demo / p@55w0rd the client would send

[Basic Auth](https://swagger.io/docs/specification/authentication/basic-authentication/)<br>
[Baisc Auth IBM](https://www.ibm.com/support/knowledgecenter/en/SSGMCP_5.1.0/com.ibm.cics.ts.internet.doc/topics/dfhtl2a.html)

#### What is CORS, why it’s needed in browsers?

Cross-Origin Resource Sharing (CORS) is a mechanism that uses additional HTTP headers to tell browsers to give a web application running at one origin, access to selected resources from a different origin.
A web application executes a cross-origin HTTP request when it requests a resource that has a different origin (domain, protocol, or port) from its own.

[CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)<br>
[CORS Wiki](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)

#### How can you initialize a CSRF attack?

Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request.
With a little help of social engineering (such as sending a link via email or chat), an attacker may trick the users of a web application into executing actions of the attacker's choosing.
If the victim is a normal user, a successful CSRF attack can force the user to perform state changing requests like transferring funds, changing their email address, and so forth.
If the victim is an administrative account, CSRF can compromise the entire web application.

[CSRF](<https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)>)<br>
[Visual Guide](https://portswigger.net/web-security/csrf)<br>
[Guide](https://www.veracode.com/security/csrf)

#### What is JWT used for? Where to store it on client side?

JSON Web Token:<br>
JWT is a great technology for API authentication and server-to-server authorization.
A JWT technically is a mechanism to verify the owner of some JSON data.
It’s an encoded string, which is URL safe, that can contain an unlimited amount of data (unlike a cookie), and it’s cryptographically signed.
When a server receives a JWT, it can guarantee the data it contains can be trusted because it’s signed by the source. No middleman can modify a JWT once it’s sent.

Regular Web App:<br>
ID Tokens, Access Tokens, and (optional) Refresh Tokens should be handled server-side in typical web applications.
The application server uses the tokens to call APIs on behalf of the user.

Single Page Apps:<br>
If your single-page app has a backend server at all, then tokens should be handled server-side.

If you have a single-page app (SPA) with no corresponding backend server, your SPA should request new tokens on login and store them in memory without any persistence.
To make API calls, your SPA would then use the in-memory copy of the token.

Under certain circumstances, you can use cookies to authenticate a single-page application:

- if your SPA is served to the client using your own backend
- if your SPA has the same domain as your backend
- if your SPA makes API calls that require authentication to your backend

[Tokens](https://auth0.com/docs/security/store-tokens)

### Threaded programming

#### When do you need to use threads in an application?

If you have too many threads the processor will spend all its time generating and switching between them.
Use too few threads you will not get the throughput you want in your application. Additionally using threads is not easy.
A language like C# makes it easier on you because you have tools like ThreadPool.QueueUserWorkItem.
This allows the system to manage thread creation and destruction. This helps mitigate the overhead of creating a new thread to pass the work onto. You have to remember that the creation of a thread is not an operation that you get for "free."
There are costs associated with starting a thread so that should always be taken into consideration.
Depending upon the language you are using to write your application you will dictate how much you need to worry about using threads.

The times I find most often that I need to consider creating threads explicitly are:<br>

- Asynchronous operations
- Operations that can be parallelized
- Continual running background operations

#### What is a daemon thread?

Java offers two types of threads: user threads and daemon threads.
User threads are high-priority threads. The JVM will wait for any user thread to complete its task before terminating it.
On the other hand, daemon threads are low-priority threads whose only role is to provide services to user threads.

#### What is the difference between concurrent and parallel execution of code?

Concurrency and parallelism are two related but distinct concepts.

Concurrency means, essentially, that task A and task B both need to happen independently of each other, and A starts running, and then B starts before A is finished.

There are various different ways of accomplishing concurrency. One of them is parallelism--having multiple CPUs working on the different tasks at the same time.
But that's not the only way. Another is by task switching, which works like this: Task A works up to a certain point, then the CPU working on it stops and switches over to task B, works on it for a while, and then switches back to task A.
If the time slices are small enough, it may appear to the user that both things are being run in parallel, even though they're actually being processed in serial by a multitasking CPU.

#### What is the most important problem developers are faced when using threads?

Threads may die in the background, throw and exception which remains to be seen or heard about. There is also a phenomenon of deadlock, where an application comes to a stop
upon waiting for a resource. Threads may increasy complexity and time and space complexity needlessly, thus we need to substantiate their usage well.

[Problems Arisen](https://www.tutorialspoint.com/major-issues-with-multi-threaded-programs)

#### In what kind of situations can deadlocks occur?

In an operating system, a deadlock occurs when a process or thread enters a waiting state because a requested system resource is held by another waiting process, which in turn is waiting for another resource held by another waiting process.
If a process is unable to change its state indefinitely because the resources requested by it are being used by another waiting process, then the system is said to be in a deadlock.

#### What are possible ways to prevent deadlocks from occurring?

- Removing the mutual exclusion condition
- The hold and wait
- The no preemption condition
- Circular wait condition

[Prevention](https://en.wikipedia.org/wiki/Deadlock#Prevention)

#### What does critical section or critical region mean in the context of concurrent programming?

In concurrent programming, concurrent accesses to shared resources can lead to unexpected or erroneous behavior, so parts of the program where the shared resource is accessed need to be protected in ways that avoid the concurrent access.
This protected section is the critical section or critical region. It cannot be executed by more than one process at a time.
Typically, the critical section accesses a shared resource, such as a data structure, a peripheral device, or a network connection, that would not operate correctly in the context of multiple concurrent accesses.
