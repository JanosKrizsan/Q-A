# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
Use consistent and descriptive identifiers and names.
Make judicious use of white space and indentation to make code easier to read.
Store ISO-8601 compliant time and date information (YYYY-MM-DD HH:MM:SS.SSSSS).
Try to use only standard SQL functions instead of vendor specific functions for reasons of portability.
Keep code succinct and devoid of redundant SQL—such as unnecessary quoting or parentheses or WHERE clauses that can otherwise be derived.


[SQL Style Guide](https://www.sqlstyle.guide/)

#### What layers can you name in a simple web application?
- Client, Application, Database
OR
- View, Business Logic, Data layers

[3 Tier](https://searchsoftwarequality.techtarget.com/definition/3-tier-application)<br>
[5 Layer](https://morphological.wordpress.com/2011/08/29/5-layer-architecture/)

### Error handling

#### What error can occur, when an array does not have an element on the requested index?
IndexError, undefined is returned.

#### What is the “finally” block, and how would you use it?
It is the ending block of the try-except-finally exception handling method. It is used to define a block of code
which will always run, not matter what happens within the previous blocks.

#### Why should we catch special exception types?
To better, or to guide user experience or ease the debugging process.

### Security

#### What is SQL injection? How to protect an application against it?
SQL injection is a code injection technique, used to attack data-driven applications, in which malicious SQL statements are inserted into an entry field for execution (e.g. to dump the database contents to the attacker). SQL injection must exploit a security vulnerability in an application's software, for example, when user input is either incorrectly filtered for string literal escape characters embedded in SQL statements or user input is not strongly typed and unexpectedly executed. SQL injection is mostly known as an attack vector for websites but can be used to attack any type of SQL database.

SQL injection attacks allow attackers to spoof identity, tamper with existing data, cause repudiation issues such as voiding transactions or changing balances, allow the complete disclosure of all data on the system, destroy the data or make it otherwise unavailable, and become administrators of the database server.

[Preventing SQL Injection](https://www.hacksplaining.com/prevention/sql-injection)

#### What is XSS? How to protect an application against it?
Cross-site scripting (XSS) is a type of computer security vulnerability typically found in web applications. XSS enables attackers to inject client-side scripts into web pages viewed by other users. A cross-site scripting vulnerability may be used by attackers to bypass access controls such as the same-origin policy. Cross-site scripting carried out on websites accounted for roughly 84% of all security vulnerabilities documented by Symantec as of 2007. In 2017, XSS was still considered a major threat vector. XSS effects vary in range from petty nuisance to significant security risk, depending on the sensitivity of the data handled by the vulnerable site and the nature of any security mitigation implemented by the site's owner.

[Ways to Prevent XSS](https://www.checkmarx.com/2017/10/09/3-ways-prevent-xss/)<br>
[HTTP Security Header X-XSS](https://www.keycdn.com/blog/x-xss-protection)

#### How to properly store passwords?
In a hashed and salted format. You do not store the password itself, but the hash+salted key.
Upon authentication the entered password's hash is compared with the stored hash.

#### What is HTTPS?
Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). It is used for secure communication over a computer network, and is widely used on the Internet. In HTTPS, the communication protocol is encrypted using Transport Layer Security (TLS), or, formerly, its predecessor, Secure Sockets Layer (SSL). The protocol is therefore also often referred to as HTTP over TLS, or HTTP over SSL.

The principal motivation for HTTPS is authentication of the accessed website and protection of the privacy and integrity of the exchanged data while in transit. It protects against man-in-the-middle attacks. The bidirectional encryption of communications between a client and server protects against eavesdropping and tampering of the communication. In practice, this provides a reasonable assurance that one is communicating without interference by attackers with the website that one intended to communicate with, as opposed to an impostor.

#### What is encryption and decryption?
Encryption:
In cryptography, encryption is the process of encoding a message or information in such a way that only authorized parties can access it and those who are not authorized cannot. Encryption does not itself prevent interference, but denies the intelligible content to a would-be interceptor. In an encryption scheme, the intended information or message, referred to as plaintext, is encrypted using an encryption algorithm – a cipher – generating ciphertext that can be read only if decrypted. For technical reasons, an encryption scheme usually uses a pseudo-random encryption key generated by an algorithm. It is in principle possible to decrypt the message without possessing the key, but, for a well-designed encryption scheme, considerable computational resources and skills are required. An authorized recipient can easily decrypt the message with the key provided by the originator to recipients but not to unauthorized users.

Decryption:
Decryption is the process of transforming data that has been rendered unreadable through encryption back to its unencrypted form. In decryption, the system extracts and converts the garbled data and transforms it to texts and images that are easily understandable not only by the reader but also by the system. Decryption may be accomplished manually or automatically. It may also be performed with a set of keys or passwords.

#### What is hashing?
Hash algorithms are one way functions. They turn any amount of data into a fixed-length "fingerprint" that cannot be reversed. They also have the property that if the input changes by even a tiny bit, the resulting hash is completely different. This is great for protecting passwords, because we want to store passwords in a form that protects them even if the password file itself is compromised, but at the same time, we need to be able to verify that a user's password is correct.

[Hashing](https://crackstation.net/hashing-security.htm)

#### What is the difference between encryption and hashing? When would you use which?
Hashing is, as shown above, great for comparing data, for example passwords. Encryption could be used to send secretive or highly private information between two parties, where one encrypts and the other decrypts it with their correct key.

#### What encryption methods do you know?
AES, 3DES, Twofish, RSA, Blowfish
64, 128, 256bit

#### What hashing methods do you know?
Hashing with Salt, Key Stretching
YubiHSM, PBKDF2, bycrypt, crypt, SHA256, SHA512, RipeMD, WHIRLPOOL

[Hashing](https://crackstation.net/hashing-security.htm)

#### How/where would you store sensitive data (like db password, API key, ...) of your application?
Password could be stored in an SQL database in hashed and salted form.

You might encrypt your Git repository with `git-remote-gcrypt` for storing API keys, or store it as an environment variable.
[Further on Secret Storage](https://medium.com/poka-techblog/the-best-way-to-store-secrets-in-your-app-is-not-to-store-secrets-in-your-app-308a6807d3ed)

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
Stack is an abstract data type with a bounded(predefined) capacity. It is a simple data structure that allows adding and removing elements in a particular order. Every time an element is added, it goes on the top of the stack and the only element that can be removed is the element that is at the top of the stack, just like a pile of objects.

[Stack](https://www.studytonight.com/data-structures/stack-data-structure)

Queue is also an abstract data type or a linear data structure, just like stack data structure, in which the first element is inserted from one end called the REAR(also called tail), and the removal of existing element takes place from the other end called as FRONT(also called head).

[Queue](https://www.studytonight.com/data-structures/queue-data-structure)

#### What is BubbleSort? Describe the main logic of this sorting algorithm.
Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list, compares adjacent pairs and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. The algorithm, which is a comparison sort, is named for the way smaller or larger elements "bubble" to the top of the list. Although the algorithm is simple, it is too slow and impractical for most problems even when compared to insertion sort. Bubble sort can be practical if the input is in mostly sorted order with some out-of-order elements nearly in position.

[BubbleSort](https://en.wikipedia.org/wiki/Bubble_sort)

#### Explain the process of finding the maximum and minimum value in a list of numbers!
One must iterate through the list at least once. we assign the first element to a variable, to which we compare the rest of the elements. If the next element is greater or lesser than the one assigned, then it is exchanged (depending on whether minimum or maximum is sought). This goes on till the very end of the list, at which we return the value of our variable. It will be either the minimum or maximum of said list.

#### Explain the process of calculating the average value in an array of numbers!
While iterating through the array we must add up each element, and at the same time count them. In the end, we divide the sum of all elements with their number, thus getting the average.

#### What is Big O complexity? Explain time and space complexity!
Big O notation is the way computer scientists describe how long an algorithm will run or how much memory/disk space it will consume. In more proper terms the big O notation describes the time or space complexity of a piece of code based on the input.

When we talk about complexity we express how the growth of some input/condition affects the consumption of some resource. This resource can be either time or memory.

In this regard complexity is a function, its output depends on its input, it represents a rate of growth.

Space complexity is the amount of memory used by the algorithm. We try to answer these two questions:
- At any given time how many elements are in collections or in the memory
- What is the memory footprint of one element in the collection(s) (for example an integer is usually calculated as 4bytes)

Time complexity:
- How many instructions are going to be run?
- How is that going to change if we have a longer input?

#### Explain the process of calculating the average value in a linked list of numbers!
While iterating through the list we must add up each element, and at the same time count them. In the end, we divide the sum of all elements with their number, thus getting the average.

[Linked Lists](https://en.wikipedia.org/wiki/Linked_list)

### Procedural

#### How the CASE condition works in SQL?
The CASE statement goes through conditions and returns a value when the first condition is met (like an IF-THEN-ELSE statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.

#### How the switch-case condition works in JavaScript?
The switch statement evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case, as well as statements in cases that follow the matching case.

[Switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

#### How to achieve a switch-case-like structure in Python?
The Pythonic way to implement switch statement is to use the powerful dictionary mappings, also known as associative arrays, that provide simple one-to-one key-value mappings.

You may be tempted to use a series of if-else-if blocks, using an if condition for each case of your switch statement.
[Switches in Python](https://jaxenter.com/implement-switch-case-statement-python-138315.html)

#### Explain variable scoping in Python!
Scope:
Variables can only reach the area in which they are defined, which is called scope. Think of it as the area of code where variables can be used. Python supports global variables (usable in the entire program) and local variables.

By default, all variables declared in a function are local variables. To access a global variable inside a function, it’s required to explicitly define ‘global variable’.

LEGB:

```
Built-in
    Global
        Enclosed
            Local
```
Variable lifetime:
- Local variables (function parameters) have a lifetime from the start to finish of the function or local scope.
- Global variables live either from module import or start of the program, until the end of the program or till 
they are explicitly deleted.
- Default arguments live from the creation of the function (module imported etc.) until the end of the program.

#### What’s the difference between const and var in JavaScript?
VAR:
The JavaScript variables statement is used to declare a variable and, optionally, we can initialize the value of that variable.

LET:
The let statement declares a local variable in a block scope. It is similar to var, in that we can optionally initialize the variable.

CONST:
Const statement values can be assigned once and they cannot be reassigned. The scope of const statement works similar to let statements.

[Variables of JS](https://dev.to/sarah_chima/var-let-and-const--whats-the-difference-69e)

#### How the list comprehension looks like in Python?
`new_list = [x for in x in list]`
`[x for x in range(10)]`

#### How the “ternary expression” looks like in Python?
`result = value_returned_if_true if boolean_expression else value_returned_if_false`

#### How the ternary expression looks like in JavaScript?
`condition ? exprIfTrue : exprIfFalse`

#### How to import a function from another module in Python?
On the top of the page:
`import module`

Use functions as:
`module.function()`

#### How to import a function from another module in JavaScript?
You can add the "export" keyword before anything to make it importable.
```
export const repeat = function (string){
    return `${string} ${string}`;
};
export function shout(string){
    return `${string.toUpperCase()}!`;
}
```
Then you may use the "import" keyword to use it in another module.
```
import {repeat, shout} from './lib.js';
repeat('hello');
shout('Modules in action');
```

### Functional

#### What is recursion?
Recursion in computer science is a method of solving a problem where the solution depends on solutions to smaller instances of the same problem (as opposed to iteration). The approach can be applied to many types of problems, and recursion is one of the central ideas of computer science.

Most computer programming languages support recursion by allowing a function to call itself from within its own code. Some functional programming languages do not define any looping constructs but rely solely on recursion to repeatedly call code. 

#### Write a recursive function which calculates the Fibonacci numbers!
```
function F(n) {
    if(n == 0) {return 0;}  
    if(n == 1) {return 1;}  
    else {return F(n-1) + F(n-2);
 }}

 def F(n):  
    if n == 0:
        return 0  
    if n == 1:
        return 1  
    else:
        return F(n-1) + F(n-2)
```
#### How to store a function in a variable in Python?
```
def F():
    print("test")

var_mine = F
var_mine()
```

For further info, please see the relevant ProgBasics question.

#### List the ways of defining a callable logical unit in JavaScript!
```
function example(test) {
    return test + test
}

example: function (test) {
    return test + test
}
let myExample = function (test) {return test + test;};

let myExample = test =>  test + test;
```

#### What is an event listener? How to attach one?
The EventListener interface represents an object that can handle an event dispatched by an EventTarget object.

`myElement.addEventListener("event", HandleFunction)`

#### How to trigger an event in JavaScript?
You may use the dispatchEvent() to do so:

Dispatches an Event at the specified EventTarget, (synchronously) invoking the affected EventListeners in the appropriate order. The normal event processing rules (including the capturing and optional bubbling phase) also apply to events dispatched manually with dispatchEvent().

[Create and Trigger Events](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events#Triggering_built-in_events)

#### What is a callback function? Tell some examples of its usage.
In computer programming, a callback function, is any executable code that is passed as an argument to other code that is expected to call back (execute) the argument at a given time.

This execution may be immediate as in a synchronous callback, or it might happen at a later time as in an asynchronous callback. In short, a callback is a function which is not called immediately. It's passed as an argument and called later.

```
console.log('1st log');

setTimeout(function(){
    console.log('3rd log');
}, 500);

console.log('2nd log');
```


#### What is a Python decorator? How does it work? Tell some examples of its usage.
A decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it. Decorators allow us to wrap another function in order to extend the behavior of wrapped function, without permanently modifying it.

In Decorators, functions are taken as the argument into another function and then called inside the wrapper function.

```
@decorator_func
def say_hello():
    print 'Hello'

def say_hello():
    print 'Hello'
say_hello = deocrator_func(say_hello)    
```

[Decorators](https://hackernoon.com/decorators-in-python-8fd0dce93c08)

#### What is the difference between synchronous and asynchronous execution?
When you execute something synchronously, you wait for it to finish before moving on to another task. When you execute something asynchronously, you can move on to another task before it finishes.

[Async Requests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Synchronous_and_Asynchronous_Requests)

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
In the case of PostgreSQL you may connect via the Terminal using specific commands like "psql". In the case of your IDE you might need certain configuration, environmental variables and a language side database adapter to do so. You might also use programs such as pgAdmin to connect to your database.

You may also use psycopg database adapter in cases such as with Python.

[Tutorial on Connection](http://www.postgresqltutorial.com/connect-to-postgresql-database/)<br>
[For Python](http://www.postgresqltutorial.com/postgresql-python/connect/)

#### When do you use the DISTINCT keyword in SQL?
It is used to return only... distinct, or differing values, thus duplicates are not returned.

#### What are aggregate functions in SQL? Give 3 examples.
An aggregate function allows you to perform a calculation on a set of values to return a single scalar value. We often use aggregate functions with the GROUP BY and HAVING clauses of the SELECT statement. Except for COUNT, aggregate functions ignore null values.

Examples:
- AVG – calculates the average of a set of values
- COUNT – counts rows in a specified table or view
- MIN – gets the minimum value in a set of values
- MAX – gets the maximum value in a set of values
- SUM – calculates the sum of values

#### What kind of JOIN types do you know in SQL? Could you give examples?
(INNER) JOIN: Returns records that have matching values in both tables
LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table

```
SELECT ColumnList from LeftTable L
INNER join  RightTable R
ON L.Column=R.Column
```
[For More](https://www.sqlshack.com/sql-join-overview-and-tutorial/)<br>
[PostgreSQL](https://www.postgresql.org/docs/8.3/tutorial-join.html)

#### What are the constraints in sql?
SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.

Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.

The following constraints are commonly used in SQL:

NOT NULL - Ensures that a column cannot have a NULL value
UNIQUE - Ensures that all values in a column are different
PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
FOREIGN KEY - Uniquely identifies a row/record in another table
CHECK - Ensures that all values in a column satisfies a specific condition
DEFAULT - Sets a default value for a column when no value is specified
INDEX - Used to create and retrieve data from the database very quickly

#### What is a cursor in SQL? Why would you use one?
A SQL cursor is a database object which is used to retrieve data from a result set one row at a time. A SQL cursor is used when the data needs to be updated row by row.

In relational databases, operations are made on a set of rows. For example, a SELECT statement returns a set of rows which is called a result set. Sometimes the application logic needs to work with one row at a time rather than the entire result set at once. This can be done using cursors.

In programming, we use a loop like FOR or WHILE to iterate through one item at a time, the cursor follows the same approach and might be preferred because it follows the same logic.

#### What are database indexes? When to use?
A database index allows a query to efficiently retrieve data from a database.  Indexes are related to specific tables and consist of one or more keys.  A table can have more than one index built from it.  The keys are a fancy term for the values we want to look up in the index.  The keys are based on the tables’ columns.  By comparing keys to the index it is possible to find one or more database records with the same value.
Since an index drastically speeds up data retrieval, it is essential the correct indexes are defined for each table. 

Missing indexes won’t be noticed for small databases, but rest assured, once your tables grow in size, queries will take much longer.

[Indexing](https://www.itprotoday.com/sql-server/indexing-dos-and-don-ts)

#### What are database transactions? When to use?
A transaction, in the context of a database, is a logical unit that is independently executed for data retrieval or updates. In relational databases, database transactions must be atomic, consistent, isolated and durable--summarized as the ACID acronym.

A transaction should be used when you need a set of changes to be processed completely to consider the operation complete and valid. In other words, if only a portion executes successfully, will that result in incomplete or invalid data being stored in your database?

For example, if you have an insert followed by an update, what happens if the insert succeeds and the update fails? If that would result in incomplete data (in this case, an orphaned record), you should wrap the two statements in a transaction to get them to complete as a "set".


#### What kind of database relations do you know? How to define them?
- One to One
    A row in table A can have only one matching row in table B, and vice versa.
- One to Many
    A row in table A can have many matching rows in table B, but a row in table B can have only one matching row in table A.
- Many to Many
    A row in table A can have many matching rows in table B, and vice versa.

[Relations](https://database.guide/the-3-types-of-relationships-in-database-design/)

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
```
SELECT * FROM table
WHERE address LIKE '%Miskolc,%';
```
Or

`____, Miskolc%`

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
It can also be done via versioning, soft delete.
You might use an audit trigger function to log the changes.

In PostgreSQL you could also edit the log_statement within your .conf file.
[PostgreSQL AT](http://wiki.postgresql.org/wiki/Audit_trigger)

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
HTML is the HyperText Markup Language, which is designed to create structured documents and provide for semantic meaning behind the documents. HTML5 is the next version of the HTML specification.

XML is the Extensible Markup Language, which provides rules for creating, structuring, and encoding documents. You often see XML being used to store data and to allow for communication between applications. It's programming language-agnostic - all of the major programming languages provide mechanisms for reading and writing XML documents, either as part of the core or in external libraries.

XHTML is an XML-based HTML. It serves the same function as HTML, but with the same rules as XML documents. These rules deal with the structure of the markup.

#### How to include a JavaScript file in a webpage?
`<script src="js/script.js"></script>`

#### How to include a CSS file in a webpage?
`<link href="myCSSfile.css" rel="stylesheet" type="text/css">`

#### How to select an element using its id in CSS?
`#id`

#### How to select elements using their class in CSS?
`.class`

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
`.aplha.beta`

[Selectors](https://css-tricks.com/multiple-class-id-selectors/)

#### How to select all list items in all ordered lists on the page in CSS?
`ol li`

#### How to select elements using their attributes in CSS?
`element[attribute]`
`x[title="test"]`
`[title~="test"]`

#### What are UX and UI?
UX refers to the user experience, while UI refers to user interface.

[Further Info](https://hackernoon.com/what-is-ui-ux-design-1f01e9dbbf02)<br>
[More](https://careerfoundry.com/en/blog/ux-design/the-difference-between-ux-and-ui-design-a-laymans-guide/)

#### Please list some points that an application should fulfill to have good UX.
- Useful
- Usable
- Findable
- Credible
- Desirable
- Accessible
- Valuable

[More](https://www.interaction-design.org/literature/article/the-7-factors-that-influence-user-experience)

#### What is XML, XSLT, DTD?
XML:
Extensible Markup Language (XML) is a markup language that defines a set of rules for encoding documents in a format that is both human-readable and machine-readable. The W3C's XML 1.0 Specification and several other related specifications—all of them free open standards—define XML.

The design goals of XML emphasize simplicity, generality, and usability across the Internet. It is a textual data format with strong support via Unicode for different human languages. Although the design of XML focuses on documents, the language is widely used for the representation of arbitrary data structures such as those used in web services.

Several schema systems exist to aid in the definition of XML-based languages, while programmers have developed many application programming interfaces (APIs) to aid the processing of XML data.

XSLT:
XSLT (eXtensible Stylesheet Language Transformations) is a language for transforming XML documents into other XML documents, or other formats such as HTML for web pages, plain text or XSL Formatting Objects, which may subsequently be converted to other formats, such as PDF, PostScript and PNG. XSLT 1.0 is widely supported in modern web browsers.

The original document is not changed; rather, a new document is created based on the content of an existing one.Typically, input documents are XML files, but anything from which the processor can build an XQuery and XPath Data Model can be used, such as relational database tables or geographical information systems.

Although XSLT is designed as a special-purpose language for XML transformation, the language is Turing-complete, making it theoretically capable of arbitrary computations.

DTD:
A document type definition (DTD) is a set of markup declarations that define a document type for a SGML-family markup language (GML, SGML, XML, HTML).

A DTD defines the valid building blocks of an XML document. It defines the document structure with a list of validated elements and attributes. A DTD can be declared inline inside an XML document, or as an external reference.

XML uses a subset of SGML DTD.

[XSLT](https://en.wikipedia.org/wiki/XSLT)<br>
[XML](https://en.wikipedia.org/wiki/XML)<br>
[DTD](https://en.wikipedia.org/wiki/Document_type_definition)

#### What is the difference between HTML and XML?
HTML VS XML
    1)	HTML is used to display data and focuses on how data looks.	
        XML is a software and hardware independent tool used to transport and store data. It focuses on what data is.
    2)	HTML is the markup language itself.	
        XML provides a framework to define markup languages.
    3)	HTML is not case sensitive.	
        XML is case sensitive.
    4)	HTML is a presentation language.	
        XML is neither a presentation language nor a programming language.
    5)	HTML has its own predefined tags.	
        In XML you can define tags according to your need.
    6)	In HTML, it is not necessary to use a closing tag.	
        XML makes it mandatory to use a closing tag.
    7)	HTML is static because it is used to display data.	
        XML is dynamic because it is used to transport data.
    8)	HTML does not preserve whitespaces.	
        XML preserves whitespaces.

[Further info](https://techdifferences.com/difference-between-xml-and-html.html)

### Javascript

#### What is javascript?
JavaScript is a programming language for the web. It is supported by most web browsers including Chrome, Firefox, Safari, internet Explorer, Edge, Opera, etc. Most mobile browsers for smart phones support JavaScript too.

It is primarily used to enhance web pages to provide for a more user friendly experience. These include dynamically updating web pages, user interface enhancements such as menus and dialog boxes, animations, 2D and 3D graphics, interactive maps, video players, and more. This mode of JavaScript usage in the web browser is also referred to as client-side javascript.

#### When to use AJAX? Bring examples of its usage.
Ajax is a set of web development techniques using many web technologies on the client side to create asynchronous web applications. With Ajax, web applications can send and retrieve data from a server asynchronously (in the background) without interfering with the display and behavior of the existing page. By decoupling the data interchange layer from the presentation layer, Ajax allows web pages and, by extension, web applications, to change content dynamically without the need to reload the entire page. In practice, modern implementations commonly utilize JSON instead of XML.

```
fetch('https://api.github.com/repos/atom/atom')  // set the path; the method is GET by default, but can be modified with a second parameter
.then((response) => response.json())  // parse JSON format into JS object
.then((data) => {
    console.log(data.stargazers_count);
})

$.ajax({
    dataType: "json",
    url: 'https://api.github.com/repos/atom/atom',
    success: function(response) {
        console.log(response['stargazers_count'])
    }
});
```

#### What is DOM and how to manipulate it from Javascript?
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

In JS you may manipulate DOM elements by referring to them in various ways then manipulating their element properties, be they attriubtes, innerHTML etc.

#### What are events and how/why to use them in Javascript?
DOM Events are sent to notify code of interesting things that have taken place. Each event is represented by an object which is based on the Event interface, and may have additional custom fields and/or functions used to get additional information about what happened. Events can represent everything from basic user interactions to automated notifications of things happening in the rendering model.

[Events](https://developer.mozilla.org/en-US/docs/Web/Events)

Events are an easy way through which to change your website, respond to User inputs, increase the UX.

You may refer to events, trigger them or add event listeners (which activate functions upon events of certain DOM elements).

#### What is event bubbling/capturing? How would you use it?
Event flow is the order in which event is received on the web page. If you click on an element like on div or on the button , which is nested to other elements, before the click is performed on the target element. It must trigger the click event each of its parent elements first, starting at the top with the global window object. By default, every element of HTML is child of the window object.

Event Bubbling is that the event starts from the deepest element or target element to its parents, then all its ancestors which are on the way to bottom to top. At present, all the modern browsers have event bubbling as the default way of event flow.

To handle cases where one event has more than one handler, event bubbling concept can be implemented.The major use of event bubbling is the registration of default functions present in the program. In recent times, not many developers use event capturing or bubbling in particular. It is not necessary to implement event bubbling; it may become complicated for the users to keep track of the actions getting executed because of an event.

#### What is JSON and how do we use it?
JSON (JavaScript Object Notation) is a lightweight format that is used for data interchanging. It is based on a subset of JavaScript language (the way objects are built in JavaScript). As stated in the MDN, some JavaScript is not JSON, and some JSON is not JavaScript.

JSON exists as a string — useful when you want to transmit data across a network. It needs to be converted to a native JavaScript object when you want to access the data. This is not a big issue —  JavaScript provides a global JSON object that has methods available for converting between the two.

JSON is purely a data format — it contains only properties, no methods.
JSON requires double quotes to be used around strings and property names. Single quotes are not valid.
Even a single misplaced comma or colon can cause a JSON file to go wrong, and not work. You should be careful to validate any data you are attempting to use (although computer-generated JSON is less likely to include errors, as long as the generator program is working correctly). You can validate JSON using an application like JSONLint.
JSON can actually take the form of any data type that is valid for inclusion inside JSON, not just arrays or objects. So for example, a single string or number would be a valid JSON object.
Unlike in JavaScript code in which object properties may be unquoted, in JSON, only quoted strings may be used as properties.

## Software engineering

### Version control

#### What type of branching strategy would you use?
- Create a development branch.
- Creature feture/... branches off of that dev branch.
- Upon completion merge them back into the development branch.
- Upon completion, testing and reviews merge the development back into master.

#### What would you do if you find a bug on the production code (master branch)?
I would create a new "fix" branch, fix the issue then merge or rebase back the fix branch into the master.

#### How can you move changes from one branch to another in GIT?
You may merge one branch into another.
You can stash the changes, create a new branch and pop them to the new branch from stash.
You could also rebase one branch to another.

#### How does a VCS help with code reviews?
Github like VSC enviornments.
In an environment where multiple people contribute to one project, for example pull requests can increase the
chance of finding bugs in not-yet pushed and finalised commits. Thus, it is potentially able to stop program-breaking changes from entering the code.

#### What is your favorite git command? Why?
`git ls-remote`, convenient way to see all available remote branches.

#### What does remote/local mean in Git? 
It refers to remote/local branches and repositories, and their respective storage locations.

### DevOps

#### Why is it good to use a package manager software?
Without package management, users must ensure that all of the required dependencies for a piece of software are installed and up-to-date, compile the software from the source code (which takes time and introduces compiler-based variations from system to system), and manage configuration for each piece of software. Without package management, application files are located in the standard locations for the system to which the developers are accustomed, regardless of which system they’re using.

[Further info](https://devopedia.org/package-manager)

#### Why is it good to use a virtual environment for a project?
Projects might have differing dependencies. To control for said dependencies it is useful to apply
virtual environments and then install said dependency versions.

[Further info](https://www.geeksforgeeks.org/python-virtual-environment/)

### Networks

#### What kind of HTTP status codes do you know?
1xx (Informational): The request was received, continuing process

2xx (Successful): The request was successfully received, understood and accepted

3xx (Redirection): Further action needs to be taken in order to complete the request

4xx (Client Error): The request contains bad syntax or cannot be fulfilled

5xx (Server Error): The server failed to fulfill an apparently valid request


- 404 - Not Found
- 401 - Unauthorized
- 200 - OK
- 303 - See Other

[HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

#### What is an API?
An application program interface (API) is a set of routines, protocols, and tools for building software applications. Basically, an API specifies how software components should interact. Additionally, APIs are used when programming graphical user interface (GUI) components. A good API makes it easier to develop a program by providing all the building blocks. A programmer then puts the blocks together.


#### What is REST API?
A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.

A RESTful API -- also referred to as a RESTful web service -- is based on representational state transfer (REST) technology, an architectural style and approach to communications often used in web services development.

REST technology is generally preferred to the more robust Simple Object Access Protocol (SOAP) technology because REST leverages less bandwidth, making it more suitable for internet usage. An API for a website is code that allows two software programs to communicate with each another. The API spells out the proper way for a developer to write a program requesting services from an operating system or other application.

#### What is JSON? When to use?
JSON (JavaScript Object Notation) is a lightweight format that is used for data interchanging. It is based on a subset of JavaScript language (the way objects are built in JavaScript). As stated in the MDN, some JavaScript is not JSON, and some JSON is not JavaScript.

An example of where this is used is web services responses. In the 'old' days, web services used XML as their primary data format for transmitting back data, but since JSON appeared (The JSON format is specified in RFC 4627 by Douglas Crockford), it has been the preferred format because it is much more lightweight.

JSON is built on two structures:

- A collection of name/value pairs. In various languages, this is realized as an object, record, struct, dictionary, hash table, keyed list, or associative array.
- An ordered list of values. In most languages, this is realized as an array, vector, list, or sequence.

[JSON Website](http://www.json.org/)

#### What is TCP/IP? What layers does it define, what are they responsible for?
TCP/IP, or the Transmission Control Protocol/Internet Protocol, is a suite of communication protocols used to interconnect network devices on the internet. TCP/IP can also be used as a communications protocol in a private network (an intranet or an extranet).

The entire internet protocol suite -- a set of rules and procedures -- is commonly referred to as TCP/IP, though others are included in the suite.

TCP/IP specifies how data is exchanged over the internet by providing end-to-end communications that identify how it should be broken into packets, addressed, transmitted, routed and received at the destination. TCP/IP requires little central management, and it is designed to make networks reliable, with the ability to recover automatically from the failure of any device on the network.

The two main protocols in the internet protocol suite serve specific functions. TCP defines how applications can create channels of communication across a network. It also manages how a message is assembled into smaller packets before they are then transmitted over the internet and reassembled in the right order at the destination address.

IP defines how to address and route each packet to make sure it reaches the right destination. Each gateway computer on the network checks this IP address to determine where to forward the message.

TCP/IP functionality is divided into four layers, each of which include specific protocols.

- The application layer provides applications with standardized data exchange. Its protocols include the Hypertext Transfer Protocol (HTTP), File Transfer Protocol (FTP), Post Office Protocol 3 (POP3), Simple Mail Transfer Protocol (SMTP) and Simple Network Management Protocol (SNMP).

- The transport layer is responsible for maintaining end-to-end communications across the network. TCP handles communications between hosts and provides flow control, multiplexing and reliability. The transport protocols include TCP and User Datagram Protocol (UDP), which is sometimes used instead of TCP for special purposes.

- The network layer, also called the internet layer, deals with packets and connects independent networks to transport the packets across network boundaries. The network layer protocols are the IP and the Internet Control Message Protocol (ICMP), which is used for error reporting.

- The physical layer consists of protocols that operate only on a link -- the network component that interconnects nodes or hosts in the network. The protocols in this layer include Ethernet for local area networks (LANs) and the Address Resolution Protocol (ARP).

[Difference of TCP/IP and OSI](https://www.geeksforgeeks.org/computer-network-tcpip-model/)<br>
[TCP/IP Layers](https://searchnetworking.techtarget.com/definition/TCP-IP)

#### What’s the difference between TCP and UDP?
TRANSMISSION CONTROL PROTOCOL (TCP):
    - TCP is a connection-oriented protocol. Connection-orientation means that the communicating devices should establish a connection before transmitting data and should close the connection after transmitting the data.
    - TCP is reliable as it guarantees delivery of data to the destination router.
    - TCP provides extensive error checking mechanisms. It is because it provides flow control and acknowledgment of data.
    - Sequencing of data is a feature of Transmission Control Protocol (TCP). this means that packets arrive in-order at the receiver.
    - TCP is comparatively slower than UDP.	
    - Retransmission of lost packets is possible in TCP, but not in UDP.
    - TCP header size is 20 bytes.
    - TCP is heavy-weight.
    - TCP is used by HTTP, HTTPs, FTP, SMTP and Telnet

USER DATAGRAM PROTOCOL (UDP):
    - UDP is the Datagram oriented protocol. This is because there is no overhead for opening a connection, maintaining a connection, and terminating a connection. UDP is efficient for broadcast and multicast type of network transmission.
    - The delivery of data to the destination cannot be guaranteed in UDP.
    - UDP has only the basic error checking mechanism using checksums.
    - There is no sequencing of data in UDP. If ordering is required, it has to be managed by the application layer.
    - UDP is faster, simpler and more efficient than TCP.
    - There is no retransmission of lost packets in User Datagram Protocol (UDP).
    - UDP Header size is 8 bytes.
    - UDP is lightweight.
    - UDP is used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP.

[Comparison](https://www.geeksforgeeks.org/differences-between-tcp-and-udp/)

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
- Method: Get, post etc.
- Request target: URL
- HTTP version
- Headers:
    User-Agent, Accept-Type, Accept-Language, Referer, Accept-Encoding, Host
- Body

[Messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages)<br>
[Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)<br>
[Header List](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
- Status Line:
    Protocol version: HTTP/1.1
    Status code: 202, 404 etc.
    Status text: OK, Not Found etc.
- Headers:
    Vary, Accept-Ranger, Etag, Server, Set-Cookie
- Body

[Messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages)<br>
[Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)<br>
[Header List](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)

#### What is DNS? How does it work?
The Domain Name System (DNS) is a hierarchical and decentralized naming system for computers, services, or other resources connected to the Internet or a private network. It associates various information with domain names assigned to each of the participating entities. Most prominently, it translates more readily memorized domain names to the numerical IP addresses needed for locating and identifying computer services and devices with the underlying network protocols. By providing a worldwide, distributed directory service, the Domain Name System has been an essential component of the functionality of the Internet since 1985.

The process of DNS resolution involves converting a hostname (such as www.example.com) into a computer-friendly IP address (such as 192.168.1.1). An IP address is given to each device on the Internet, and that address is necessary to find the appropriate Internet device - like a street address is used to find a particular home. When a user wants to load a webpage, a translation must occur between what a user types into their web browser (example.com) and the machine-friendly address necessary to locate the example.com webpage.

[DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)
#### What is a web server?
A web server is server software, or hardware dedicated to running said software, that can satisfy World Wide Web client requests. A web server can, in general, contain one or more websites. A web server processes incoming network requests over HTTP and several other related protocols.

The primary function of a web server is to store, process and deliver web pages to clients. The communication between client and server takes place using the Hypertext Transfer Protocol (HTTP). Pages delivered are most frequently HTML documents, which may include images, style sheets and scripts in addition to the text content.

#### Explain the client-server architecture.
Client–server model is a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and service requesters, called clients. Often clients and servers communicate over a computer network on separate hardware, but both client and server may reside in the same system. A server host runs one or more server programs which share their resources with clients. A client does not share any of its resources, but requests a server's content or service function. Clients therefore initiate communication sessions with servers which await incoming requests. Examples of computer applications that use the client–server model are Email, network printing, and the World Wide Web.

Client/server architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection. This system shares computing resources.

Client/server architecture is also known as a networking computing model or client/server network because all the requests and services are delivered over a network.

#### What would you use a session for?
Because HTTP is stateless, in order to associate a request to any other request, you need a way to store user data between HTTP requests. Users logging into their accounts, for example.

#### What would you use a cookie for?
Using the Set-Cookie header field, an HTTP server can pass name/value pairs and associated metadata (called cookies) to a user agent. When the user agent makes subsequent requests to the server, the user agent uses the metadata and other information to determine whether to return the name/value pairs in the Cookie header.

Mainly for session management or to learn more about the way the user interacts with the website, save user preferences and settings, like language and region. Can also use a cookies for authentication and tracking.

[Uses](https://en.wikipedia.org/wiki/HTTP_cookie#Uses)

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
Agile, Waterfall, Prototype, Rapid, Spiral

Agile<br>
    Pros:<br>
        Adaptive approach that responds to changes favorably
        Allows for direct communication to maintain transparency
        Improved quality by finding and fixing defects quickly and identifying expectation mismatches early.
    Cons:<br>
        Focuses on working with software and lacks documentation efficiency
        Chances of getting off-track as outcomes are not clear

Waterfall<br>
    Pros:<br>
        Easy to understand and functional
        Simple enough to handle as model is rigid
        Saves significant amount of time
        Allows for easy testing and analysis
    Cons:<br>
        Only matches precise needs
        Not applicable for maintenance projects
        No option to know possible outcome of a project
        Not excellent for long and ongoing projects

Prototype<br>
    Pros:<br>
        Gives clear idea about the functional process of the software
        Reduces the risk of failure in a software functionality
        Assists well in requirement gathering and the overall analysis
    Cons:<br>
        Chances of extension in management cost
        Excessive involvement of client can affect processing
        Too many changes affect the workflow of the software

Rapid<br>
    Pros:<br>
        Makes the entire development process effortless
        Assists client in taking quick reviews
        Encourages feedback from customers for improvement
    Cons:<br>
        Dependant on the team for performance
        Works on modularized system confined on this methodology
        Requires extremely skilled personnel to handle complexities
        Not applicable for the small budgeted projects

Spiral<br>
    Pros:<br>
        Risk factors are considerably reduced
        Excellent for large and complex projects
        Allows for additional functionality later
        Suitable for highly risky projects with varied business needs
    Cons:<br>
        Costly model in software development
        Failure in risk analysis phase may damage the whole project
        Not appropriate for low-risk projects
        Might get continued and never finish

[Methodologies, 2018](https://acodez.in/12-best-software-development-methodologies-pros-cons/)<br>
[Methodologies, 2018](https://acodez.in/12-best-software-development-methodologies-pros-cons/)<br>
[Methodologies Explained](http://www.itinfo.am/eng/software-development-methodologies/)

#### What are the SCRUM roles?
Product Owner:<br>
    Person with the project vision, breaks down the project into smaller tasks and prioritizes them in order for
    everything to meet the goals of the customer, market and organization.

Scrum Master:<br>
    Helps to make sure the project is following the Scrum framework. Guides, protects and coaches the team, however his responsibility is mainly to the process, not only to the team.

Development Team:<br>
    The developers who execute the project, and work together for the completion of it.

#### What are the SCRUM ceremonies?
- Sprint Backlog Refinement
- Sprint Planning Meeting
- Daily Stand-up Meeting
- Sprint Review Meeting
- Sprint Retrospective Meeting

[Ceremonies](https://www.visual-paradigm.com/scrum/what-are-scrum-ceremonies/)

#### What are the SCRUM artifacts?
- Product Vision
- Sprint Goal
- Product Backlog
- Sprint Backlog
- Definition of Done
- Burn-Down Chart
- Increment
- Burn-Down Chart

[Artifacts](https://www.visual-paradigm.com/scrum/what-are-scrum-artifacts/)

#### What is the main goal of a retrospective meeting?
[Retrospective Meeting](https://retromat.org/blog/what-is-a-retrospective/)

A retrospective is an opportunity to learn and improve. It is time set aside – outside of day-to-day routine – to reflect on past events and behaviors. In its simplest form you answer three questions:
    -What worked well?
    -What didn’t work well?
    -What are we going to try to do differently?

#### Explain, when would you recommend to use the waterfall methodology?
While the waterfall model has seen a slow phasing out in recent years in favor of more agile methods, it can still provide a number of benefits, particularly for larger projects and organizations that require the stringent stages and deadlines available within these cool, cascading waters.

Due to the inherent linear structure of a waterfall project, such applications are always well-suited for organizations or teams that work well under a milestone- and date-focused paradigm. With clear, concrete, and well understood stages that everyone on the team can understand and prepare for, it is relatively simple to develop a time line for the entire process and assign particular markers and milestones for each stage and even completion. This isn’t to suggest software development isn’t often rife with delays (since it is), but waterfall is befitting the kind of project that needs deadlines.