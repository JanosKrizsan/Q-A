# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
Abstract data-type that represents a number of countable items, where the same item might occur more than once.

Method examples include but not limited to:<br>
Python:<br>
append(), extend(), len(), remove(), clear()

JS:<br>
concat(), merge(), slice(), splice(), push(), pop()

#### What is the difference between a list/array and a set?
A set is an unordered collection with no duplicates, while a list/array may include duplicates. Upon converting to a set,the duplicates are removed. 

#### What is the purpose and methods of a dictionary/map data structure?
They are associative lists of key-value pairs. Data can easily be found by their respective keys.
Map() in Python may refer to a function which returns a new iterable from an existing iterable, with each item modified via an inner function's application.

Method examples include but not limited to:<br>
Map in JS:<br>
clear(), forEach(), keys(), values(), get(key), set(key, value)

Dictionary in Python:<br>
pop(), clear(), keys(), values(), items(), setdefault(), update()

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
```
FUNCTION Fibonacci(num_n):
"Prints Fibonacci numbers up to the given num_n."

    DECLARE THREE VARIABLES (num_one, num_two_ num_three)
    num_one = 0
    num_two = num_one
    num_three = 1
    FOR ( if integer count is less than num_n, INCREMENT on loop):
        num_one = num_two
        num_two = num_three 
        num_three = num_one + num_two
    END FOR    
    Print num_one
```

#### How do you find a max value in a list/array if you can’t use any built-in functions?
```
FUNCTION Max(list/array):
"Iterates through an array and returns the mathematically highest number"

    DECLARE ONE VARIABLE (highest_number)
    highest_number = 0
    FOR (iterate through the array items):
        IF (highest_number less than current_array_item)
            highest_number = current_array_item
        END IF    
    END FOR    
    RETURN highest_number
```

#### How do you find the average of values in a list/array if you can’t use any built-in functions?
```
FUNCTION Average(list/array):
"Iterates through an array and adds up its items, while counting them, then divides the sum
with the count and returns said number."

    DECLARE TWO VARIABLES (sum_of_items, number_of_items)
    sum_of_items = 0
    number_of_items = 0
    FOR (iterate through the array items)
        sum_of_items += current_array_item
        number_of_items += 1 
    END FOR    
    average = sum_ot_items / number_of_items
    RETURN average
```

#### What do we call an *in-place* sort?
It sorts the items within an iterable by modifying the order of the elements
only within said iterable. More simply, it does not use any additional space 
for sorting.

#### Explain an algorithm which sorts a list!

Bubble Sort:<br>
"It sorts a given array/list by swapping its adjacent elements. 
It iterates through the given array multiple times."

Quick-sort:<br>
"Divides the array/list into sub-arrays, low and high elements, then recursively sorts said
sub-arrays into further sub-arrays.

Insertion Sort:<br>
"A sort that builds the final array one item at a time. Consumes one element each repetition while
building a sorted output array, and repeats until no input elements are left from the origin array."

Merge Sort:<br>
"Similar to Quicksort, divides the array/list into sub-arrays. However, it calls itself on the sub-arrays
and merges them back together after."
```
    It essentially proceeds as such:
        1. Finds the middle point of the array, dividing it into two halves.
        2. Calls itself on the first half.
        3. Calls itself on the second half.
        4. Merges the previously referenced two halves.
```

### Programming paradigms - procedural

#### What is the call stack?
A data structure in memory for storing items in a last-in-first-out manner, so that the caller of the subroutine pushes the return address onto the stack and the called subroutine, after finishing, pops the return address off the call stack to transfer control to that return address.

Since the call stack is organized as a stack, the caller pushes the return address onto the stack, and the called subroutine, when it finishes, pulls or pops the return address off the call stack and transfers control to that address. If a called subroutine calls on yet another subroutine, it will push another return address onto the call stack, and so on, with the information stacking up and unstacking as the program dictates. If the pushing consumes all of the space allocated for the call stack, an error called a stack overflow occurs, generally causing the program to crash. Adding a subroutine's entry to the call stack is sometimes called "winding"; conversely, removing entries is "unwinding".

There is usually exactly one call stack associated with a running program (or more accurately, with each task or thread of a process), although additional stacks may be created for signal handling or cooperative multitasking (as with setcontext). Since there is only one in this important context, it can be referred to as the stack (implicitly, "of the task"); however, in the Forth programming language the data stack or parameter stack is accessed more explicitly than the call stack and is commonly referred to as the stack (see below).

In high-level programming languages, the specifics of the call stack are usually hidden from the programmer. They are given access only to a set of functions, and not the memory on the stack itself. This is an example of abstraction. Most assembly languages, on the other hand, require programmers to be involved with manipulating the stack. The actual details of the stack in a programming language depend upon the compiler, operating system, and the available instruction set.

#### What is “Stack overflow”?
In software, a stack overflow occurs if the call stack pointer exceeds the stack bound. The call stack may consist of a limited amount of address space, often determined at the start of the program. The size of the call stack depends on many factors, including the programming language, machine architecture, multi-threading, and amount of available memory. When a program attempts to use more space than is available on the call stack (that is, when it attempts to access memory beyond the call stack's bounds, which is essentially a buffer overflow), the stack is said to overflow, typically resulting in a program crash.

#### What are the main parts of a function?
Name, parameters, statements within the body. With the arrow function in JS or lambda in Python, and expression can be provided
instead of statements.

We could define a default for our paremeters, or define them as Rest Parameters (args, ...theArgs etc. ).

### Programming languages - Python  

#### How do you use a dictionary in Python?
If and when we require key-value pairs, such as:
Define an empty one or use a constructor:
`dict = {} | dict(X)`

Define a specific dictionary:
`dict = {"apple": 1, "carrot" : "why"}`

Select keys, values, or items:
`dict.keys() | dict.values() | dict.items()`

Dictionary comprehension:
`{key: value for key, value in dict.items()}`

#### What does it mean that an object is immutable in Python?
It means that your dreams will be shattered if you wish to change the state or
contents of said object.

#### What is a conditional expression in Python?
"It is a path of execution which is dependent on certain... conditions."

```
If true:
    do something
else if this is true:
    do this instead 
else if none of the above are true:
    do some other thing
```

 Ternary Expressions such as:
`TRUE if EXPRESSION else FALSE`

#### What are different types of arguments in Python?
Default Arguments which hold default values and are pre-defined.
Arbitrary Arguments, such as Args and Kwargs.
Positional Arguments, which need to be passed in their respective positions.
Keyword Arguments, which are passed with their respective keys, their position does not matter.

#### What is variable shadowing? (context: variable scope)
Variable shadowing occurs when a variable declared within a certain scope has the same name as a variable declared in an outer scope.This outer variable is said to be shadowed by the inner variable, while the inner identifier is said to mask the outer identifier. This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
If based on condition, you could be able to delete a specific item from the list that fulfills the condition.
By accident you might clear the list, or in the case of adding and depending on the type you might add the new item
to all existing items instead of the list itself as an element, or append it by the times of items length. Anything
could happen depending on what is your goal, or mistake.

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
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

#### If you need to access the iterator variable after a for loop, how would you do it in Python?
We can assign the value to a variable from outside the for loop, but that would only return the last value.
Otherwise we could append the values to a list for example within the for loop, to access all values.

We would be also able to embed functions, other loops etc. within our for loop thus being able to access the iterator variable.

#### What type of elements can a list contain in Python?
May contain any type of element, including other lists, tuples, sets, dictionaries etc.

#### What is slice operator in Python and how to use?
It is defined as `[beginning_index:ending_index]`.
We can slice the first 3 elements: `[0:4]`
We can reverse the list as such: `[::-1]`
Or we can slice starting from the end, called negative slicing: `[-4:-1]`

It is:
- Exclusive of the ending_index.
- Begins from 0, or -1 in case of negative slicing.

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
"+" may be used, it concatenates the two lists, making them into one.
```
a = [1, 2, 3, 4]
b = [1, 2]
c = a + b
c will be [1, 2, 3, 4, 1, 2]
```
#### What is the purpose of the in and not in membership operators in Python?
It checks if the iterable includes or does not, the item in question.
Returns a boolean.

#### What does the + operator mean when used with strings in Python?
"+" operator concatenates two strings, such as:
```
a = "cat"
b = "dog"
c = a + b
c will be "catdog"
```
#### Explain f strings in Python?
A new, and improved way of formatting strings, Literal String Interpolation.
Example:
```
value = 12
print(f" This is an F string with the value of {value}.")
will print "This is an F string with the value of 12."
```
#### Name 4 iterable types in Python!
List, dictionary, string, set, etc.

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
A comprehension is able to create a new iterable object with less code, basically in a shortened for loop, returning a whole new object.

A generator is an iterable created using a function with a yield statement. Generator expressions allow the creation of a generator on-the-fly without a yield keyword. But they don’t share the full power of generator created with a yield function. The generator yields one item at a time — thus it is more memory efficient than a list.

#### Does the order of the function definitions matter in Python? Why?
Yes, it does. As the file is read from top to bottom, a function must be defined above its call.

All functions must be defined before any are used.
However, the functions can be defined in any order, as long as all are defined before any executable code uses a function.
You don't need "forward declaration" because all declarations are completely independent of each other. As long as all declarations come before all executable code.
#### What does unpacking mean in Python?
Packing:
"When we are not certain with how many arguments will be passed to a function, we pack all arguments as a tuple while receiving arguments
using *. For receiving keyword arguments, we pack them as a dictionary and receive them using **."

Unpacking:
"Is used to pass a list or dictionary at its element level."

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
Example:
```
def myfunc():
    a = (1, 3, 4, 5, 5, 5)
    for item in a:
        print(item)

my_variable = myfunc

print(my_variable)

my_variable()
```
The above will print the function object, then call the function itself and print the elements of a.
If we assign the function as this:
```
def myfunc():
    a = (1, 3, 4, 5, 5, 5)

my_variable = myfunc()

print(my_variable)

my_variable()
```
It will print None, and a TypeError: "Nonetype" object is not callable.
## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
You may use prints to see the result of certain operations, functions etc.
Also the try-except-finally is great for catching errors.
There is also a built-in debugger in most IDEs (Integrated Development Environment), which is most useful.

#### What does step over, step into and step out mean while using the debugger?
```
Step into will cause the debugger to descend into any method calls on the current line. If there are multiple method calls, they'll be visited in order of execution; if there are no method calls, this is same as step over. This is broadly equivalent to following every individual line of execution as would be seen by the interpreter.

Step over proceeds to the next line in your current scope (i.e. it goes to the next line), without descending into any method calls on the way. This is generally used for following the logic through a particular method without worrying about the details of its collaborators, and can be useful for finding at what point in a method the expected conditions are violated.

Step out proceeds until the next "return" or equivalent - i.e. until control has returned to the preceding stack frame. This is generally used when you've seen all you need to at this point/method, and want to bubble up the stack a few layers to where the value is actually used.
```
In other words:
```
Step in: means that if there is a function call, it goes inside the function and you can see how the function is executing line by line till it returns and you go back to the next line right after the function call.

Step over: means that if there is a function call, it just executes it like a black box and returns the result, but you cannot see how the function was executed.

Step out: means that if you have Stepped in a function and now you want to skip seeing how the rest of the function is going to execute, you Step out and the function returns. Then, you go back to the next line, that is the line right after the function call.
```
#### How can you start to debug a program from a certain line using the debugger?
You need to create a breakpoint at the line, where the execution stops and you may inspect current processes
suspended. The debugger will always run the program as is, from the beginning.

### Version control

#### What are the advantages of using a version control system?
- Backup
- Understanding What Happened
- Restoring Previous Versions
- Storing Versions 
- Collaboration

[Distributed Version Control Systems](https://scriptcrunch.com/295/)<br>
[Why Use It?](https://www.git-tower.com/learn/git/ebook/en/command-line/basics/why-use-version-control)

#### What is the difference between the working directory, the staging area and the repository in git?
Working Directory:
Repositories created with the git init command are called working directories. The working directory is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify.

Staging Area:
The Staging Area is when git starts tracking and saving changes that occur in files. These saved changes reflect in the .git directory.

Repository:
The Local Repository is everything in your .git directory. Mainly what you will see in your Local Repository are all of your checkpoints or commits. It is the area that saves everything.

[Git Gud](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)<br>
[Git Basics](https://git-scm.com/book/en/v1/Getting-Started-Git-Basics)

#### What are remote repositories in git?
In contrast, remote repositories are hosted on a server that is accessible for all team members - most likely on the internet or on a local network.

Technically, a remote repository doesn't differ from a local one: it contains branches, commits, and tags just like a local repository. However, a local repository has a working copy associated with it: a directory where some version of your project's files is checked out for you to work with.
A remote repository doesn't have such a working directory: it only consists of the bare ".git" repository folder.

[Remote Repositories](https://www.git-tower.com/learn/git/ebook/en/command-line/remote-repositories/introduction)<br>
[Working With Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)

#### Why does a merge conflict occur?
Conflicts generally arise when two people have changed the same lines in a file, or if one developer deleted a file while another developer was modifying it. In these cases, Git cannot automatically determine what is correct. Conflicts only affect the developer conducting the merge, the rest of the team is unaware of the conflict. Git will mark the file as being conflicted and halt the merging process. It is then the developers' responsibility to resolve the conflict.

[Merge Conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
`git status` to check files changed
`git add xyz.file` or `git add -A` or `git add .` or `git add -u` to select change(s) to be added
`git commit -m "commit message"` to commit my changes
`git push` or `git push origin branch` to upload changes to remote repository

#### What does it mean atomic commits and descriptive commit messages?
The smallest possible changes are committed, separately.

You want to make commits that are generally smaller and that encompass only one irreducible feature, fix, or improvement.

#### What’s the difference between git and GitHub?
Git is a revision control system, a tool to manage your source code history.
GitHub is a hosting service for Git repositories.
Git is the tool, GitHub is the service for projects that use Git.

## Software design

### Clean code

#### What does clean code mean?
Clean code is code that is easy to understand and easy to change.

It is easy to understand the execution flow of the entire application, 
how the different objects collaborate with each other, the role and responsibility of each class, what each method does, what is the purpose of each expression and variable.

Clean code is obvious to other programmers, does not contain duplication, easier to maintain.

#### What steps do we usually do during a clean code refactoring?
- Rename ambiguous names, variables and functions
- Fix typos
- Remove magic numbers
- Extract each step of logic into functions if possible
- Remove duplicate code

1, The code should become cleaner.
2, New functionality shouldn't be created during refactoring.
3, All existing tests must pass after refactoring.
### Error handling

#### What is exception handling?
Handles when an error or exception occurs, in a language specific manner.
It might be due to programming error, user error, or user restrictions.
Informs the developer or the user of the exception and/or correct actions to take.

#### What are the basics of exception handling in Python?
- Raise Exceptions for said purpose.
- Use Try and Except - Else - Finally 
    Try executes, if an error is encountered, the Except block executes. Then, if specified,
    the Finally block of code will execute. The Else block will execute if no exception is found.

#### In which case should we catch an exception? Why?
When an error or exception occurs it can affect user experience and/or
how the program executes. It might even break the program. 

Exception handling assists us in debugging and fixing said errors. Furthermore,
for ease of testing.

#### What can/should we do with an exception in the ‘except’ block?
We may print out/log or ignore said exception. We may also raise a specific error in case of 
our exception.

#### What does the else and finally statement do in a try-except block in Python?
Else: executes if an exception is not raised
Finally: always executes at the end of the try-except block

##Software Development Methodologies

#### What is the main goal of a retrospective meeting?
[Retrospective Meeting](https://retromat.org/blog/what-is-a-retrospective/)

A retrospective is an opportunity to learn and improve. It is time set aside – outside of day-to-day routine – to reflect on past events and behaviors. In its simplest form you answer three questions:
    -What worked well?
    -What didn’t work well?
    -What are we going to try to do differently?

## Programming environment

### Unix

#### What is UNIX and what is Linux?
UNIX:
UNIX is a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, development starting in the 1970s at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others.

Unix systems are characterized by a modular design that is sometimes called the "Unix philosophy". This concept entails that the operating system provides a set of simple tools that each performs a limited, well-defined function with a unified filesystem (the Unix filesystem) as the main means of communication, and a shell scripting and command language (the Unix shell) to combine the tools to perform complex workflows. Unix distinguishes itself from its predecessors as the first portable operating system: almost the entire operating system is written in the C programming language, thus allowing Unix to reach numerous platforms.

Unix was originally meant to be a convenient platform for programmers developing software to be run on it and on other systems, rather than for non-programmers. The system grew larger as the operating system started spreading in academic circles, as users added their own tools to the system and shared them with colleagues.

[Further details on UNIX](http://www.unix.org/what_is_unix.html)

Linux:
Linux is a family of open source Unix-like operating systems based on the Linux kernel, an operating system kernel first released on September 17, 1991 by Linus Torvalds. Linux is typically packaged in a Linux distribution (distro).

Distributions include the Linux kernel and supporting system software and libraries, many of which are provided by the GNU Project. Many Linux distributions use the word "Linux" in their name, but the Free Software Foundation uses the name GNU/Linux to emphasize the importance of GNU software, causing some controversy.

[Further details on Linux](https://www.linux.com/what-is-linux)

#### What do we call the shell in Linux?
There is a Terminal in Linux which (most of the distros) uses the bash shell.

#### What does root means in a Linux environment?
Root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user and the superuser.

[Further info on Root](http://www.linfo.org/root.html)

#### How do you access your personal files in Linux?
Via either the Terminal or a file manager. In case your files are.
Usually they are under `/home/user` directory.

#### How can you install an application in Linux?
To install a specific package via the Terminal:
`sudo apt-get install package_name`

Can also be done via a package manager like the Ubuntu Software Manager.

It can also be done in this way:
```
wget link_to_package.deb
dpkg -i package.deb
```

#### What is package management in Linux, what are repositories?
Package Management:
Contemporary distributions of Linux-based operating systems install software in pre-compiled packages, which are archives that contain binaries of software, configuration files, and information about dependencies. Furthermore, package management tools keep track of updates and upgrades so that the user doesn’t have to hunt down information about bug and security fixes.

Without package management, users must ensure that all of the required dependencies for a piece of software are installed and up-to-date, compile the software from the source code (which takes time and introduces compiler-based variations from system to system), and manage configuration for each piece of software. Without package management, application files are located in the standard locations for the system to which the developers are accustomed, regardless of which system they’re using.

Package management systems attempt to solve these problems and are the tools through which developers attempt to increase the overall quality and coherence of a Linux-based operating system.

[For More, click me](https://www.linode.com/docs/tools-reference/linux-package-management/)

Repositories:
A collection of software for a Linux distribution on a server. You grab information on the software that is available on the server using the packaging tools (like apt-get) and download the software directly from those servers. As there are many folders in the web, they need to be kept separate. Ubuntu 5.10 will have different repositories than Ubuntu 5.04 or Mandriva or Redhat or Debian distros. Keeping the repositories split from each other ensures that your system will stay safe and not break due to incompatible software.

#### How do you navigate in the filesystem with the command line?
By the following commands you may move or edit directories:
- rmdir: The rmdir command will delete an empty directory. To delete a directory and all of its contents recursively, use rm -r instead.

- mkdir: The mkdir command will allow you to create directories. Example: "mkdir music" will create a directory called "music".

- cd: To move around the file system.
    Go to the root directory with `cd /`, to your home dir with `cd` or `cd~`. To navigate one directory up, use
    `cd ..`, to navigate to the previous directory, `cd -`.

To navigate through multiple levels of directory at once, specify the full directory path that you want to go to. For example, use, `cd /var/www` to go directly to the /www subdirectory of /var/. As another example, `cd ~/Desktop` will move you to the Desktop subdirectory inside your home directory.

#### What does the following commands do: mkdir, rm, cat, cp, touch?
```
mkdir -> creates a directory
rm -> deletes/removes a file
cp -> creates a copy of the file or directory
cat -> concatenates files, but can also create and copy files with content (depending on the shell redirection feature)
touch -> creates (a) new file(s) without content, changes access/modification time
```
#### How can you look up what does a command do in Linux if you have no internet connection?
One could use the -h or --help switches after a command, or look at the command's man page for more information, however
not all commands have a man page. In cases like these, info might provide some insight.

Also, the whatis command shows a one line summary of a command, taken from its man page.

#### What does the following commands do: head, tail, more, less?
```
head -> prints the top N number of lines of a given input, by default, the first 10 lines of specified files
tail -> prints the last N number of the lines of a given input, by default, the last 10 lines of specified files
more -> used to view the text files in the command prompt, displaying one screen at a time in case the file is large, also allowing scroll
less -> used to read contents of a text file one page at a time, has faster access since it loads page by page
```
#### How do you download a file from internet using the terminal?
To download a file to the current folder:
`wget "link_goes_here"`

To download it to a given folder:
`wget -P /home/Codecool/given_folder/ "link_goes_here"`

To also name it:
`wget -O /home/Codecool/given_folder/File_Name_Given "link_goes_here"`