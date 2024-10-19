### **Inheritance in C#**

**Inheritance** is one of the fundamental concepts of Object-Oriented Programming (OOP). It allows you to create a new class based on an existing class. The new class (called the **derived class** or **child class**) inherits the fields, properties, and methods of the existing class (called the **base class** or **parent class**). This promotes **code reuse** and **extensibility**.

### **Key Concepts of Inheritance:**

1. **Base Class (Parent Class)**: The class that provides common functionality.
2. **Derived Class (Child Class)**: The class that inherits from the base class and can add its own functionality.
3. **Overriding**: The derived class can modify the behavior of the base class methods.
4. **`base` Keyword**: Used to call methods or constructors of the base class from the derived class.
5. **`virtual` and `override`**: Used to modify or extend methods in the base class.
6. **Access Modifiers**: Controls the visibility of the base class members (e.g., `public`, `protected`, `private`).

---

### **Basic Inheritance Example**

Here’s a simple example that shows how a `Car` class can inherit from a `Vehicle` class:

```csharp
// Base class
public class Vehicle
{
    public string Make { get; set; }
    public string Model { get; set; }

    // Base class method
    public void Start()
    {
        Console.WriteLine("The vehicle has started.");
    }
}

// Derived class
public class Car : Vehicle
{
    public int NumberOfDoors { get; set; }

    // Derived class method
    public void Honk()
    {
        Console.WriteLine("The car is honking.");
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Create an object of the derived class (Car)
        Car myCar = new Car();
        
        // Set properties inherited from Vehicle
        myCar.Make = "Toyota";
        myCar.Model = "Camry";
        myCar.NumberOfDoors = 4;

        // Call methods from both the base class and derived class
        myCar.Start();  // From Vehicle
        myCar.Honk();   // From Car

        Console.WriteLine($"My car is a {myCar.Make} {myCar.Model} with {myCar.NumberOfDoors} doors.");
    }
}
```

#### Output:

```
The vehicle has started.
The car is honking.
My car is a Toyota Camry with 4 doors.
```

In this example, the `Car` class inherits properties (`Make`, `Model`) and methods (`Start`) from the `Vehicle` class. It can also define its own properties and methods (`NumberOfDoors`, `Honk`).

---

### **Overriding Methods**

In some cases, you may want to change the behavior of a method that is inherited from the base class. This is done by **overriding** the base class method.

- To allow a method to be overridden, mark it as `virtual` in the base class.
- In the derived class, use the `override` keyword to change the behavior.

#### Example of Overriding:

```csharp
// Base class
public class Animal
{
    // Virtual method in the base class
    public virtual void Speak()
    {
        Console.WriteLine("The animal makes a sound.");
    }
}

// Derived class
public class Dog : Animal
{
    // Override the base class method
    public override void Speak()
    {
        Console.WriteLine("The dog barks.");
    }
}

// Another derived class
public class Cat : Animal
{
    // Override the base class method
    public override void Speak()
    {
        Console.WriteLine("The cat meows.");
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        Animal myAnimal = new Animal();
        myAnimal.Speak();  // Output: The animal makes a sound.

        Dog myDog = new Dog();
        myDog.Speak();     // Output: The dog barks.

        Cat myCat = new Cat();
        myCat.Speak();     // Output: The cat meows.
    }
}
```

#### Output:

```
The animal makes a sound.
The dog barks.
The cat meows.
```

In this example, the `Speak` method in the base class `Animal` is marked as `virtual`, allowing derived classes (`Dog`, `Cat`) to override it with their own implementations.

---

### **`base` Keyword**

The `base` keyword is used to access members of the base class from the derived class. This is useful when you want to call a method or constructor of the base class in the derived class.

#### Example Using `base`:

```csharp
// Base class
public class Vehicle
{
    public string Make { get; set; }
    public string Model { get; set; }

    public Vehicle(string make, string model)
    {
        Make = make;
        Model = model;
    }

    public virtual void Start()
    {
        Console.WriteLine("The vehicle has started.");
    }
}

// Derived class
public class Car : Vehicle
{
    public int NumberOfDoors { get; set; }

    public Car(string make, string model, int numberOfDoors) : base(make, model)
    {
        NumberOfDoors = numberOfDoors;
    }

    public override void Start()
    {
        base.Start();  // Call the base class method
        Console.WriteLine("The car is now running.");
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        Car myCar = new Car("Honda", "Civic", 4);
        myCar.Start();
    }
}
```

#### Output:

```
The vehicle has started.
The car is now running.
```

In this example, the `Car` class constructor uses `base(make, model)` to call the constructor of the base class `Vehicle`. Additionally, the `Start` method in `Car` calls the `Start` method of the base class using `base.Start()`.

---

### **Inheritance with Access Modifiers**

The base class members can have different access modifiers, which affect their visibility in derived classes:

- **`public`**: The member is accessible from anywhere.
- **`protected`**: The member is accessible only within its class and by derived classes.
- **`private`**: The member is accessible only within its class and not by derived classes.

#### Example of `protected` Access Modifier:

```csharp
// Base class
public class Vehicle
{
    protected string Make { get; set; }
    protected string Model { get; set; }

    public Vehicle(string make, string model)
    {
        Make = make;
        Model = model;
    }

    public void DisplayInfo()
    {
        Console.WriteLine($"Vehicle: {Make} {Model}");
    }
}

// Derived class
public class Car : Vehicle
{
    public Car(string make, string model) : base(make, model) { }

    public void ShowMakeModel()
    {
        Console.WriteLine($"Car: {Make} {Model}");  // Can access protected members
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        Car myCar = new Car("BMW", "X5");
        myCar.DisplayInfo();   // Access method from base class
        myCar.ShowMakeModel(); // Access protected fields from derived class
    }
}
```

#### Output:

```
Vehicle: BMW X5
Car: BMW X5
```

In this example, the `Make` and `Model` fields are marked as `protected`, meaning they are not accessible outside the class, but they are accessible within the derived class `Car`.

---

### **Multiple Levels of Inheritance**

Inheritance can be extended through multiple levels. A class can inherit from another derived class.

#### Example:

```csharp
// Base class
public class Animal
{
    public virtual void Eat()
    {
        Console.WriteLine("The animal is eating.");
    }
}

// Derived class
public class Mammal : Animal
{
    public override void Eat()
    {
        Console.WriteLine("The mammal is eating.");
    }
}

// Another derived class
public class Dog : Mammal
{
    public override void Eat()
    {
        Console.WriteLine("The dog is eating.");
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        Dog myDog = new Dog();
        myDog.Eat();  // Output: The dog is eating.
    }
}
```

In this example, the `Dog` class inherits from `Mammal`, which in turn inherits from `Animal`. The `Eat` method is overridden at each level of inheritance.

---

### **Key Points to Remember About Inheritance in C#:**

- **Inheritance** enables code reuse and extends the functionality of an existing class.
- A derived class inherits all the accessible members (fields, methods, properties) from its base class.
- Use the `virtual` keyword in the base class to allow derived classes to override methods.
- Use the `override` keyword in derived classes to change or extend the behavior of base class methods.
- The `base` keyword allows a derived class to access members of its base class.
- C# does **not** support multiple inheritance (a class cannot inherit from more than one class), but you can use interfaces to achieve similar functionality.

---

### **Exercise:**
1. Create a

 base class `Employee` with fields `Name` and `Position`. Create a derived class `Manager` that adds a field `Department` and overrides a method `Work` to specify that the manager is managing the department.
2. Add another derived class `Developer` that overrides the `Work` method to specify that the developer is writing code.

Let me know if you need further explanation or help with the exercises!