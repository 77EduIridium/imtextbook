[< Back](readme.md)  

# Introduction to C# Programming

Welcome to this comprehensive textbook on C# programming within the .NET ecosystem. This book is designed for students who are beginning their journey into object-oriented programming with C#. Throughout this course, you'll learn the fundamental concepts of C#, including data types, control structures, methods, classes, interfaces, and more. We'll also explore how to interact with the .NET CLI and handle command-line arguments.

C# is a modern, versatile programming language developed by Microsoft as part of the .NET framework. It combines the power of object-oriented programming with simplicity and readability, making it an excellent choice for developing applications ranging from console programs to web applications and games.

## What You'll Learn

By the end of this textbook, you'll be able to:

- Understand basic C# syntax and data types
- Control program flow using conditional statements and loops
- Define and use methods with different modifiers
- Create and work with classes, interfaces, and inheritance
- Organize code using namespaces
- Handle command-line arguments
- Use .NET CLI commands for project management

## Prerequisites

This textbook assumes you have basic knowledge of programming concepts. Familiarity with another programming language will be helpful but is not required. You'll need:

- A computer with Windows, macOS, or Linux
- .NET SDK installed (download from dotnet.microsoft.com)
- A code editor (Visual Studio Code is recommended)

## Getting Started

To install the .NET SDK, visit the official Microsoft website and download the latest version for your operating system. Once installed, open a terminal and run:

```
dotnet --version
```

If you see a version number, you're ready to start coding!

## Chapter Overview

1. **Basic Syntax and Data Types**: Understanding variables, types, and basic operations
2. **Control Structures**: Making decisions with if-else and switch statements
3. **Methods**: Creating reusable code blocks
4. **Classes and Object-Oriented Programming**: Building complex programs with OOP concepts
5. **Namespaces and Assemblies**: Organizing and packaging your code
6. **Command-Line Arguments and .NET CLI**: Interacting with your programs and development tools

Each chapter includes examples and exercises to reinforce your learning. Let's begin our journey into C# programming!

# Chapter 1: Basic Syntax and Data Types

In this chapter, we'll explore the fundamental building blocks of C# programs: variables, data types, and basic syntax. Understanding these concepts is crucial before moving on to more complex topics.

## Variables and Data Types

A variable is a named location in memory that stores a value. In C#, you must declare the type of data a variable will hold before using it.

### Primitive Data Types

C# supports several built-in data types:

- `int`: Integer numbers (e.g., 42)
- `double`: Floating-point numbers with decimal places (e.g., 3.14)
- `char`: Single characters (e.g., 'A')
- `string`: Sequences of characters (e.g., "Hello World")
- `bool`: Boolean values (true or false)

### Declaring Variables

```csharp
int age = 25;
double height = 1.75;
char grade = 'A';
string name = "John Doe";
bool isStudent = true;
```

## Operators

C# provides various operators for performing operations on variables:

### Arithmetic Operators
- `+` : Addition
- `-` : Subtraction
- `*` : Multiplication
- `/` : Division
- `%` : Modulo (remainder)

### Comparison Operators
- `==` : Equal to
- `!=` : Not equal to
- `<` : Less than
- `>` : Greater than
- `<=` : Less than or equal to
- `>=` : Greater than or equal to

### Logical Operators
- `&&` : Logical AND
- `||` : Logical OR
- `!` : Logical NOT

## Type Conversion

Sometimes you need to convert between different data types. C# provides two main ways:

1. **Implicit conversion**: Automatic, when no data loss occurs
2. **Explicit conversion** (casting): Manual, using parentheses

```csharp
int number = 10;
double decimalNumber = number;  // Implicit conversion

double pi = 3.14159;
int approximatePi = (int)pi;   // Explicit conversion (loses precision)
```

## The `sizeof` Operator

The `sizeof` operator returns the size of a data type in bytes:

```csharp
Console.WriteLine($"Size of int: {sizeof(int)} bytes");    // 4 bytes
Console.WriteLine($"Size of double: {sizeof(double)} bytes"); // 8 bytes
```

## Exercise

Write a program that declares variables of different types, performs some calculations, and displays the results. Also, demonstrate the `sizeof` operator for various data types.

# Chapter 2: Control Structures

Control structures allow your program to make decisions and repeat actions. This chapter covers conditional statements and loops.

## Conditional Statements

### If-Else Statements

The `if-else` statement executes different code blocks based on conditions:

```csharp
int age = 18;

if (age >= 18)
{
    Console.WriteLine("You are an adult.");
}
else
{
    Console.WriteLine("You are a minor.");
}
```

You can chain multiple conditions using `else if`:

```csharp
int score = 85;

if (score >= 90)
{
    Console.WriteLine("Grade: A");
}
else if (score >= 80)
{
    Console.WriteLine("Grade: B");
}
else if (score >= 70)
{
    Console.WriteLine("Grade: C");
}
else
{
    Console.WriteLine("Grade: F");
}
```

### Switch Statements

The `switch` statement is useful when you need to compare a variable against multiple values:

```csharp
int dayOfWeek = 3;
string dayName;

switch (dayOfWeek)
{
    case 1:
        dayName = "Monday";
        break;
    case 2:
        dayName = "Tuesday";
        break;
    case 3:
        dayName = "Wednesday";
        break;
    case 4:
        dayName = "Thursday";
        break;
    case 5:
        dayName = "Friday";
        break;
    case 6:
        dayName = "Saturday";
        break;
    case 7:
        dayName = "Sunday";
        break;
    default:
        dayName = "Invalid day";
        break;
}

Console.WriteLine($"Day {dayOfWeek} is {dayName}");
```

## Loops

Loops allow you to repeat code multiple times.

### For Loop

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine($"Iteration {i}");
}
```

### While Loop

```csharp
int counter = 0;
while (counter < 5)
{
    Console.WriteLine($"Counter: {counter}");
    counter++;
}
```

### Do-While Loop

```csharp
int number;
do
{
    Console.Write("Enter a positive number: ");
    number = int.Parse(Console.ReadLine());
} while (number <= 0);
```

## Exercise

Create a program that asks the user for their age and determines whether they can vote, drive, or drink alcohol based on typical age requirements. Use both if-else and switch statements in your solution.

# Chapter 3: Methods

Methods are reusable blocks of code that perform specific tasks. This chapter covers how to define and use methods in C#.

## Method Declaration

A method consists of several parts:

```csharp
access_modifier return_type method_name(parameters)
{
    // Method body
    return value; // If return type is not void
}
```

### Access Modifiers
- `public`: Accessible from anywhere
- `private`: Accessible only within the same class
- `protected`: Accessible within the same class and derived classes
- `internal`: Accessible within the same assembly

### Return Types
- `void`: Method doesn't return a value
- Any data type: Method returns a value of that type

### Static Methods

Static methods belong to the class rather than instances of the class:

```csharp
public static void PrintMessage()
{
    Console.WriteLine("Hello from a static method!");
}
```

### Methods with Return Values

```csharp
public static int AddNumbers(int a, int b)
{
    return a + b;
}
```

### Methods with Parameters

```csharp
public static void GreetUser(string name, int age)
{
    Console.WriteLine($"Hello, {name}! You are {age} years old.");
}
```

## Calling Methods

To use a method, you call it by its name followed by parentheses:

```csharp
PrintMessage(); // Calling a static method

int result = AddNumbers(5, 3);
Console.WriteLine($"5 + 3 = {result}");

GreetUser("Alice", 25);
```

## Method Overloading

You can define multiple methods with the same name but different parameters:

```csharp
public static int Multiply(int a, int b)
{
    return a * b;
}

public static double Multiply(double a, double b)
{
    return a * b;
}
```

## Exercise

Create a calculator class with methods for basic arithmetic operations. Implement method overloading for addition and multiplication to handle both integers and doubles.

# Chapter 4: Classes and Object-Oriented Programming

Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects," which can contain data and code. This chapter introduces classes, interfaces, inheritance, and other OOP concepts.

## Classes

A class is a blueprint for creating objects:

```csharp
public class Person
{
    // Fields
    public string Name;
    public int Age;

    // Constructor
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Method
    public void Introduce()
    {
        Console.WriteLine($"Hi, I'm {Name} and I'm {Age} years old.");
    }
}
```

## Objects

Objects are instances of classes:

```csharp
Person person1 = new Person("Alice", 25);
Person person2 = new Person("Bob", 30);

person1.Introduce(); // Output: Hi, I'm Alice and I'm 25 years old.
person2.Introduce(); // Output: Hi, I'm Bob and I'm 30 years old.
```

## Inheritance

Inheritance allows a class to inherit properties and methods from another class:

```csharp
public class Student : Person
{
    public string Major;

    public Student(string name, int age, string major) : base(name, age)
    {
        Major = major;
    }

    public void Study()
    {
        Console.WriteLine($"{Name} is studying {Major}.");
    }
}
```

## Interfaces

An interface defines a contract that classes must implement:

```csharp
public interface IShape
{
    double CalculateArea();
    double CalculatePerimeter();
}

public class Circle : IShape
{
    public double Radius { get; set; }

    public Circle(double radius)
    {
        Radius = radius;
    }

    public double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }

    public double CalculatePerimeter()
    {
        return 2 * Math.PI * Radius;
    }
}
```

## Abstract Classes and Methods

Abstract classes cannot be instantiated and may contain abstract methods:

```csharp
public abstract class Animal
{
    public string Name { get; set; }

    public Animal(string name)
    {
        Name = name;
    }

    public abstract void MakeSound();

    public virtual void Eat()
    {
        Console.WriteLine($"{Name} is eating.");
    }
}

public class Dog : Animal
{
    public Dog(string name) : base(name) { }

    public override void MakeSound()
    {
        Console.WriteLine($"{Name} says Woof!");
    }

    public override void Eat()
    {
        Console.WriteLine($"{Name} is eating dog food.");
    }
}
```

## Virtual and Override

The `virtual` keyword allows methods to be overridden in derived classes, while `override` implements the overridden method:

```csharp
public class BaseClass
{
    public virtual void DisplayMessage()
    {
        Console.WriteLine("Message from BaseClass");
    }
}

public class DerivedClass : BaseClass
{
    public override void DisplayMessage()
    {
        Console.WriteLine("Message from DerivedClass");
    }
}
```

## Exercise

Create a hierarchy of classes representing different types of vehicles. Implement interfaces for vehicles that can fly or swim, and use abstract classes for common vehicle properties.

# Chapter 5: Namespaces and Assemblies

Namespaces help organize code and prevent naming conflicts. Assemblies are the physical files containing compiled code.

## Namespaces

A namespace is a container for related classes and other types:

```csharp
namespace MyCompany.Utilities
{
    public class MathHelper
    {
        public static int Add(int a, int b)
        {
            return a + b;
        }
    }
}

namespace MyCompany.Graphics
{
    public class DrawingHelper
    {
        public static void DrawCircle()
        {
            Console.WriteLine("Drawing a circle...");
        }
    }
}
```

## Using Namespaces

To use types from a namespace, you can either fully qualify the name or use a `using` directive:

```csharp
using MyCompany.Utilities;
using MyCompany.Graphics;

class Program
{
    static void Main()
    {
        int result = MathHelper.Add(5, 3);
        DrawingHelper.DrawCircle();

        // Or fully qualified:
        // int result = MyCompany.Utilities.MathHelper.Add(5, 3);
    }
}
```

## Assemblies

An assembly is a compiled code library. In .NET, assemblies are .dll or .exe files. You can reference external assemblies to use their types:

```csharp
using System.Data.SqlClient;

// Now you can use SqlConnection, SqlCommand, etc.
```

## Exercise

Create a simple library project with utility classes organized in namespaces. Then create a console application that references this library and uses its classes.

# Chapter 6: Command-Line Arguments and .NET CLI

This chapter covers how to work with command-line arguments and use the .NET CLI for project management.

## Command-Line Arguments

The `Main` method can accept an array of strings representing command-line arguments:

```csharp
class Program
{
    static void Main(string[] args)
    {
        if (args.Length == 0)
        {
            Console.WriteLine("No arguments provided.");
            return;
        }

        Console.WriteLine($"Number of arguments: {args.Length}");
        for (int i = 0; i < args.Length; i++)
        {
            Console.WriteLine($"Argument {i}: {args[i]}");
        }
    }
}
```

## Parsing Command-Line Arguments

A common pattern is to parse arguments with flags:

```csharp
class Program
{
    static void Main(string[] args)
    {
        string name = "User";
        int age = 0;

        for (int i = 0; i < args.Length; i++)
        {
            switch (args[i])
            {
                case "--name":
                    if (i + 1 < args.Length)
                    {
                        name = args[i + 1];
                        i++; // Skip the next argument
                    }
                    break;
                case "--age":
                    if (i + 1 < args.Length && int.TryParse(args[i + 1], out int parsedAge))
                    {
                        age = parsedAge;
                        i++; // Skip the next argument
                    }
                    break;
            }
        }

        Console.WriteLine($"Name: {name}, Age: {age}");
    }
}
```

## .NET CLI Commands

The .NET CLI provides commands for creating, building, and running .NET projects.

### Creating a New Console Application

```
dotnet new console -n MyApp
cd MyApp
```

### Building a Project

```
dotnet build
```

### Running a Project

```
dotnet run
```

### Adding a Package Reference

```
dotnet add package Newtonsoft.Json
```

### Creating a Class Library

```
dotnet new classlib -n MyLibrary
```

### Publishing an Application

```
dotnet publish -c Release -r win-x64 --self-contained
```

## Exercise

Create a command-line application that accepts various options (like file paths, output formats, etc.) and performs different operations based on the provided arguments. Use the .NET CLI to build and run your application.

## Conclusion

Congratulations! You've completed this comprehensive introduction to C# programming. You've learned about basic syntax, data types, control structures, methods, object-oriented programming concepts, namespaces, command-line arguments, and .NET CLI usage.

Remember, programming is a skill that improves with practice. Continue exploring C# by building your own projects, contributing to open-source repositories, or learning about advanced topics like asynchronous programming, LINQ, and web development with ASP.NET.

Happy coding!