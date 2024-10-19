# Exercise

Here are some basic exercises to help you practice working with **classes** and **objects** in C#. These exercises will involve creating simple classes, defining fields and methods, and working with objects.

### **Exercise 1: Create a `Person` Class**

**Task:**
1. Create a class named `Person` with the following fields:
   - `Name` (string)
   - `Age` (int)
2. Create a method named `Greet()` that prints a greeting message with the person's name and age.
3. Create a few `Person` objects in the `Main` method, set their names and ages, and call the `Greet()` method.

**Example Output:**
```
Hello, my name is John, and I am 25 years old.
Hello, my name is Alice, and I am 30 years old.
```

#### **Solution Example:**

```csharp
public class Person
{
    public string Name;  // Field for Name
    public int Age;      // Field for Age

    // Method to greet
    public void Greet()
    {
        Console.WriteLine($"Hello, my name is {Name}, and I am {Age} years old.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create Person objects
        Person person1 = new Person();
        person1.Name = "John";
        person1.Age = 25;
        person1.Greet();

        Person person2 = new Person();
        person2.Name = "Alice";
        person2.Age = 30;
        person2.Greet();
    }
}
```

---

### **Exercise 2: Create a `Car` Class**

**Task:**
1. Create a class named `Car` with the following fields:
   - `Make` (string)
   - `Model` (string)
   - `Year` (int)
2. Create a method `DisplayInfo()` that prints the car's make, model, and year.
3. In the `Main` method, create two `Car` objects, set their properties, and display their information.

**Example Output:**
```
Car: 2020 Toyota Corolla
Car: 2021 Honda Civic
```

#### **Solution Example:**

```csharp
public class Car
{
    public string Make;
    public string Model;
    public int Year;

    // Method to display car information
    public void DisplayInfo()
    {
        Console.WriteLine($"Car: {Year} {Make} {Model}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create Car objects
        Car car1 = new Car();
        car1.Make = "Toyota";
        car1.Model = "Corolla";
        car1.Year = 2020;
        car1.DisplayInfo();

        Car car2 = new Car();
        car2.Make = "Honda";
        car2.Model = "Civic";
        car2.Year = 2021;
        car2.DisplayInfo();
    }
}
```

---

### **Exercise 3: Create a `Rectangle` Class**

**Task:**
1. Create a class named `Rectangle` with the following fields:
   - `Length` (double)
   - `Width` (double)
2. Create methods:
   - `GetArea()` that returns the area of the rectangle.
   - `GetPerimeter()` that returns the perimeter of the rectangle.
3. In the `Main` method, create two `Rectangle` objects with different lengths and widths, and display their area and perimeter.

**Formula for area**: `Area = Length * Width`

**Formula for perimeter**: `Perimeter = 2 * (Length + Width)`

**Example Output:**
```
Rectangle 1: Area = 20, Perimeter = 18
Rectangle 2: Area = 50, Perimeter = 30
```

#### **Solution Example:**

```csharp
public class Rectangle
{
    public double Length;
    public double Width;

    // Method to calculate area
    public double GetArea()
    {
        return Length * Width;
    }

    // Method to calculate perimeter
    public double GetPerimeter()
    {
        return 2 * (Length + Width);
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create Rectangle objects
        Rectangle rect1 = new Rectangle();
        rect1.Length = 5;
        rect1.Width = 4;
        Console.WriteLine($"Rectangle 1: Area = {rect1.GetArea()}, Perimeter = {rect1.GetPerimeter()}");

        Rectangle rect2 = new Rectangle();
        rect2.Length = 10;
        rect2.Width = 5;
        Console.WriteLine($"Rectangle 2: Area = {rect2.GetArea()}, Perimeter = {rect2.GetPerimeter()}");
    }
}
```

---

### **Exercise 4: Create a `BankAccount` Class**

**Task:**
1. Create a class named `BankAccount` with the following fields:
   - `AccountHolder` (string)
   - `Balance` (double)
2. Create methods:
   - `Deposit(double amount)` to add money to the balance.
   - `Withdraw(double amount)` to subtract money from the balance, but only if there’s enough money.
   - `DisplayBalance()` to display the current balance.
3. In the `Main` method, create a `BankAccount` object, perform some deposits and withdrawals, and display the final balance.

**Example Output:**
```
Deposited 500. New balance: 500
Withdrew 200. New balance: 300
Withdrew 150. New balance: 150
```

#### **Solution Example:**

```csharp
public class BankAccount
{
    public string AccountHolder;
    public double Balance;

    // Method to deposit money
    public void Deposit(double amount)
    {
        Balance += amount;
        Console.WriteLine($"Deposited {amount}. New balance: {Balance}");
    }

    // Method to withdraw money
    public void Withdraw(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
            Console.WriteLine($"Withdrew {amount}. New balance: {Balance}");
        }
        else
        {
            Console.WriteLine($"Insufficient funds. Current balance: {Balance}");
        }
    }

    // Method to display balance
    public void DisplayBalance()
    {
        Console.WriteLine($"Current balance: {Balance}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create BankAccount object
        BankAccount account = new BankAccount();
        account.AccountHolder = "John Doe";

        // Perform some transactions
        account.Deposit(500);
        account.Withdraw(200);
        account.Withdraw(150);
    }
}
```

---

### **Exercise 5: Create a `Student` Class**

**Task:**
1. Create a class named `Student` with the following fields:
   - `Name` (string)
   - `Grade` (double)
2. Create a method `IsPassing()` that returns `true` if the grade is 60 or above, and `false` otherwise.
3. In the `Main` method, create a few `Student` objects, set their names and grades, and print whether each student is passing.

**Example Output:**
```
John is passing.
Alice is not passing.
```

#### **Solution Example:**

```csharp
public class Student
{
    public string Name;
    public double Grade;

    // Method to check if the student is passing
    public bool IsPassing()
    {
        return Grade >= 60;
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create Student objects
        Student student1 = new Student();
        student1.Name = "John";
        student1.Grade = 75;

        Student student2 = new Student();
        student2.Name = "Alice";
        student2.Grade = 55;

        // Check if students are passing
        Console.WriteLine($"{student1.Name} is {(student1.IsPassing() ? "passing" : "not passing")}.");
        Console.WriteLine($"{student2.Name} is {(student2.IsPassing() ? "passing" : "not passing")}.");
    }
}
```

---

### **Summary**

In these exercises, you practiced:
- Creating classes and objects.
- Defining fields to hold data for objects.
- Writing methods to perform actions for objects.
- Using objects to call methods and access fields.

### **Next Step**:
Try adding more complexity by adding more fields, validation, or error handling to these classes. You could also try combining some of these classes (e.g., `Student` and `BankAccount` for a student’s school account).

Let me know if you'd like further guidance or if you want more exercises!