# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

It stands for stopping the current operation as soon as possible upon occurrence of unexpected errors. The result is a generally
more stable result. By improving the feedback loop, we quickly reveal all problems in our code, making it easier to spot and fix them.

Benefits:

- Shortens feedback loop.
- Increased confidence in our application.
- Protection of the persistence state.

[Ing C#](https://enterprisecraftsmanship.com/posts/exceptions-for-flow-control/)<br>
[In General](https://enterprisecraftsmanship.com/posts/fail-fast-principle/)

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?

Go through the list via 2 pointers, one moving at the pace of one node, the other two. When the faster
reaches the end, the other one should be at the middle element, returning it.

#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?

[Possible Answers](https://medium.com/solvingalgo/solving-algorithmic-problems-find-a-duplicate-in-an-array-3d9edad5ad41)

#### What is a linked list? How to find if a linked list has a loop?

Linked List:<br>
A linked list is a linear collection of elements whose order is not given by their allocation in the memory, but by pointing to
one another. A data structure of nodes, representing a sequence.

Loop detection:<br>
[Check me](https://www.geeksforgeeks.org/detect-loop-in-a-linked-list/)

#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?

[Big O Comprehensive Cheat Sheet](https://cooervo.github.io/Algorithms-DataStructures-BigONotation/index.html)

#### How does HashMap work?

[HashMap](https://www.geeksforgeeks.org/internal-working-of-hashmap-java/)<br>
[HashMap parts](https://howtodoinjava.com/java/collections/hashmap/how-hashmap-works-in-java/)

- A particular index location in array is referred as bucket, because it can hold the first element of a linkedlist of entry objects.
- Key object’s hashCode() is required to calculate the index location of Entry object.
- Key object’s equals() method is used to maintain uniqueness of keys in map.
- Value object’s hashCode() and equals() method are not used in HashMap’s get() and put() methods.
- Hash code for null keys is always zero, and such entry object is always stored in zero index in Entry[].

#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)

If immutable, the object's hashcode wont change and it allows caching the hashcode of different keys
which makes the overall retrieval process very fast. Also for mutable objects ,the hashCode() might be
dependent on fields that could change, if this happens you wont be able to find the key (and its value) in the
HashMap since hashCode() returns different value.

### Other

#### What is a garbage collector, in a nutshell?

A higher entity with the sole purpose of cleaning up after us.

Garbage collection (GC) is a form of automatic memory management.
The garbage collector, or just collector, attempts to reclaim garbage, or memory occupied by objects that
are no longer in use by the program. Garbage collection is often portrayed as the opposite of manual memory management, which requires the programmer to specify which objects to deallocate and
return to the memory system. Garbage collection, like other memory management techniques, may take a significant proportion of total processing
time in a program and can thus have significant influence on performance.

[The Collector](https://en.wikibooks.org/wiki/Introduction_to_Programming_Languages/Garbage_Collection)

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?

Casting is turning one object type into another.

Upcasting and downcasting are important part of Java, which allow us to build complicated programs using simple
syntax, and gives us great advantages, like Polymorphism or grouping different objects.
Java permits an object of a subclass type to be treated as an object of any superclass type. This is called upcasting.
Upcasting is done automatically, while downcasting must be manually done by the programmer.

[Cat Example](https://www.cs.utexas.edu/~cannata/cs345/Class%20Notes/14%20Java%20Upcasting%20Downcasting.htm)<br>
[Good and Short](https://stackoverflow.com/questions/23414090/what-is-the-difference-between-up-casting-and-down-casting-with-respect-to-class/32813618)

#### Which order should we catch the exceptions? Why?

The order is whatever matches first, gets executed.

If the first catch matches the exception, it executes, if it doesn't, the next one is tried and on and on until one is matched or none are.
So, when catching exceptions you want to always catch the most specific first and then the most generic (as RuntimeException or Exception).

[Concise](https://stackoverflow.com/questions/10964882/order-of-catching-exceptions-in-java)<br>
[Detailed](https://www.codejava.net/java-core/exception/5-rules-about-catching-exceptions-in-java)

### Object-oriented

#### What is a class?

In object-oriented programming, a class is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods).
In many languages, the class name is used as the name for the class (the template itself), the name for the default constructor of the class (a subroutine that creates objects), and as the type of objects generated by instantiating the class; these distinct concepts are easily conflated.

When an object is created by a constructor of the class, the resulting object is called an instance of the class, and the member variables specific to the object are called instance variables, to contrast with the class variables shared across the class.

In some languages, classes are only a compile-time feature (new classes cannot be declared at run-time), while in other languages classes are first-class citizens, and are generally themselves objects (typically of type Class or similar).
In these languages, a class that creates classes is called a metaclass.

#### What is an object?

In computer science, an object can be a variable, a data structure, a function, or a method, and as such, is a value in memory referenced by an identifier.

In the class-based object-oriented programming paradigm, object refers to a particular instance of a class, where the object can be a combination of variables, functions, and data structures.

In relational database management, an object can be a table or column, or an association between data and a database entity (such as relating a person's age to a specific person)

#### What is a constructor?

In class-based object-oriented programming, a constructor is a special type of subroutine called to create an object.
It prepares the new object for use, often accepting arguments that the constructor uses to set required member variables.

A constructor resembles an instance method, but it differs from a method in that it has no explicit return type, it is not implicitly inherited and it usually has different rules for scope modifiers.
Constructors often have the same name as the declaring class. They have the task of initializing the object's data members and of establishing the invariant of the class, failing if the invariant is invalid.
A properly written constructor leaves the resulting object in a valid state. Immutable objects must be initialized in a constructor.

[Constructor](<https://en.wikipedia.org/wiki/Constructor_(object-oriented_programming)>)

#### Do we require parameter for constructors?

Not necessarily, we can create non-argument or default constructiors. If we do not define such a constructor the
compiler will create one.

We can define a parameterized constructor ourselves should there be a need.

#### What is an interface?

It is actually a concept of abstraction and encapsulation.
For a given "box", it declares the "inputs" and "outputs" of that box.
In the world of software, that usually means the operations that can be invoked on the box (along with arguments) and in some cases the return types of these operations.

[Interface](https://stackoverflow.com/questions/2866987/what-is-the-definition-of-interface-in-object-oriented-programming)

#### What are access modifiers?

Access modifiers are keywords used to specify the accessibility of a class (or type) and its members.

[Modifiers](https://www.geeksforgeeks.org/access-modifiers-java/)

#### What is data hiding?

Data hiding was introduced as part of the OOP methodology, in which a program is segregated into objects with specific data and functions.
This technique enhances a programmer’s ability to create classes with unique data sets and functions, avoiding unnecessary penetration from other program classes.

Because software architecture techniques rarely differ, there are few data hiding contradictions.
Data hiding only hides class data components, whereas data encapsulation hides class data parts and private methods.

[Encapsulation](https://stackoverflow.com/questions/12013448/encapsulation-vs-data-hiding-java)<br>
[Encap Wiki](<https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)>)<br>
[Hiding]()

#### Can a static method use non-static members?

No, since it would not know which instance to operate on. If we instantiate the class within the static context eg. a method,
we will be able to access the non-static members of the class.

[Example](https://stackoverflow.com/questions/38263533/can-static-method-access-non-static-instance-variable)<br>

#### What is the difference between hiding a static method and overriding an instance method?

The version of the overridden instance method that gets invoked is the one in the subclass.
The version of the hidden static method that gets invoked depends on whether it is invoked from the superclass or the subclass.

Hiding a static (class) method:<br>

You cannot override static methods. However, a parent and child class can have static methods under identical signatures,
which results in the "hiding" of the parent class' method.

Overriding an instance method:<br>

If you do have a similar situation only regarding instance methods, it overrides the parent class' method. The method which
overrides can also return a subtype of the type which the overrode method would return. It is called a covariant return type.

[Behaviours](https://docs.oracle.com/javase/tutorial/java/IandI/override.html)

#### Define the following terms: Instantiation, Attribute, Method

- Instantiation: Creation of a real instance or realization of a particular abstraction or template such as a class.
- Attribute: Data contained, can be defined as fields or properties.
- Method: Behaviour, a procedure associated with a message and an object.

#### Could we access a static variable (or method) from a non-static method? Why?

[Yes](https://javarevisited.blogspot.com/2017/10/can-non-static-method-access-static.html)<br>
[For More Info](https://medium.com/@gabriellamedas/differences-between-static-and-non-static-methods-in-java-b93156be75c6)

#### Could we access a non-static variable (or method) from a static method? Why?

No, see above.

#### How many instances you have of a static variable of a given class?

One, or more if one would use ClassLoaders.

[ClassLoaders](https://stackoverflow.com/questions/3349797/is-it-possible-to-have-multiple-instances-of-static-variables)

#### Why is it not a good practice to write a lot of static methods?

- Static methods usually indicate a method that does not know where it belongs (even though they might "belong" to a class).
- It is preferable to think of them as global procedures, a class is mainly a tag in this case.
- Difficulty of testing.
- They are not polymorphic.
- They increase the complexity of an application.

[Reference](https://simpleprogrammer.com/static-methods-will-shock-you/)

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?

Features:<br>

Variable:<br>

- Belongs to the class and not instances / objects.
- Variables are initialized only once at execution, and will be done so before instance variables.
- A single copy will be shared across all instances.
- A static variable can be accessed directly by the classname without an object. `<class-name>.<variable-name>`
- A static method can call only other static methods and can not call a non-static method from it.
- A static method can be accessed directly by the class name and doesn't need any object.
- A static method cannot refer to "this" or "super" keywords in anyway. `<class-name>.<method-name>`

Method:<br>

- It is a method which belongs to the class and not to the object(instance).
- A static method can access only static data. It can not access non-static data (instance variables).

Possible Uses:<br>

- Declaring a true global constant, not a global variable/attribute. (PI in math)
- Singletons.
- Object creation.

[Info](https://www.guru99.com/java-static-variable-methods.html)

#### What is the ‘this’ reference?

It references the current object.

#### What are base class, subclass and superclass?

Base class: A class from which others are derived. <br>
Subclass: A class that inherits from another class. <br>
Superclass: A specific class in the chain of inheritance which has a parent-child relationship with a subclass.

#### Draw an object oriented family (as entities, with relations) on the whiteboard.

[Examples](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/uml-class-diagram-tutorial/)<br>
[Wiki](https://en.wikipedia.org/wiki/Class_diagram)

#### Difference between overloading and overriding?

Overloading:<br>

- Used to increase readability.
- Performed within class.
- Parameters must be different.
- It is an example of compile time polymorphism.
- Return type can be same or different.

Overriding:<br>

- Used to provide a specific implementation of the method already in the superclass.
- Occurs in two classes, that have an IS-A i.e. inheritance relationship.
- Parameters must be the same.
- It is an example of run-time polymorphism.
- Return type must be the same or a covariant.

#### What are the Object Oriented Principles? Explain the concepts with realistic examples!

Encapsulation:<br>

```
public class Dog {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

Abstraction:<br>

```
public interface Whenever {
    public Integer decideTime();
}

abstract class Whatever implements Whenever{
    abstract String SayWhat();
    public abstract Integer NumberizeIt();
}

public class Decision extends Whatever {
    //implement methods
}
```

Inheritance:<br>

```
public interface Movable {
    move();
}
public abstract class Animal {
    private String name;

    public String getName(){return name;}
    public void setName(String name){this.name = name;}
}

public class Dog extends Animal implements Movable {

   private void printName() {
        setName("Lord of Darkness");
        System.out.println(getName);
   }
   move(){...}
}
```

Polymorphism:<br>

```
List<Object> aList = new ArrayList<>();
```

#### What is method overloading?

It is creating methods of similar signatures within the same class with differing parameters.

#### What is method overriding?

Creating methods with the same signatures in parent-child classes (child overrides parent's method) for
specific implementation within the child class.

#### Explain how object oriented languages attempt to simplify memory management for Programmers.

Memory is automatically managed: memory is allocated when an object is created, and reclaimed at some point after the object becomes unreachable.

[In Detail](https://cdn.ineed.coffee/wp-content/uploads/2011/04/object-oriented-memory-management-java-c++.pdf)

#### Explain the “Single Responsibility” principle!

Every module, class or method is responsible for only one part of the functionality provided, and that should be entirely
encapsulated by the given class, method etc. All services should be aligned to this single responsibility.

#### What is an object oriented program? Explain, show.

A program based on the concept of "objects", which can contain data, in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods).
A feature of objects is an object's procedures that can access and often modify the data fields of the object with which they are associated (objects have a notion of "this" or "self").

Please see above for examples.

#### How do you make a class immutable? What do you need to watch out for?

- Declare the class as final, so it cannot be extended.
- Make all fields private so direct access is not allowed.
- No setter methods for variables.
- All mutable fields should be final, so a value can only be assigned once.
- Initialize all the fields via a constructor performing deep copy.
- Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

#### How many instances can be created for an abstract class?

None.
[Further](https://stackoverflow.com/questions/13670991/can-we-instantiate-an-abstract-class)

## Programming languages

### Java

#### What is autoboxing and unboxing?

Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes.
For example, converting an int to an Integer, a double to a Double, and so on. If the conversion goes the other way, this is called unboxing.

Autoboxing: `Character ch = 'a';`

[Auto and Unboxing](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)

#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

Short seems to be the best choice.
[Types](https://en.wikibooks.org/wiki/Java_Programming/Primitive_Types)

#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

As a general rule, variables declared inside a scope are not visible/accessible to the code that is defined outside the scope.
Thus, when you declare a variable within a scope, you are localizing that variable and protecting it from an unauthorized access and/or modification.
Indeed, the scope rules provide the foundation for encapsulation.

Their lifetime is the lifetime of their scope, be it a method, class etc.

[Further](http://etutorials.org/cert/java+certification/Chapter+4.+Declarations+and+Access+Control/4.5+Scope+Rules/)

#### What is the purpose of the ‘equals()’ method?

If compares two objects by their attributes' values.
If we use `==` then the two objects' memory references are compared.

[equals(), ==, hashCode()](https://www.javaworld.com/article/3305792/comparing-java-objects-with-equals-and-hashcode.html)

#### What is the difference between '==' and 'equals()'?

Please see above.

#### What does the ‘static’ keyword mean?

When a member is declared static, it can be accessed before any objects of its class are created, and without reference to any object.
When a variable is declared as static, then a single copy of variable is created and shared among all objects at class level.
Static variables are, essentially, global variables. All instances of the class share the same static variable.

When a method is declared with static keyword, it is known as static method. The most common example of a static method is main( ) method.
As discussed above, Any static member can be accessed before any objects of its class are created, and without reference to any object.

Static data (fields and members) are loaded into memory on class loading and remain until the class is unloaded from memory (typically on JVM termination).

[Data Segments](https://en.wikipedia.org/wiki/Data_segment)

#### Why is the main() method declared as static? Explain.

Since main() method is the entry point of any Java application, hence making the main() method as static is mandatory due to following reasons:<br>

- The static main() method makes it very clear for the JVM to call it for launching the Java Application. Otherwise, it would be required to specify the entry function for each Java application build, for the JVM to launch the application.
- The method is static because otherwise there would be ambiguity which constructor should be called.
- The main() method is static because its convenient for the JDK.
  Consider a scenario where it’s not mandatory to make main() method static.
  Then in this case, that just makes it harder on various IDEs to auto-detect the ‘launchable’ classes in a project.
  Hence making it a convention to make the entry method ‘main()’ as ‘public static void main(String[] args)’ is convenient.

#### What is the default access modifier in a class?

If a class has no modifier (the default, also known as package-private), it is visible only within its own package.

[Access Modifiers](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)

#### What is the JVM?

Java Virtual Machine:<br>
A Java virtual machine (JVM) is a virtual machine that enables a computer to run Java programs as well as programs written in other languages that are also compiled to Java bytecode.
The JVM is detailed by a specification that formally describes what is required in a JVM implementation.
Having a specification ensures interoperability of Java programs across different implementations so that program authors using the Java Development Kit (JDK) need not worry about idiosyncrasies of the underlying hardware platform.

#### What is the difference between the JRE and the JDK?

Java Runtime Environment:<br>
The Java Runtime Environment provides the minimum requirements for executing a Java application; it consists of the Java Virtual Machine (JVM), core classes, and supporting files.

Java Development Kit:<br>
The Java Development Kit (JDK) is a software development environment used for developing Java applications and applets.
It includes the Java Runtime Environment (JRE), an interpreter/loader (Java), a compiler (javac), an archiver (jar), a documentation generator (Javadoc) and other tools needed in Java development.

[Further](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/)

#### What is the difference between long and Long?

Long<br>

- An object/class, can be null as well.
- Can be passed to a method accepting Object, Number, Long or long (autoboxing).
- Can be used as a generic parameter type. `List<Long>`.
- Serializable.

long<br>

- A primitive, which must have a value.
- `List<long>` is not accepted.
- More efficient than Long considering memory space and processing speed.

#### Can a long store bigger numbers than a Long?

No, Long uses long.

#### What kind of packages do you know under java.util.\* ? Bring at least 3 examples.

Random, Math, List, Hashmap, HashSet, ArrayList

#### What are the access modifiers in Java? Which one could we use for class?

Default, Private, Protected, Public. For a class we can use the default and public ones.

#### Can an “enum” contain methods in Java? Explain.

Yes, an enum can contain methods, it is still a class.

[Example](https://stackoverflow.com/questions/18883646/java-enum-methods/18883717)<br>
[Enums](https://blog.scottlogic.com/2016/07/28/java-enums-how-to-use-them-smarter.html)

#### When would you use a private/protected/public attribute? What is the difference?

When I would need to give specific access to other parts of the application. I would use private regarding most if not
all of the fields within classes and use getters / setters where need be. Difference lies in accessibility of the outside world
(outside of that class in which the attribute is) to said attributes.

For constants I think it would be better to use public, for example as they are static final.

#### How do you prevent developers from subclassing a class?

We can declare it as final.

#### How do you prevent developers from overriding a method in a subclass?

Declare the methods as final in the superclass.

#### How do you prevent developers from changing the value of a variable?

Final...private, getter.

#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

Create a currency object which stores the amount as a primitive float or double.

#### What happens if you try to call something, that you have no access to, because of data hiding?

The compiler will throw an error, not being able to find it. This question is too ambiguous for me. If we are talking about about a field for example
I would create a getter for it, provided it is private and we cannot access it.

#### What happens if you try to delete/drop an item from an array, while you are iterating over it?

From an array you must reassign each item, or you can do a `System.arraycopy`, or simply copy the elements which you
want to keep.

#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

I think a ConcurrentModificationException occurs.
[ConcurrentModificationException](https://docs.oracle.com/javase/7/docs/api/java/util/ConcurrentModificationException.html)

#### What happens if you try to add an item to the end of an array, while you are iterating over it?

We will most likely receive an ArrayIndexOutOfBoundsException.
[ArrayIndexOutOfBoundsException](https://docs.oracle.com/javase/9/docs/api/java/lang/ArrayIndexOutOfBoundsException.html)

#### If you need to access the iterator variable after a for loop, how would you do it?

I can think of it like so:<br>

```
int outsider = 0;
for (int i=0; i < num; i++) {
     //do stuff
     outsider = i;
     }
```

This way the outsider keeps the current value of i, however if we know the latest value we can add a condition which only saves
the last one, not needing to assign a new value each time the loop runs.

#### Which interfaces extend the Collection interface in Java. Which classes?

Mapped herein:<br>
[Collection](https://www.javatpoint.com/collections-in-java)

#### What is the connection between equals() and hashCode()? How are they used in HashMap?

- Use `key.hashCode()` to determine which bucket the entry is stored, if any
- If found, for each entry's key `key1` in that bucket, if `key == key1 || key.equals(key1)`, then return `key1`'s entry
- Any other outcomes, no corresponding entry

[Further Info](https://stackoverflow.com/questions/1894377/understanding-the-workings-of-equals-and-hashcode-in-a-hashmap)

#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?

Checked:<br>

- Exceptions that are checked at compile time.
  If some code within a method throws a checked exception, then the method must either handle the exception or it must specify the exception using throws keyword.

Unchecked:<br>

- Exceptions that are not checked at compiled time. In C++, all exceptions are unchecked, so it is not forced by the compiler to either handle or specify the exception.
  It is up to the programmers to be civilized, and specify or catch the exceptions.
- In Java exceptions under Error and RuntimeException classes are unchecked exceptions, everything else under throwable is checked.

Example of SQLException or IOException of using FileReader.

#### What is Error in Java and how does it relate to Exception?

An Error is a subclass of Throwable that indicates serious problems that a reasonable application should not try to catch.
Most such errors are abnormal conditions.
The ThreadDeath error, though a "normal" condition, is also a subclass of Error because most applications should not try to catch it.

Both Errors and Exceptions are the subclasses of java.lang.Throwable class.
Errors are the conditions which cannot get recovered by any handling techniques. It surely cause termination of the program abnormally.
Errors belong to unchecked type and mostly occur at runtime. Some of the examples of errors are Out of memory error or a System crash error.

#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

Finally runs after all other previous blocks, always.
Finally block is used for cleanup, like to free resources used within try/catch, close db connections, close sockets, etc.. even when an unhandled exception occurs within your try/catch block.
The only time the finally block doesn't execute is when System.exit() is called in try/catch or some error occurs instead of an exception.

#### What is the largest number you can work with in Java?

If we go by primitives, it is long with +9,223,372,036,854,775,807.
[Values](https://docs.oracle.com/javase/6/docs/api/constant-values.html#java.lang.Integer.MAX_VALUE)

#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?

If you are overriding any method, overridden method (i.e. declared in subclass) must not be more restrictive.

It's a fundamental principle in OOP: the child class is a fully-fledged instance of the parent class, and must therefore present at least the same interface as the parent class.
Making protected/public things less visible would violate this idea; you could make child classes unusable as instances of the parent class.

#### Can the main method be overridden? Explain your answer!

No, it is a static method, however we can overload it or hide it.

#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?

See below.

#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

The overriding method must NOT throw checked exceptions that are new or broader than those declared by the overridden method.
For example, a method that declares a FileNotFoundException cannot be overridden by a method that declares a SQLException, Exception, or any other non-runtime exception unless it's a subclass of FileNotFoundException.

- If SuperClass does not declare an exception, then the SubClass can only declare unchecked exceptions, but not the checked exceptions.
- If SuperClass declares an exception, then the SubClass can only declare the child exceptions of the exception declared by the SuperClass, but not any other exception.
- If SuperClass declares an exception, then the SubClass can declare without exception.

It is mainly due to polymorphism.

#### What does "final" mean in case of a variable, method or a class?

Variable becomes a constant, cannot be modified.
A class cannot be inherited if declared final.
A method declared final cannot be overridden.

#### What is the super keyword?

It refers to the SuperClass or Parent class of the current class.

#### What are “generics”? When to use? Show examples.

Java Generics were introduced in JDK 5.0 with the aim of reducing bugs and adding an extra layer of abstraction over types.
It literally is what the word "generic" implies, making something into an all-out usable abstraction.

"Java Generic methods and generic classes enable programmers to specify, with a single method declaration, a set of related methods, or with a single class declaration, a set of related types, respectively."

[Generics](https://www.tutorialspoint.com/java/java_generics.htm)

Example:<br>
A generic interface implemented by memory and JDBC modules, for queries on a database. This greatly reduced code repetition
and simplified understanding.

```
public interface GenericQueriesDao<T> {

    void add(T object);
    T find(int id);
    void remove(int id);

    List<T> getAll();
    void removeAll();

}
```

#### What is the benefit of having “generic” containers?

Generics is a feature of the Java Language that promotes type safety, code manageability and efficiency and, most importantly, much cleaner and reduced code.
You can use generics to create type safe collections with no boxing and un-boxing overhead; this is also known as parametric polymorphism.

#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?

Possibly via sockets, or Servlets over a web framework or in the background sending packets to one another.

[Sockets](https://docs.oracle.com/javase/tutorial/networking/sockets/)<br>
[More Sockets](https://www.oracle.com/technetwork/java/socket-140484.html)

#### What is an annotation? What can be annotated and how? Show examples.

Annotations, a form of metadata, provide data about a program that is not part of the program itself.
Annotations have no direct effect on the operation of the code they annotate.

- Information for the compiler — Annotations can be used by the compiler to detect errors or suppress warnings.
- Compile-time and deployment-time processing — Software tools can process annotation information to generate code, XML files, and so forth.
- Runtime processing — Some annotations are available to be examined at runtime.

```
@Override
@Author
@Test
@BeforeEach
@BeforeAll
@WebServlet
```

### C#;

#### Explain the purpose of IL and how does it relate to CLR?

IL/CIL:<br>
The intermediate language binary instruction set, defined within the Common Language Infrastructure (CLI) specification. CIL instructions are executed by a CLI-compatible runtime environment such as the Common Language Runtime. Languages which target the CLI compile to CIL. CIL is object-oriented, stack-based bytecode. Runtimes typically just-in-time compile CIL instructions into native code.

CLR:<br>
CLR is the basic and Virtual Machine component of the .NET Framework. It is the run-time enviornment in the .NET Framework that runs the codes and helps in making the development process easier by providing various services. Basically, it is responsible for managing the execution of .NET programs regardless of any .NET programming language.

Parts:<br>

- Common Language Specification(CLS)
- Common Type System(CTS)
- Garbage Collector(GC)
- Just-in-Time Compiler(JIT)

[CIL](https://en.wikipedia.org/wiki/Common_Intermediate_Language)<br>
[CLI](https://en.wikipedia.org/wiki/Common_Language_Infrastructure)<br>
[CIL Instructions](https://en.wikipedia.org/wiki/List_of_CIL_instructions)<br>
[Understanding CLI](https://www.codeproject.com/Articles/362076/Understanding-Common-Intermediate-Language-CIL)<br>
[.NET Core CLR](https://stackoverflow.com/questions/48908739/clr-vs-core-clr)<br>
[Related Code](https://www.codeproject.com/Articles/781096/What-is-IL-Code-CLR-CTS-CLS-JIT)<br>
[CLR and Friends](https://www.geeksforgeeks.org/common-language-runtime-clr-in-c-sharp/)

#### What does “managed code” mean?

Managed code is not compiled to machine code but to an intermediate language which is interpreted and executed by some service on a machine and is therefore operating within a secure framework which handles dangerous things like memory and threads for you. In modern usage this frequently means .NET but does not have to.

- Executed by the CLR
- Targets the common language runtime, known as managed code
- Supplies the metadata for the CLR to provide services such as memory management, cross-language integration, code access security,
  and automatic lifetime control of objects. All code based on IL executes as managed code
- Code that executes under the CLI execution environment

Unmanaged code is compiled to machine code and therefore executed by the OS directly. It therefore has the ability to do damaging/powerful things Managed code does not. This is how everything used to work, so typically it's associated with old stuff like .dlls.

Native code is often synonymous with Unmanaged, but is not identical.

[Source](https://stackoverflow.com/questions/334326/what-is-managed-or-unmanaged-code-in-programming)

#### What is an assembly?

An assembly is a collection of types and resources that are built to work together and form a logical unit of functionality. Assemblies take the form of executable (.exe) or dynamic link library (.dll) files, and are the building blocks of .NET applications. They provide the common language runtime with the information it needs to be aware of type implementations.
To the runtime, a type does not exist outside the context of an assembly.

[Assemblies](https://docs.microsoft.com/en-us/dotnet/standard/assembly/)

#### What is the difference between an EXE and a DLL?

EXE:

- It's a executable file.
- When loading an executable, no export is called, but only the module entry point.
- When a system launches new executable, a new process is created
- The entry thread is called in context of main thread of that process.
- Essentially a launcher of a separate application.

DLL:

- It's a Dynamic Link Library.
- There are multiple exported symbols.
- The system loads a DLL into the context of an existing process.
- Cannot run on it's own.
- Essentially a shared library.

[Differences](https://stackoverflow.com/questions/1210873/difference-between-dll-and-exe)<br>
[Another Source](http://www.differencebetween.net/technology/difference-between-exe-and-dll/)

#### What is strong-typing versus weak-typing? Which is preferred? Why?

Weakly-typed:<br>
In a weakly typed language, the type of a value depends on how it is used. For example if I can pass a string to the addition operator and it will AutoMagically be interpreted as a number or cause an error if the contents of the string cannot be translated into a number. Similarly, I can concatenate strings and numbers or use strings as booleans, etc.

Strongly-typed:<br>
In a strongly typed language, a value has a type and that type cannot change. What you can do to a value depends on the type of the value.

Strongly-typed advantage:<br>
The advantage of a strongly typed language is that you are forced to make the behaviour of your program explicit. If you want to add a number and a string your code must translate the string into a number to be used as an operand of the addition operator. This makes code easier to understand because there is no (or less) hidden behaviour. However, it also makes your code more verbose.

Weakly-typed advantage:<br>
The advantage of a weakly typed language is that you need to write less code. However, that code is harder to understand because a lot of its behaviour is hidden in implicit type conversions.

[Source](https://wiki.c2.com/?WeakAndStrongTyping)<br>
[Different View](https://www.destroyallsoftware.com/compendium/strong-and-weak-typing?share_key=6b0dd1ec18ab6102)

#### What is a namespace?

Namespaces:
Namespaces are used both as an "internal" organization system for a program, and as an "external" organization system—a way of presenting program elements that are exposed to other programs.

- They organize large code projects.
- They are delimited by using the . operator.
- The using directive obviates the requirement to specify the name of the namespace for every class.
- The global namespace is the "root" namespace: global::System will always refer to the .NET System namespace.

[Namespace](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/namespaces/)
[Namespace Declarations](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/namespaces)

#### Explain sealed class in C#?

When applied to a class, the sealed modifier prevents other classes from inheriting from it, akin to the final modifier in Java.

You can also use the sealed modifier on a method or property that overrides a virtual method or property in a base class. This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.

[Sealed Modifier](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/sealed)

#### What is explicit vs. implicit conversion? Give examples of both of them.

Explicit:<br>
Explicit conversion or cast is a process of passing information to the compiler that the program is trying to perform conversion with the knowledge of possible data loss.

```
double d = 75.25;
int i;
i = (int)d;
```

Implicit:<br>
Implicit conversion is the simplest type of conversion. This type of conversion is type-safe and no loss of data happens during conversion. These conversions deal in converting a derived class to base class.

```
int i = 75;
long j = i;
```

[Conversions](https://www.softwaretestinghelp.com/c-sharp/c-sharp-type-casting-data-conversion/#Implicit_Conversion)

#### Is a struct stored on the heap or stack?

Value types, and as such a struct is stored on the stack when the value is a local variable or temporary.

[Struct Allocation](https://stackoverflow.com/questions/4853213/are-structs-always-stack-allocated-or-sometimes-heap-allocated)<br>
[The Truth About Value Types](https://docs.microsoft.com/en-gb/archive/blogs/ericlippert/the-truth-about-value-types)

#### Can a struct have methods?

Structure:<br>

- Structure can include constructors, constants, fields, methods, properties, indexers, operators, events & nested types.
- Structure cannot include parameterless constructor or destructor.
- Structure can implement interfaces, same as class.
- A structure cannot inherit another structure or class, and it cannot be the base of a class.
- Structure members cannot be specified as abstract, virtual, or protected.

Differences between a Class and a Structure:<br>

- Class is a reference type whereas struct is a value type
- Structs cannot declare a default constructor or destructor. However, it can have parametrized constructors.
- Structs can be instasntiated without the new operator. However, you won't be able to use any of its methods, events or properties if you do so.
- Structs cannot be used as a base or cannot derive another struct or class.

[Struct](https://www.tutorialsteacher.com/csharp/csharp-struct)<br>
[Destructor / Finalizer](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/destructors)

#### Can DateTimes be null?

As DateTime is a value type it must either be set to a nullable type or the MinValue must be utilised.

```
Nullable<DateTime>
DateTime? nullDateTime = null;
```

Some state that the DateTime.MinValue could be used for this, or a parameterless DateTime instantiated, resulting in the same outcome. However that returns `1/1/0001 12:00:00 AM`, and not a null. Thus it still returns a value.

#### List out the differences between Array and ArrayList in C#?

1. Array stores data of the same type whereas ArrayList stores data which may be of different types.
2. Size of an ArrayList grows dynamically while Array size remains static throughout the program.
3. Insertion and deletion operation in ArrayList is slower than an Array.
4. Arrays are strongly typed whereas ArrayLists are not strongly typed.
5. Arrays belong to System.Array namespace whereas ArrayLists belong to System.Collections namespace.

Array:<br>

- Strongly typed, can store only one type of elements
- We can only store one data type
- It cannot accept a null value, or non-value
- Belongs to System.Array namespace

ArrayList:<br>

- Weakly typed, can store any type of elements
- We can store any data type, even more than one type at the same time
- It can hold a null value
- Belongs to System.Collections namespace

[Array vs ArrayList](https://keydifferences.com/difference-between-array-and-arraylist-in-c-sharp.html)<br>
[Differences](https://www.c-sharpcorner.com/blogs/difference-between-array-and-arraylist-in-c-sharp)<br>
[ArrayList](https://referencesource.microsoft.com/#mscorlib)

#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?

The using() pattern provides a convenient synthax that ensures the correct usage of IDisposable objects.

When the lifetime of an IDisposable object is limited to a single method, you should declare and instantiate it in the using statement. The using statement calls the Dispose method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as Dispose is called. Within the using block, the object is read-only and cannot be modified or reassigned.

The using statement ensures that Dispose is called even if an exception occurs within the using block. You can achieve the same result by putting the object inside a try block and then calling Dispose in a finally block; in fact, this is how the using statement is translated by the compiler. The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):

[IDisposable, Dispose()](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/implementing-dispose)<br>
[Using](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/using-statement)

#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?

Finalizers are needed to guarantee the release of scarce resources back into the system like file handles, sockets, kernel objects, etc. Since the finalizer always runs at the end of the objects life, it’s the designated place to release those handles.

The Dispose pattern is used to provide deterministic destruction of resources. Since the .net runtime garbage collector is non-deterministic (which means you can never be sure when the runtime will collect old objects and call their finalizer), a method was needed to ensure the deterministic release of system resources. Therefore, when you implement the Dispose pattern properly you provide deterministic release of the resources and in cases where the consumer is careless and does not dispose the object, the finalizer will clean up the object.

[Source](https://stackoverflow.com/questions/331786/since-net-has-a-garbage-collector-why-do-we-need-finalizers-destructors-dispose)

#### Why to use keyword “const” in C#? Give an example.

A `const` is a constant field or local, that are not variables and cannot be modified after declaration.
The `static` modifier is not allowed in a constant declaration.

```
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

The `readonly` keyword differs from the `const` keyword. A `const` field can only be initialized at the declaration of the field. A `readonly` field can be initialized either at the declaration or in a constructor. Therefore, `readonly` fields can have different values depending on the constructor used. Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants.

[Const](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/const)<br>
[Readonly](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/readonly)

#### What is the difference between “const” and “readonly” variables in C#?

Please see above.

#### What is a property in C#?

A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field. Properties can be used as if they are public data members, but they are actually special methods called accessors. This enables data to be accessed easily and still helps promote the safety and flexibility of methods.

[Properties](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties)

#### List out two different types of errors in C#?

- Program errors. A program error is a run-time error that cannot necessarily be avoided by writing bug-free code.
- System failures. A system failure is a run-time error that cannot be handled programmatically in a meaningful way. For example, any method can throw an OutOfMemoryException exception if the common language runtime is unable to allocate additional memory.
- Usage errors. A usage error represents an error in program logic that can result in an exception. However, the error should be addressed not through exception handling but by modifying the faulty code.

[Exception Class](https://docs.microsoft.com/en-us/dotnet/api/system.exception?view=netframework-4.8)<br>
[Errors](https://docs.microsoft.com/en-us/dotnet/api/system.exception?view=netframework-4.8#Errors)

#### What is the difference between “out” and “ref” parameters in C#?

In:<br>
The in keyword specifies that you are passing a parameter by reference, but also that you will not modify the value inside a method. Essentially it is passed as a read-only reference. The argument passed must be initialized before.

Out:<br>
The out keyword causes arguments to be passed by reference. It makes the formal parameter an alias for the argument, which must be a variable. In other words, any operation on the parameter is made on the argument. It is like the ref keyword, except that ref requires that the variable be initialized before it is passed. It is also like the in keyword, except that in does not allow the called method to modify the argument value. To use an out parameter, both the method definition and the calling method must explicitly use the out keyword.

Ref:<br>
When used in a method's parameter list, the ref keyword indicates that an argument is passed by reference, not by value. The ref keyword makes the formal parameter an alias for the argument, which must be a variable. In other words, any operation on the parameter is made on the argument. For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.

[In](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/in-parameter-modifier)<br>
[Out](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/out-parameter-modifier)<br>
[Ref](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/ref)

#### Can we override private virtual method in C#?

No, because you can only override what you can see. A private method is a private implementation detail of a base class and must not be accessible.

[Private Virtual](https://stackoverflow.com/questions/3082310/why-are-private-virtual-methods-illegal-in-c)

#### What's the difference between IEquatable and just overriding Object.Equals()?

MSDN:<br>
If you implement IEquatable, you should also override the base class implementations of Object.Equals(Object) and GetHashCode so that their behavior is consistent with that of the IEquatable.Equals method. If you do override Object.Equals(Object), your overridden implementation is also called in calls to the static Equals(System.Object, System.Object) method on your class. This ensures that all invocations of the Equals method return consistent results.

From a performance standpoint, it's better to use the generic version because there's no boxing/unboxing penalty associated with it.

[Exact Question](https://stackoverflow.com/questions/2734914/whats-the-difference-between-iequatable-and-just-overriding-object-equals)

#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!

Public:<br>
The type or member can be accessed by any other code in the same assembly or another assembly that references it.

Private:<br>
The type or member can be accessed only by code in the same class or struct.

Protected:<br>
The type or member can be accessed only by code in the same class, or in a class that is derived from that class.

Internal:<br>
The type or member can be accessed by any code in the same assembly, but not from another assembly.

Protected Internal:<br>
The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.

Private Protected:<br>
The type or member can be accessed only within its declaring assembly, by code in the same class or in a type that is derived from that class.

[Access Modifiers](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)

#### What’s the difference between using `override` and `new` keywords when defining method in child class?

The override modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.

The new keyword explicitly hides a member that is inherited from a base class. When you hide an inherited member, the derived version of the member replaces the base class version.

[Override](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/override)<br>
[New](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-modifier)

#### Explain StringBuilder class in C#!

Although StringBuilder and String both represent sequences of characters, they are implemented differently. String is an immutable type. That is, each operation that appears to modify a String object actually creates a new string.

For example, the call to the String.Concat method in the following C# example appears to change the value of a string variable named value. In fact, the Concat method returns a value object that has a different value and address from the value object that was passed to the method.

When not to use a StringBuilder:<br>

- When the number of changes that your app will make to a string is small. In these cases, StringBuilder might offer negligible or no performance improvement over String.

- When you are performing a fixed number of concatenation operations, particularly with string literals. In this case, the compiler might combine the concatenation operations into a single operation.

- When you have to perform extensive search operations while you are building your string. The StringBuilder class lacks search methods such as IndexOf or StartsWith. You'll have to convert the StringBuilder object to a String for these operations, and this can negate the performance benefit from using StringBuilder.

When to use it:<br>

- When you expect your app to make an unknown number of changes to a string at design time (for example, when you are using a loop to concatenate a random number of strings that contain user input).

- When you expect your app to make a significant number of changes to a string.

[StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netframework-4.8)<br>
[Usage]()

#### How we can sort the array elements in descending order in C#?

Either via build-in functions:<br>

```
Array.Sort(array);
Array.Reverse(array);
```

Or we could use LINQ:<br>

```
arr = arr.OrderByDescending(c => c).ToArray();
```

For more check the link below.
[Source](https://www.geeksforgeeks.org/different-ways-to-sort-an-array-in-descending-order-in-c-sharp/)

#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).

An Interface type can have as its contents a null reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type

Structs can implement an interface but they cannot inherit from another struct. For that reason, struct members cannot be declared as protected.

Runtime creates new method for every "Type Argument". When you call a generic method with a value type, you're actually calling a dedicated method created for respective value type. So there is no need of boxing.

When calling the interface method which is not directly implemented in your struct type, then boxing will happen.

[Boxing of Value Types](https://stackoverflow.com/questions/25508615/are-value-types-boxed-when-passed-as-generic-parameters-with-an-interface-constr)<br>
[Value Type Boxing by Interfaces](https://blogs.u2u.be/u2u/post/c-value-type-boxing-by-interfaces)<br>
[Generics](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/)

#### What are Nullable Types in C#?

A nullable value type T? represents all values of its underlying value type T and an additional null value. For example, you can assign any of the following three values to a bool? variable: true, false, or null. An underlying value type T cannot be a nullable value type itself.

Any nullable value type is an instance of the generic System.Nullable structure. You can refer to a nullable value type with an underlying type T in any of the following interchangeable forms: Nullable or T?.

You typically use a nullable value type when you need to represent the undefined value of an underlying value type. For example, a Boolean, or bool, variable can only be either true or false. However, in some applications a variable value can be undefined or missing. For example, a database field may contain true or false, or it may contain no value at all, that is, NULL. You can use the bool? type in that scenario.

[Nullable Types](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/nullable-value-types)

#### Conceptually, what is the difference between early-binding and late-binding?

Early bound just means the target method is found at compile time, and code is created that will call this. Whether its virtual or not (meaning there's an extra step to find it at call time is irrelevant). If the method doesn't exist the compiler will fail to compile the code.

Late bound means the target method is looked up at run time. Often the textual name of the method is used to look it up. If the method isn't there, bang. The program will crash or go into some exception handling scheme at run time.

Binding usually has an effect on performance. Because late binding requires lookups at runtime, it is usually means method calls are slower than early bound method calls.

Early Bound:<br>

- The compiler can work out where the called function will be at compile time.
- The compiler can guarantee early (before any of the programs code runs) that the function will exist and be callable at runtime.
- The compiler guarantees that the function takes the right number of arguments and that they are of the correct type. It also checks that the return value is of the correct type.

Late Bound:<br>

- The lookup will take longer because its not a simple offset calculation, there are usually text comparisons to be made.
- The target function may not exist.
- The target function may not accept the arguments passed to it, and may have a return value of the wrong type.
- With some implementations, the target method can actually change at run-time. So, the lookup may execute a different function. Late-binding allows function calls to start calling a new override for a method instead of calling the existing base method.

Early-binding is considered static, late-binding is dynamic in regards of C#.

[Explanation](https://stackoverflow.com/questions/484214/early-and-late-binding)<br>
[Further](http://net-informations.com/faq/oops/binding.htm)

#### What is a delegate, event, callback, multicast delegate?

Delegate:<br>

A delegate is a type that safely encapsulates a method, similar to a function pointer in C and C++. Unlike C function pointers, delegates are object-oriented, type safe, and secure. The type of a delegate is defined by the name of the delegate.

A delegate is a type that represents references to methods with a particular parameter list and return type. When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type. You can invoke (or call) the method through the delegate instance.

A delegate object is normally constructed by providing the name of the method the delegate will wrap, or with an anonymous function. Once a delegate is instantiated, a method call made to the delegate will be passed by the delegate to that method. The parameters passed to the delegate by the caller are passed to the method, and the return value, if any, from the method is returned to the caller by the delegate. This is known as invoking the delegate. An instantiated delegate can be invoked as if it were the wrapped method itself.

Delegates cannot be inherited, they are sealed.

Multicast-Delegate:<br>

It is a delegate that invokes more than one method.
A delegate can call more than one method when invoked. This is referred to as multicasting. To add an extra method to the delegate's list of methods—the invocation list—simply requires adding two delegates using the addition or addition assignment operators ('+' or '+=').

If the delegate uses reference parameters, the reference is passed sequentially to each of the three methods in turn, and any changes by one method are visible to the next method. When any of the methods throws an exception that is not caught within the method, that exception is passed to the caller of the delegate and no subsequent methods in the invocation list are called. If the delegate has a return value and/or out parameters, it returns the return value and parameters of the last method invoked. To remove a method from the invocation list, use the subtraction or subtraction assignment operators (- or -=).

Event:<br>

Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).

Events enable a class or object to notify other classes or objects when something of interest occurs. The class that sends (or raises) the event is called the publisher and the classes that receive (or handle) the event are called subscribers.

Callback:<br>

Callbacks are extensibility points that allow a framework to call back into user code through a delegate. These delegates are usually passed to the framework through a parameter of a method.

A callback function is code within a managed application that helps an unmanaged DLL function complete a task. Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation. Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.

[In Depth](https://csharpindepth.com/articles/Events)<br>
[Delegates](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/)<br>
[Using Delegates](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/using-delegates)<br>
[Events](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/events/)<br>
[Events Wiki](<https://en.wikipedia.org/wiki/Event_(computing)>)<br>
[Callback Wiki](<https://en.wikipedia.org/wiki/Callback_(computer_programming)>)<br>
[Callback Functions](https://docs.microsoft.com/en-us/dotnet/framework/interop/callback-functions)<br>
[Events and Callbacks](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/events-and-callbacks)

#### What is an enum in C#?

An enumeration type (or enum type) is a value type defined by a set of named constants of the underlying integral numeric type. To define an enumeration type, use the enum keyword and specify the names of enum members.

[Enum](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/enum)

#### What are the null-coalescing and null-conditional operators?

The null-coalescing operator ?? returns the value of its left-hand operand if it isn't null; otherwise, it evaluates the right-hand operand and returns its result. The ?? operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.

The null-coalescing assignment operator ??= assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null. The ??= operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.

[Coalescing](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/null-coalescing-operator)

A null-conditional operator applies a member access, ?., or element access, ?[], operation to its operand only if that operand evaluates to non-null; otherwise, it returns null.

The null-conditional operators are short-circuiting. That is, if one operation in a chain of conditional member or element access operations returns null, the rest of the chain doesn't execute.

[Conditional](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/member-access-operators#null-conditional-operators--and-)

The unary postfix ! operator is the null-forgiving operator. In an enabled nullable annotation context, you use the null-forgiving operator to declare that expression x of a reference type isn't null: x!. The unary prefix ! operator is the logical negation operator.

[Forgiving](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/null-forgiving)

#### What is serialization?

Serialization is the process of converting the state of an object into a form that can be persisted or transported. The complement of serialization is deserialization, which converts a stream into an object. Together, these processes allow data to be stored and transferred.

[Serialization](https://docs.microsoft.com/en-us/dotnet/standard/serialization/)

#### What is the difference between Finalize() and Dispose() methods?

Finalize():<br>

- It can be used to free unmanaged resources (when you implement it) like files, database connections etc. held by an object before that object is destroyed.
- Internally, it is called by the Garbage Collector and cannot be called by user code.
- It belongs to the Object class.
- It's implemented with the help of the destructor in C++ & C#.
- There are performance costs associated with the Finalize method since it doesn't clean the memory immediately and is called by GC automatically.

Dispose:<br>

- It is used to free unmanaged resources like files, database connections etc. at any time.
- Explicitly, it is called by user code and the class which is implementing dispose method, have to implement IDisposable interface.
- It belongs to IDisposable interface.
- It's implemented by the IDisposable interface Dispose() method.
- There is no performance cost associated with Dispose method.

[Further](https://www.dotnettricks.com/learn/netframework/difference-between-finalize-and-dispose-method)<br>
[Close vs Dispose](https://stackoverflow.com/questions/17168839/what-is-the-difference-between-connection-close-and-connection-dispose)

#### How do you inherit a class from another class in C#?

This tutorial introduces you to inheritance in C#. Inheritance is a feature of object-oriented programming languages that allows you to define a base class that provides specific functionality (data and behavior) and to define derived classes that either inherit or override that functionality.

[Inheritance](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance)

#### What is difference between “is” and “as” operators in C#?

Is:<br>
The is operator checks if an object can be cast to a specific type.

As:<br>
The as operator attempts to cast an object to a specific type, and returns null if it fails.

[Is, As](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/type-testing-and-cast)<br>
[Further](https://stackoverflow.com/questions/3786361/difference-between-is-and-as-keyword)

#### What are indexers in C# .NET?

Indexers allow instances of a class or struct to be indexed just like arrays. The indexed value can be set or retrieved without explicitly specifying a type or instance member. Indexers resemble properties except that their accessors take parameters.

[Indexers](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/indexers/)

#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?

Query expressions can be compiled to expression trees or to delegates, depending on the type that the query is applied to. IEnumerable queries are compiled to delegates. IQueryable and IQueryable queries are compiled to expression trees.

Yes, both will give you deferred execution.

The difference is that IQueryable is the interface that allows LINQ-to-SQL (LINQ.-to-anything really) to work. So if you further refine your query on an IQueryable, that query will be executed in the database, if possible.

For the IEnumerable case, it will be LINQ-to-object, meaning that all objects matching the original query will have to be loaded into memory from the database.

[Differences Explained](https://stackoverflow.com/questions/2876616/returning-ienumerablet-vs-iqueryablet)

#### What is LINQ? Explain the idea of extension methods.

Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language. Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support. Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on. With LINQ, a query is a first-class language construct, just like classes, methods, events. You write queries against strongly typed collections of objects by using language keywords and familiar operators.

[Extension Methods](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)<br>
[What is LINQ](https://stackoverflow.com/questions/471502/what-is-linq-and-what-does-it-do)<br>
[LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)

#### What are the advantages and disadvantages of lazy loading?

Advantages:<br>

- Minimizes start up time of the application.
- Application consumes less memory because of on-demand loading.
- Unnecessary database SQL execution is avoided.

Disadvantages:<br>

- The only one disadvantage is that the code becomes complicated. As we need to do checks if the loading is needed or not, there is a slight decrease in performance.

[Lazy Loading Explained](https://www.codeproject.com/Articles/652556/Can-you-explain-Lazy-Loading)<br>
[What Is](https://www.imperva.com/learn/performance/lazy-loading/)

#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?

When you use the yield contextual keyword in a statement, you indicate that the method, operator, or get accessor in which it appears is an iterator. Using yield to define an iterator removes the need for an explicit extra class when you implement the IEnumerable and IEnumerator pattern for a custom collection type.

[Yield](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/yield)

#### What are attributes in C#? Give some examples of usage of them.

Attribute:<br>

Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth). After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called reflection.

Attributes add metadata to your program. Metadata is information about the types defined in a program. All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly. You can add custom attributes to specify any additional information that is required. For more information, see, Creating Custom Attributes (C#).

You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.

Attributes can accept arguments in the same way as methods and properties.

Your program can examine its own metadata or the metadata in other programs by using reflection. For more information, see Accessing Attributes by Using Reflection (C#).

Attributes provide a way of associating information with code in a declarative way. They can also provide a reusable element that can be applied to a variety of targets.

[Attributes](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/)<br>
[Use Attributes](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/attributes)

#### By what mechanism does NUnit know what methods to test?

By attributes, see the link for more precise info.

[NUnit Attributes](https://github.com/nunit/docs/wiki/Attributes)

#### What is the GAC? What problem does it solve?

Global Assembly Cache:<br>
Each computer where the common language runtime is installed has a machine-wide code cache called the global assembly cache. The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.

You should share assemblies by installing them into the global assembly cache only when you need to. As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required. In addition, it is not necessary to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.

[Explanation](https://stackoverflow.com/questions/1268342/what-is-the-gac-in-net)<br>
[GAC](https://docs.microsoft.com/en-us/dotnet/framework/app-domains/gac?redirectedfrom=MSDN)

#### What is the largest number you can work with in C#?

[Largest Number](https://stackoverflow.com/questions/24874495/largest-data-type-to-store-numbers)

### Database

#### How can you connect your application to a database server? What are the possible ways?

Connections are built by supplying an underlying driver or provider with a connection string, which is a way of addressing a specific database or server and instance as well as user authentication credentials (for example, Server=sql_box;Database=Common;User ID=uid;Pwd=password;).
Once a connection has been built it can be opened and closed at will, and properties (such as the command time-out length, or transaction, if one exists) can be set.
The Connection String is composed of a set of key/value pairs as dictated by the data access interface and data provider being used.

Many databases (such as PostgreSQL) only allow one operation to be performed at a time on each connection.
If a request for data (a SQL Select statement) is sent to the database and a result set is returned, the connection is open but not available for other operations until the client finishes consuming the result set.
Other databases, like SQL Server 2005 (and later), do not impose this limitation.
However, databases that provide multiple operations per connection usually incur far more overhead than those that permit only a single operation task at a time.

[General](https://en.wikipedia.org/wiki/Database_connection)<br>
[Example](https://stackoverflow.com/questions/42541373/how-does-an-application-connect-to-a-sql-server-database)

#### What do you know about database normalization?

Normalization is used for mainly two purposes:

- Eliminating redundant(useless) data.
- Ensuring data dependencies make sense i.e data is logically stored.

Database normalization is a process used to organize a database into tables and columns.  
The idea is that a table should be about a specific topic and that and only supporting topics included.

By limiting a table to one purpose you reduce the number of duplicate data contained within your database.
This eliminates some issues stemming from database modifications.

[Example](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/)<br>
[Forms and specifics](https://en.wikipedia.org/wiki/Database_normalization)
