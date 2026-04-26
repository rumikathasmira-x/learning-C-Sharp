# C# Programming Lecture Notes
---

## Table of Contents

1. [Introduction to Programming](#1-introduction-to-programming)
2. [C# Fundamentals](#2-c-fundamentals)
3. [Data Types & Variables](#3-data-types--variables)
4. [Type Casting](#4-type-casting)
5. [User Input & Output](#5-user-input--output)
6. [Operators](#6-operators)
7. [Control Flow](#7-control-flow)
8. [Loops](#8-loops)
9. [Arrays](#9-arrays)
10. [Methods](#10-methods)
11. [Object-Oriented Programming](#11-object-oriented-programming)
12. [Exception Handling](#12-exception-handling)
13. [String Interpolation](#13-string-interpolation)
14. [Practice Sessions & Lab Sheets](#14-practice-sessions--lab-sheets)

---

## 1. Introduction to Programming

### Key Definitions
| Term | Definition |
|------|------------|
| **Algorithm** | Step-by-step instructions to solve a problem |
| **Compiler** | Converts entire source code into machine-level instructions |
| **Interpreter** | Translates and executes code line-by-line |
| **Pseudocode** | Human-readable description of an algorithm |

### Pseudocode Structure
```
START
PRINT "Enter a number N:"
INPUT N
IF N > 0 THEN
    PRINT "Positive"
ELSE IF N < 0 THEN
    PRINT "Negative"
ELSE
    PRINT "Zero"
END IF
END
```

### Flowchart Symbols
- **Oval:** Start/End
- **Rectangle:** Process/Action
- **Diamond:** Decision
- **Parallelogram:** Input/Output

### Password Validation Flowchart Logic
```
START
valid = FALSE
WHILE valid == FALSE
    PRINT "Enter your password (min 6 chars)"
    INPUT password
    IF LENGTH(password) >= 6 THEN
        valid = TRUE
    ELSE
        PRINT "Password too short! Try again"
    END IF
END WHILE
PRINT "Password successfully set"
STOP
```

---

## 2. C# Fundamentals

### Pre-processor Directives
| Directive | Purpose |
|-----------|---------|
| `#define` | Define a symbol |
| `#undef` | Undefine a symbol |
| `#if` | Test a symbol for true |
| `#else` | Compound conditional with `#if` |
| `#error` | Generate an error at a specific location |
| `#warning` | Generate a warning at a specific location |

### Compiled vs Interpreted Languages
- **Compiled (C#):** Source → Compiler → Machine Code → Execute
- **Interpreted (Python):** Source → Interpreter executes line-by-line

### Visual Studio / VS Code Setup
- Install **C# Dev Kit** extension for VS Code
- Alternative: JetBrains Rider

---

## 3. Data Types & Variables

### Common Data Types
```csharp
// Integer
int age = 20;
int marks = 85;
int quantity = 5;

// Double (decimal)
double price = 1250.75;
double average = 78.5;
double height = 5.6;

// Character
char grade = 'A';
char gender = 'M';
char symbol = '#';

// String
string name = "Amal";
string city = "Colombo";
string message = "Welcome to C#";

// Boolean
bool isLoggedIn = true;
bool hasPermission = false;
bool isAdult = age >= 18;  // true
```

### Identifier Rules
- Can contain letters, digits, and underscore (`_`)
- Must begin with a letter or underscore
- Should start with lowercase letter
- Cannot contain whitespace
- Case-sensitive (`myVar` ≠ `myvar`)
- Cannot use reserved keywords (`int`, `double`, etc.)

### Multiple Variable Declaration
```csharp
int x, y, z;
int x = 5, y = 10, z = 15;
int a = 10, b = 20;
int sum = a + b;  // 30
```

---

## 4. Type Casting

### Using `Convert` Class
```csharp
// double → int
double a = 3.14;
int b = Convert.ToInt32(a);        // 3

// int → string
int e = 321;
string eValue = Convert.ToString(e);

// string → char
string g = "$";
char gValue = Convert.ToChar(g);

// string → bool
string c = "True";
bool cValue = Convert.ToBoolean(c);

// Check type
Console.WriteLine(b.GetType());    // System.Int32
```

---

## 5. User Input & Output

### Basic I/O
```csharp
// Output
Console.Write("Hello ");           // No newline
Console.WriteLine("World!");       // With newline

// Input
string name = Console.ReadLine();

// Input with conversion
int userAge = Convert.ToInt32(Console.ReadLine());
double userValue = Convert.ToDouble(Console.ReadLine());
```

### Example: Name and Age
```csharp
Console.Write("What is your name?: ");
string name = Console.ReadLine();
Console.WriteLine("Hello " + name);

Console.Write("Please enter your age: ");
int userAge = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("I am " + userAge + " years old");
```

---

## 6. Operators

### Arithmetic Operators
```csharp
int Apple = 5;

// Addition
Apple = Apple + 15;     // 20
Apple += 45;            // 65 (shorthand)
Apple++;                // 66 (increment by 1)

// Subtraction
Apple = Apple - 2;      // 64
Apple -= 2;             // 62
Apple--;                // 61

// Multiplication
Apple = Apple * 10;     // 610
Apple *= 4;             // 2440

// Division
Apple = Apple / 2;      // 1220
Apple /= 2;             // 610

// Modulus (remainder)
int remain = Apple % 3; // 1
```

> **Note:** Use `double` for precise decimal division.

### Comparison Operators (return `bool`)
| Operator | Meaning | Example (`a=6, b=9`) |
|----------|---------|----------------------|
| `==` | Equal to | `a == b` → `False` |
| `!=` | Not equal to | `a != b` → `True` |
| `>` | Greater than | `a > b` → `False` |
| `>=` | Greater than or equal | `a >= b` → `False` |
| `<` | Less than | `a < b` → `True` |
| `<=` | Less than or equal | `a <= b` → `True` |

### Logical Operators
```csharp
// AND (&&) - both must be true
Console.WriteLine(a != b && b == 3);  // False

// OR (||) - at least one true
Console.WriteLine(a != b || b == 2);  // True
```

---

## 7. Control Flow

### If-Else Statements
```csharp
Console.Write("Please enter your age: ");
int personAge = Convert.ToInt32(Console.ReadLine());

if (personAge >= 100)
{
    Console.WriteLine("You are too old!");
}
else if (personAge <= 0)
{
    Console.WriteLine("You are not born yet");
}
else if (personAge >= 18)
{
    Console.WriteLine("You are signed in!");
}
else
{
    Console.WriteLine("You must be older than 18");
}
```

### Switch Statements
```csharp
Console.Write("Which day is today?: ");
string day = Console.ReadLine();

switch (day)
{
    case "Monday":
        Console.WriteLine("It's Monday!");
        break;
    case "Tuesday":
        Console.WriteLine("It's Tuesday!");
        break;
    // ... other days
    default:
        Console.WriteLine("The value is not a day!!");
        break;
}
```

### Example: Color Picker
```csharp
Console.Write("Enter a number from 1 to 3: ");
string choice = Console.ReadLine();

switch (choice)
{
    case "1": Console.WriteLine("Red"); break;
    case "2": Console.WriteLine("Blue"); break;
    case "3": Console.WriteLine("Green"); break;
    default: Console.WriteLine("Invalid choice"); break;
}
```

---

## 8. Loops

### For Loop
```csharp
// Structure: (initialization; condition; increment)
for (int i = 0; i <= 10; i++)
{
    Console.WriteLine(i);
}

// Countdown
for (int i = 10; i > 0; i--)
{
    Console.WriteLine(i);
}
Console.WriteLine("Happy New Year!");
```

### Nested For Loops
```csharp
Console.Write("How many rows?: ");
int rows = Convert.ToInt32(Console.ReadLine());
Console.Write("How many columns?: ");
int cols = Convert.ToInt32(Console.ReadLine());
Console.Write("What symbol?: ");
string symbol = Console.ReadLine();

for (int a = 0; a < rows; a++)
{
    for (int b = 0; b < cols; b++)
    {
        Console.Write(symbol);
    }
    Console.WriteLine();  // New line after each row
}
```

### While Loop
```csharp
Console.Write("Enter your name: ");
string name = Console.ReadLine();

while (name == "")
{
    Console.Write("Enter your name: ");
    name = Console.ReadLine();
}
Console.WriteLine("Hello " + name);
```

### Break and Continue
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 4)
        continue;        // Skip current iteration

    if (i == 7)
        break;           // Exit loop completely

    Console.WriteLine(i + " Hello");
}
// Output: 0,1,2,3,5,6 (4 skipped, stopped at 7)
```

### Foreach Loop
```csharp
string[] cars = { "BMW", "Ferrari", "Mustang" };

foreach (string car in cars)
{
    Console.WriteLine(car);
}
```

---

## 9. Arrays

### Declaration & Initialization
```csharp
// Method 1: Direct initialization
string[] cars = { "Toyota", "BMW", "Mustang", "Benz" };

// Method 2: Declare size first
string[] cars = new string[5];
cars[0] = "A";
cars[1] = "B";
// ...

// Access elements
Console.WriteLine(cars[0]);     // Toyota
Console.WriteLine(cars[1]);     // BMW

// Update element
cars[3] = "Lamborghini";
```

### Loop Through Arrays
```csharp
// Using for loop
for (int i = 0; i < cars.Length; i++)
{
    Console.WriteLine(cars[i]);
}

// Using foreach
foreach (string car in cars)
{
    Console.WriteLine(car);
}
```

### Array of Objects
```csharp
Car[] garage = new Car[4];

garage[0] = new Car("Toyota");
garage[1] = new Car("Mustang");
garage[2] = new Car("BYD");
garage[3] = new Car("MUC");

// Access properties
Console.WriteLine(garage[0].model);

// Or initialize directly
Car[] garage = {
    new Car("Toyota"),
    new Car("Mustang"),
    new Car("BYD"),
    new Car("MUC")
};
```

---

## 10. Methods

### Basic Method
```csharp
static void Main(string[] args)
{
    SingHappyBirthday();
    SingHappyBirthday();
}

static void SingHappyBirthday()
{
    Console.WriteLine("Happy Birthday to you!");
    Console.WriteLine("Happy Birthday to you!");
    Console.WriteLine("Happy Birthday dear friend");
    Console.WriteLine("Happy Birthday to you!");
}
```

### Method with Parameters
```csharp
static void Main(string[] args)
{
    string name = "Sujani";
    SingHappyBirthday(name);
}

static void SingHappyBirthday(string name)
{
    Console.WriteLine("Happy Birthday dear " + name);
}
```

### Multiple Parameters
```csharp
static void Main(string[] args)
{
    string name = "Sujani";
    int age = 25;
    SingHappyBirthday(name, age);
}

static void SingHappyBirthday(string name, int age)
{
    Console.WriteLine("Happy Birthday dear " + name);
    Console.WriteLine("You are " + age + " years old");
}
```

### Return Values
```csharp
static void Main(string[] args)
{
    double result = Multiply(5, 6);
    Console.WriteLine("Result: " + result);
}

static double Multiply(double x, double y)
{
    return x * y;
}
```

### Method Overloading
> Same method name, different parameters (unique signature)

```csharp
static double Multiply(double x, double y)
{
    return x * y;
}

static double Multiply(double x, double y, double z)
{
    return x * y * z;
}

// Usage
Multiply(5, 6);      // Calls 2-param version
Multiply(5, 6, 7);   // Calls 3-param version
```

### Params Keyword
```csharp
static void Main(string[] args)
{
    double total = Checkout(500.45, 30.64, 100, 20.54);
    Console.WriteLine(total);  // 651.63
}

static double Checkout(params double[] prices)
{
    double total = 0;
    foreach (double price in prices)
    {
        total += price;
    }
    return total;
}
```

---

## 11. Object-Oriented Programming

### Classes & Objects
```csharp
// Human.cs
internal class Human
{
    public string name;
    public int age;

    public void Eat()
    {
        Console.WriteLine($"{name} is eating!");
    }

    public void Sleep()
    {
        Console.WriteLine($"{name} is sleeping!");
    }
}

// Program.cs
Human human1 = new Human();
human1.name = "Rumika";
human1.age = 19;
human1.Eat();       // Rumika is eating!
human1.Sleep();     // Rumika is sleeping!
```

### Constructors
```csharp
internal class Car
{
    // Fields
    string make;
    string model;
    int year;
    string color;

    // Constructor
    public Car(string make, string model, int year, string color)
    {
        this.make = make;
        this.model = model;
        this.year = year;
        this.color = color;
    }

    public void Drive()
    {
        Console.WriteLine($"You drive the {make} {model}");
    }
}

// Usage
Car car1 = new Car("Toyota", "ABC", 2026, "Red");
car1.Drive();  // You drive the Toyota ABC
```

### Overloaded Constructors
```csharp
internal class Pizza
{
    string bread, sauce, cheese, topping;

    // Constructor 1: Full pizza
    public Pizza(string bread, string sauce, string cheese, string topping)
    {
        this.bread = bread;
        this.sauce = sauce;
        this.cheese = cheese;
        this.topping = topping;
    }

    // Constructor 2: No topping
    public Pizza(string bread, string sauce)
    {
        this.bread = bread;
        this.sauce = sauce;
    }

    // Constructor 3: Bread only
    public Pizza(string bread)
    {
        this.bread = bread;
    }
}
```

### Static Modifier
```csharp
internal class Car
{
    string model;
    public static int numberOfCars;  // Shared across all objects

    public Car(string model)
    {
        this.model = model;
        numberOfCars++;  // Increment shared counter
    }
}

// Usage
Car car1 = new Car("ABC");
Car car2 = new Car("DEF");
Car car3 = new Car("GHI");
Console.WriteLine(Car.numberOfCars);  // 3
```

### Inheritance
```csharp
// Base/Parent Class
internal class Vehicle
{
    public int speed = 50;

    public void Go()
    {
        Console.WriteLine("This vehicle is moving!");
    }
}

// Derived/Child Classes
internal class Bike : Vehicle
{
    public int wheels = 2;
}

internal class Car : Vehicle
{
    public int wheels = 4;
}

// Usage
Car car1 = new Car();
Console.WriteLine(car1.speed);   // 50 (inherited)
Console.WriteLine(car1.wheels);  // 4 (own)
car1.Go();                       // This vehicle is moving!
```

### Method Overriding
```csharp
// Parent Class
internal class Animal
{
    public virtual void Speak()     // virtual = can be overridden
    {
        Console.WriteLine("Animal goes .....");
    }
}

// Child Classes
internal class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("A Dog goes baww");
    }
}

internal class Cat : Animal
{
    public override void Speak()
    {
        Console.WriteLine("A Cat goes meow");
    }
}

// Usage
Animal animal1 = new Animal();
Dog dog1 = new Dog();
Cat cat1 = new Cat();

animal1.Speak();  // Animal goes .....
dog1.Speak();     // A Dog goes baww
cat1.Speak();     // A Cat goes meow
```

### Polymorphism
```csharp
Vehicle[] vehicles = { car1, bicycle1, boat1 };

foreach (Vehicle vehicle in vehicles)
{
    vehicle.Go();  // Calls the overridden method for each type
}
// Output:
// Go Car!
// Go Bicycle!
// Go Boat!
```

### Interfaces
```csharp
// Interface declaration (no implementation)
internal interface iPrey
{
    void feel();
}

internal interface iPredator
{
    void hunt();
}

// Implementation
internal class Rabbit : iPrey
{
    public void feel()
    {
        Console.WriteLine("Rabbit runs away!");
    }
}

internal class Fish : iPrey, iPredator  // Multiple interfaces
{
    public void feel()
    {
        Console.WriteLine("Searching for fish food");
    }

    public void hunt()
    {
        Console.WriteLine("Fish swims away");
    }
}
```

### Objects as Arguments
```csharp
public static void changeColor(Car car, string color)
{
    car.color = color;  // Modifies the original object
}

// Usage
Car car1 = new Car("DEF", "Blue");
changeColor(car1, "Black");
Console.WriteLine(car1.color);  // Black
```

---

## 12. Exception Handling

```csharp
try
{
    Console.Write("Enter a number: ");
    int num1 = Convert.ToInt32(Console.ReadLine());
    Console.Write("Enter another number: ");
    int num2 = Convert.ToInt32(Console.ReadLine());

    int result = num1 / num2;
    Console.WriteLine("Result: " + result);
}
catch (FormatException e)
{
    Console.WriteLine("Please enter ONLY numbers!");
}
catch (DivideByZeroException e)
{
    Console.WriteLine("You cannot divide by ZERO!");
}
catch (Exception e)
{
    Console.WriteLine("Something went wrong!");
}
finally
{
    Console.WriteLine("-- Thank you for visiting --");
}
```

| Block | Purpose |
|-------|---------|
| `try` | Code that might cause an error |
| `catch` | Handle specific errors |
| `finally` | Always executes (cleanup) |

---

## 13. String Interpolation

```csharp
string firstName = "Rumika";
string lastName = "Thasmira";
int age = 19;

// Old way
Console.WriteLine("Hello " + firstName + " " + lastName);

// New way (like Python f-strings)
Console.WriteLine($"Hello {firstName} {lastName}");
Console.WriteLine($"You are {age} years old!");
```

---

## 14. Practice Sessions & Lab Sheets

### Common Patterns

**Username Validation:**
```csharp
Console.Write("Give your username: ");
string userAnswer = Console.ReadLine();

if (userAnswer == "rumika-thasmira")
    Console.WriteLine("Welcome aboard!!");
else if (userAnswer == "")
    Console.WriteLine("You need to enter a username");
else
    Console.WriteLine("Wrong username!");
```

**Password Loop:**
```csharp
Console.Write("Passcode: ");
string userPass = Console.ReadLine();

while (userPass != "988L")
{
    Console.Write("Passcode: ");
    userPass = Console.ReadLine();
}
Console.WriteLine("Access Granted!");
```

**Odd or Even:**
```csharp
Console.Write("Enter a number: ");
int num = Convert.ToInt32(Console.ReadLine());

if (num % 2 == 0)
    Console.WriteLine("It's an Even number!");
else
    Console.WriteLine("It's an Odd number!");
```

### Lab Sheet Solutions Summary

| Lab | Key Concepts |
|-----|-------------|
| **Lab 1** | VS Installation, basic output |
| **Lab 2** | Variables, displaying student info, pen cost calculation |
| **Lab 3** | Comments, escape sequences (`\t`, `\n`), user input |
| **Lab 4** | If-else, switch, for loops, nested loops, while loops, arrays |
| **Lab 5** | Methods, return values, method overloading |
| **Lab 6** | Debugging errors, proper variable naming |

### Self-Study Assignments
- foreach loop exercises (arrays)
- Method creation with parameters
- Return keyword practice
- Method overloading challenges

---

## Quick Reference

### Console Methods
| Method | Description |
|--------|-------------|
| `Console.Write()` | Print without newline |
| `Console.WriteLine()` | Print with newline |
| `Console.ReadLine()` | Read string input |
| `Console.ReadKey()` | Wait for key press |

### Escape Sequences
| Sequence | Meaning |
|----------|---------|
| `\n` | New line |
| `\t` | Tab space |

### Access Modifiers
| Modifier | Access |
|----------|--------|
| `public` | Anywhere |
| `private` | Within class only |
| `internal` | Within assembly |
| `static` | Belongs to class, not instance |

---
