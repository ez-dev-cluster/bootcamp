Object-Oriented Design (OOD) is the process of planning a system of interacting objects to solve a software problem using principles of Object-Oriented Programming (OOP). OOD involves identifying the classes, their responsibilities, and their relationships to design flexible and maintainable software.

### Key Concepts in Object-Oriented Design:

1. **Classes and Objects**
2. **Relationships between classes**
   - Inheritance
   - Association
   - Aggregation
   - Composition
3. **SOLID Principles**
4. **Design Patterns**

---

### **1. Classes and Objects**

In OOD, the first step is to identify the classes and objects needed to model the problem domain. Each class should have a clear responsibility and should represent a single concept or entity in the system.

#### Example:
For a car rental system, you might identify the following classes:
- `Car`
- `Customer`
- `Rental`
- `Payment`

Each of these classes will have attributes (fields) and behaviors (methods) relevant to the entity they represent.

---

### **2. Relationships Between Classes**

Classes interact with each other through relationships. Understanding these relationships is crucial in designing an effective object-oriented system.

#### **Inheritance**: 
Inheritance models an "is-a" relationship. A subclass inherits the attributes and methods of its parent class.

#### Example:

```csharp
public class Vehicle
{
    public string Make { get; set; }
    public string Model { get; set; }

    public void Start() { /* Start vehicle */ }
}

public class Car : Vehicle
{
    public int NumberOfDoors { get; set; }
}
```

In this example, `Car` inherits from `Vehicle`, which means that `Car` "is a" `Vehicle`.

---

#### **Association**: 
Association models a "has-a" relationship, where one class uses another class without implying ownership.

#### Example:

```csharp
public class Customer
{
    public string Name { get; set; }

    // Customer rents a car
    public void RentCar(Car car) 
    {
        Console.WriteLine($"{Name} rented {car.Make} {car.Model}");
    }
}
```

In this case, `Customer` has a relationship with `Car`, but neither owns the other.

---

#### **Aggregation**:
Aggregation is a special type of association where one class "contains" other objects, but those objects can exist independently.

#### Example:

```csharp
public class Team
{
    public List<Player> Players { get; set; } = new List<Player>();

    public void AddPlayer(Player player)
    {
        Players.Add(player);
    }
}
```

In this example, the `Team` class contains `Player` objects, but the players can exist independently of the team.

---

#### **Composition**: 
Composition is a stronger form of aggregation where one class owns the other. The lifecycle of the contained objects depends on the containing object.

#### Example:

```csharp
public class Engine
{
    public void Start() { /* Start engine */ }
}

public class Car
{
    private Engine engine = new Engine();

    public void StartCar()
    {
        engine.Start();
        Console.WriteLine("Car is running");
    }
}
```

In this case, `Car` owns the `Engine`, and the engine cannot exist independently of the car.

---

### **3. SOLID Principles**

The **SOLID** principles are guidelines for designing well-structured, maintainable, and flexible software systems. These principles encourage separation of concerns and reduce code dependencies.

1. **Single Responsibility Principle (SRP)**: A class should have only one reason to change, meaning it should have only one responsibility.

   - Example: In a car rental system, `Car` should only handle car-related logic, and `Rental` should manage rental-related logic.

2. **Open/Closed Principle (OCP)**: Classes should be open for extension but closed for modification. You should be able to add new functionality without changing the existing code.

   - Example: You could extend the `Car` class to create a `Truck` class without modifying the original `Car` class.

3. **Liskov Substitution Principle (LSP)**: Subtypes must be substitutable for their base types without altering the correctness of the program.

   - Example: If `Truck` inherits from `Vehicle`, you should be able to use a `Truck` wherever a `Vehicle` is expected.

4. **Interface Segregation Principle (ISP)**: Clients should not be forced to depend on methods they don’t use. It’s better to have small, specific interfaces.

   - Example: Instead of one large interface, you could have separate interfaces for rental services and payment processing.

5. **Dependency Inversion Principle (DIP)**: High-level modules should not depend on low-level modules; both should depend on abstractions.

   - Example: In a payment system, `Rental` should depend on an abstract `IPaymentProcessor` interface, not on a specific payment processor implementation like `PayPalPaymentProcessor`.

---

### **4. Design Patterns**

**Design patterns** are tried-and-tested solutions to common software design problems. Some commonly used patterns in OOP are:

- **Singleton**: Ensures that a class has only one instance and provides a global point of access to it.
- **Factory**: Creates objects without specifying the exact class to create.
- **Observer**: Allows objects to be notified of changes in other objects.
- **Strategy**: Defines a family of algorithms and makes them interchangeable.

#### Example: Factory Pattern

```csharp
public abstract class Car
{
    public abstract void Drive();
}

public class Sedan : Car
{
    public override void Drive()
    {
        Console.WriteLine("Driving a sedan.");
    }
}

public class Suv : Car
{
    public override void Drive()
    {
        Console.WriteLine("Driving an SUV.");
    }
}

public class CarFactory
{
    public Car CreateCar(string carType)
    {
        if (carType == "Sedan")
        {
            return new Sedan();
        }
        else if (carType == "SUV")
        {
            return new Suv();
        }
        else
        {
            throw new ArgumentException("Invalid car type");
        }
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        CarFactory factory = new CarFactory();

        Car myCar = factory.CreateCar("Sedan");
        myCar.Drive();
    }
}
```

This example uses the **Factory Pattern** to create objects of different car types (`Sedan`, `SUV`) without specifying the exact class in the main program.

---

### **Steps to Design an Object-Oriented System:**

1. **Identify Classes**: Based on the problem domain, identify the classes you need. Each class should represent an entity or concept.
   
2. **Define Responsibilities**: Assign responsibilities to each class. What data should it hold? What methods should it expose?

3. **Establish Relationships**: Define how the classes will interact. Use inheritance, composition, or association where appropriate.

4. **Follow SOLID Principles**: Ensure your design adheres to the SOLID principles for maintainability and flexibility.

5. **Use Design Patterns**: Apply design patterns where necessary to solve common problems in a standard, efficient way.

---

### **Example: Designing a Library Management System**

1. **Identify Classes**: 
   - `Book`, `Member`, `Librarian`, `Loan`

2. **Define Responsibilities**:
   - `Book`: Holds information about the book (title, author, ISBN).
   - `Member`: Handles the member details (name, member ID).
   - `Librarian`: Manages the book borrowing/return process.
   - `Loan`: Tracks book loans, due dates, and overdue penalties.

3. **Relationships**:
   - `Member` borrows a `Book` (association).
   - `Loan` aggregates the relationship between `Member` and `Book`.

4. **Applying SOLID Principles**:
   - Separate the loan handling logic into a `LoanManager` class to keep `Member` and `Book` focused on their own responsibilities (SRP).
   - Use an abstract `NotificationService` for sending alerts when a book is due (DIP).

5. **Applying Design Patterns**:
   - Use the **Factory Pattern** to create different types of notifications (e.g., email, SMS).

---

### **Summary**

- **Object-Oriented Design** focuses on identifying classes, defining their responsibilities, and establishing relationships between them.
- Following **SOLID principles** helps in building flexible and maintainable systems.
- **Design patterns** provide reusable solutions to common design problems, making your software more efficient and easier to understand.

---

### **Exercise:**
Design a basic shopping cart system. Identify the classes, establish relationships, and consider using some SOLID principles. Think about adding a `Payment` system and use a design pattern like **Factory** for different payment methods (credit card, PayPal, etc.).

Let me know if you need help with any part of the design!