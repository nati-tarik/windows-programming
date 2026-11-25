# WINDOW PROGRAMMING

## Pre-Mid Semester Assignment

### Group Members

    No. Full Name           Student ID
  ----- ------------------- -------------
      1 Bethel Dawit        UUR00803/17
      2 Kalkidan Araya      UUR00985/16
      3 Natnael Bizuayehu   UUR00785/17

------------------------------------------------------------------------

# Part 1: Software Development, Methodologies and Principles

## Question 1: Choosing the Right SDLC Model

**Answer:**

**A. Flight-control software**

For flight-control software, I recommend the Waterfall or V-Model
because the system requires high accuracy and safety. Its requirements
are usually clearly defined, and mistakes can put people's lives at
risk. Therefore, each development stage should be carefully planned,
tested, and approved before moving to the next stage.

**B. Food-delivery mobile application**

For a food-delivery application, I recommend the Agile model, especially
Scrum. Startups often face changing customer needs and market
conditions. Agile allows developers to release features in small stages,
receive user feedback, and make improvements quickly.

**How requirements, risks, and testing affect the choice**

Requirements, risks, and testing play an important role when choosing an
SDLC model. Stable requirements and high risks are better handled by
planned models such as Waterfall or V-Model. Changing requirements are
better suited to Agile. In safety-critical systems, testing must be
detailed and performed at every stage, while startup applications
benefit from continuous testing and user feedback.

## Question 2: The Hidden Trade-offs of Rapid Application Development (RAD)

**Answer:**

Rapid Application Development (RAD) focuses on building software quickly
through prototypes and continuous user feedback. However, reducing
planning can cause problems later.

First, without proper planning, the software may have a poor structure,
making it difficult to maintain and expand. Second, the system may not
handle a large number of users because scalability was not considered
from the beginning. Also, limited testing can lead to errors and
security problems.

RAD is suitable for small projects that need quick results, but it is
not the best choice for large or critical systems such as banking and
healthcare applications because they require strong security,
reliability, and proper planning.

## Question 3: Balancing Software Development Principles (DRY, KISS, YAGNI, SoC)

**Answer:**

Yes, following DRY and Separation of Concerns too much can sometimes
violate KISS and YAGNI.

DRY means avoiding repeated code, while Separation of Concerns means
dividing a program into different parts based on their responsibilities.
However, applying these principles unnecessarily can make a simple
program complicated.

For example, creating many classes, interfaces, and methods just to
perform a simple addition can make the code harder to understand and
maintain.

KISS encourages keeping the code simple, while YAGNI reminds developers
not to add features that are not currently needed.

Therefore, developers should balance these principles and choose a
simple solution that meets the actual requirements.

## Question 4: The Economics of Testing and Code Quality

**Answer:**

Fixing errors during the early stages of software development is cheaper
and easier than fixing them after deployment.

This is because errors found later may affect other parts of the system,
requiring more time, money, and effort to correct. After deployment,
errors can also affect users, cause data loss, and damage the reputation
of the organization.

Modern practices help reduce these costs:

-   **TDD (Test-Driven Development):** Developers write tests before
    writing the actual code. This helps identify problems early.
-   **Continuous Integration (CI):** Code is regularly combined and
    tested to find errors quickly.
-   **Code Review:** Other developers check the code and identify
    mistakes before it becomes part of the final system.

In conclusion, finding and fixing errors early improves software quality
and reduces development costs.

------------------------------------------------------------------------

# Part 2: .NET Architecture, C# and Windows Programming

## Question 5: MSIL, JIT, and the Platform Independence Paradox

**Answer:**

MSIL (Microsoft Intermediate Language) is CPU-independent, meaning it
can be converted into machine code for different processors. However,
traditional .NET Framework applications were platform-dependent because
the CLR (Common Language Runtime) and many .NET libraries were designed
mainly for Windows.

The JIT (Just-In-Time) compiler converts MSIL into native machine code
when the program runs.

Mono helped solve this problem by providing an alternative .NET runtime
that works on operating systems such as Linux and macOS. It allows .NET
applications to run on different platforms by providing the required
runtime and libraries.

Therefore, MSIL provides CPU independence, but a compatible runtime and
libraries are also needed for an application to work on different
operating systems.

## Question 6: Managed vs. Unmanaged Code and Language Interoperability

**Answer:**

Managed code runs under the .NET Common Language Runtime (CLR), which
provides services that make programs safer and more reliable.

The CLR helps prevent common problems through:

-   **Garbage Collection:** Automatically manages memory and removes
    unused objects.
-   **Type Safety:** Prevents invalid use of data types.
-   **Array Bounds Checking:** Prevents accessing elements outside an
    array's limits.
-   **Exception Handling:** Helps manage errors using try and catch.

C# and VB.NET can work together because both languages compile into MSIL
and follow the Common Type System (CTS). CTS provides common data types
such as Integer, String, and Boolean.

As a result, a class written in C# can be used in a VB.NET application
without major data conversion problems.

## Question 7: Solving DLL Hell: Assemblies, Manifests, and Namespaces

**Answer:**

DLL Hell happens when different applications depend on different
versions of the same DLL file. Installing a new version can sometimes
cause older applications to stop working.

.NET helps solve this problem through the following features:

-   **Assemblies:** Packages containing compiled code and other
    resources.
-   **Manifest:** Contains information about an assembly, including its
    name, version, and dependencies.
-   **Strong Names:** Give assemblies a unique identity and help protect
    their integrity.
-   **GAC (Global Assembly Cache):** Stores shared assemblies so
    different applications can use the required versions.
-   **Side-by-side execution:** Allows different versions of the same
    assembly to exist on one computer.

**Difference between Namespace and Assembly:**

A namespace is used to organize related classes and avoid naming
conflicts. An assembly is a compiled file, such as a DLL or EXE, used
for deployment and execution.

One assembly can contain several namespaces, and a namespace can exist
across multiple assemblies.

## Question 8: Abstraction in Data Access: ADO.NET vs. Entity Framework and LINQ

**Answer:**

ADO.NET requires developers to manually manage database connections,
write SQL queries, and convert database results into objects. This can
make the code longer and increase the chance of errors.

Entity Framework (EF) makes database operations easier by allowing
developers to work with database records as C# objects.

Its main advantages include:

-   **Automatic Mapping:** Converts database tables into C# classes.
-   **Less Code:** Reduces the need to write SQL queries manually.
-   **LINQ:** Allows developers to query data using C# syntax.
-   **Type Safety:** Helps identify some errors during compilation.
-   **Connection Management:** Handles many database connection tasks
    automatically.

However, Entity Framework also has disadvantages. It can have
performance overhead and gives developers less control over some complex
queries.

In conclusion, ADO.NET provides more direct control, while Entity
Framework makes database development easier and faster.

## Question 9: Under the Hood of Event-Driven Programming

**Answer:**

A console application normally executes instructions from top to bottom,
while a Windows Forms application waits for user actions such as button
clicks.

In Windows Forms, the program uses a message loop to keep running and
respond to user events.

When a user clicks a button, the following steps happen:

1.  The user clicks the button.
2.  Windows receives the mouse action and creates a message.
3.  The message is placed in the application's message queue.
4.  The message loop receives and processes the message.
5.  Windows Forms recognizes the action as a button click.
6.  The button's Click event is triggered.
7.  The event handler method is called.
8.  The instructions inside the event handler are executed.
9.  After execution, the program returns to the message loop and waits
    for another event.

Event-driven programming allows an application to respond to user
actions instead of following only a fixed sequence of instructions.
