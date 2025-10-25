## What are the fundamentals of oop concepts
1. Encapsulation | When an object's internal representation is hidden from view outside it's definition, it is said to be encapsulated. Only the necessary information is accessible, while the rest of the data implementation is hidden.
2. Abstraction | Abstraction is the process of identifying and eliminating irrelevant details from an object's critical behavior and data.
3. Inheritance | Inheritance is the ability to create new classes from existing ones. It is accomplished by gaining access to, altering, and extending the behavior of objects in the parent class.
4. Polymorphism | Polymorphism is a name that means "one name, many forms." It is accomplished using several methods with the same name but different implementations.

## What is common language runtume (CLR)
The common language runtime manages the execution of .NET programs (CLR). The just-in-time compiler translates compiled code into machine instructions. This is the program that the computer runs. CLR provides memory management, exception handling, type safety, and other services.

## What is managed and unmanaged code
1. Managed Code | Managed code is executed by the CLR (Common Language Runtime), on which all application code is based. The internet platform, because of the, it is regarded as managed. Internally, the net framework uses the garbage collector to clear out unused memory
2. Unmanaged Code | Unmanaged code is any code executed by an application runtime in a framework other than .NET. The application runtime will handle memory, security, and other performance operations.

## What is an interface
In C#, an interface is a class blueprint. It is like an abstract class in that all the methods declared within the interface are abstract. It cannot have a method body and cannot be instantiated. Instead, it is used to achieve multiple inheritances that class cant reach.

```csharp
namespace program
{
   public class odd
   {
      //members
   }

   public class even
   {
      //members
   }

   public class oddeven:odd:even
   {
      //access odd and even members
   }
}
```

## What are the different types of classes in C#
1. Partial Class | Its member can be divided or shared across multiple files. The keyword partial denotes it.
2. Abstract Class | An abstract class is one whose object cannot be instantiated. The only way to get the class is to inherit it. It must include at least one method. The keyword abstract denotes it.
3. Sealed Class | A sealed class cannot be inherited. To access the sealed class members, we must first create the class object. Then, the keyword sealed denotes it.
4. Static Class | This class does not allow inheritance. The class members are also static. The keyword static denotes this. This keyword instructs the compiler to look for any instances of the static class created by accident.

## Difference between the equality operator (==) and Equals() method in C#
The == operator and the equals() method compare two value or reference type data items. This article explains the fundamental distinction between the two. The comparison operator is the Equality Operator (==), and the equals() method compares the contents of a string. The == operator compares the identify of the reference, whereas the Equals() method compares only the reference.

## Explain code compilation in C#
In C#, code compilation consists of three steps:
- The C# compiler is compiling the source code into managed code
- Putting the newly created code together into assemblies
- The common language runtime (CLR) is being loaded. CLR is carrying out the assembly

## What are the differences between a class and a struct
Class
- Support inheritance
- Class is pass by reference (reference type)
- Members are private by default
- Suitable for larger complex objects
- Can use waste collector for memory management

Struct
- Does not support inheritance
- Struct is pass by copy (value type)
- Members are public by default
- Suitable for small isolated models
- Cannot use garbage collector and hence no memory management

## What is the difference between the virtual method and the abstract method
1. Virtual Method | A default implementation of the virtual method always required. It can, however, be overridden in the derived class, though this is not required. For example, the override keyword can be used to override it
2. Abstract Method | An abstract method has no implementation. Instead, it belongs to the abstract class. The derived class must implement the abstract form. Although an override keyword is not required in this case, it can be used

## Explain Namespace in C#
Namespace are employed int the organization of large code projects. For example, in C#, the most common namespace is "System". We can create our namespaces and use one namespace within another, known as nested namespaces.
The keyword "namespace" is used to identify them.

## What is the "using" statement in C#
- The "using" keyword indicates that the program uses the specified namespace.
- As an example, consider system. The system is a namespace in this context.
- The class console is defined in the system module. So, in our program, we can use a console. WriteLine("...") or ReadLine("...").

## Explain Abstraction
One of the OOP concepts is an abstraction. It is used to display only the class essential features and hide unnecessary information.

Let use a car as an example:

A car driver should be familiar with the vehicle details such as color, name, mirror, steering, gear, brake, and so on. He doesn't need to know about an internal engine and exhaust system.

As a result, abstraction aids in knowing what is required and concealing internal details from the outside world. Internal information can be hidden by declaring such parameters as private and using the private keyword.

## Explain Polymorphism
Polymorphism in programming refers to the same method but different implementations. It is classified into two types:

**Compile-time Polymorphism**: The compiler resolves the call in compile time polymorphism and is also referred to as static binding, and overloading.
**Runtime Polymorphism**: The compiler does not resolve the runtime polymorphism call and is also referred to as dynamic binding, late binding, and overriding.

## How is exception handling implemented ic C#
In C#, exception handling is accomplished using four keyword:
- **try**: Contains a block of code that will be checked for exceptions.
- **catch**: A program that catches an exception with the help of the exception handler.
- **finally**: It is a block of code written to run regardless of whether an exception is caught.
- **throw**: When a problem occurs, it throws an exception.

## What are C# I/O classes, what are the commonly used I/O classes
The **System.IO** namespace in C# contains classes used to perform various operations on files such as creating, deleting, opening, closing, and so on.
The following are some examples of commonly used I/O classes:
- File | Aids in the manipulation of a file.
- StreamWriter | This class is used to write characters to a stream.
- StreamReader | This class is used to read characters from a stream.
- StringWriter | This class is used to write a string buffer.
- StringReader | This class is used to read a string buffer.
- Path | Used to perform operations on the path information.

## What is stream reader / stream writer class
The namespace **System.IO** contains the classes stream reader and stream writer used to read or write character90, reader-based data.
- Member of StreamReader are : Close(), Read(), ReadLine().
- Member of StreamWriter are : Close(), Write(), WriteLine().

```csharp
class Program
{
   using(StreamReader SR = new StreamReader("C:\Read.txt"))
   {
   //code block to read
   }

   using(StreamWriter SW = new StreamWriter("C:\Read.txt"))
   {
   //code block to write
   }
}
```

## What is a destructor in C#
Destructor are used to clear memory and free resources. In C#, however, this is handled by the garbage collector on its own. Internally, System. GC.Collect() is used to clean up, but it may be necessary to implement destructors in some cases manually.

```csharp
~Vehicle()
{
   Console.WriteLine("...");
}
```

## What is an abstract class
- An abstract class is one that is denoted by the abstract keyword and can only be used as a base class.
- This class should always be inherited; it is impossible to create an instance of the class itself.
- If we dont want any program to create an object of a class, we can make such classes abstract.
- There are no implementations of any methods in the abstract class; they must be implemented in the child class.

```csharp
abstract class abs
{
   public void Addition();
}

class childclass : abs
{
   childclass cs1 = new childclass();
   int submission = cs1.Addition();
}
```

## What are boxing and unboxing code
Boxing Code | Boxing is the process of converting a value type to a reference type.
Example:
int Val1 = 50;
//Boxing
object boxingVal = Val1;

Unboxing Code | Unboxing is the explicit conversion of the same reference type back to the value type.
Example:
//Unboxing
int unboxing = int(boxingVal);

## What is the difference between continue and break statement
Break Statement | The break statement terminates the loop. It causes the programs control to exit the loop.
Continue Statement | The continue statement instructs the programs control to exit only the current iteration. However, it does not affect on the loop.
