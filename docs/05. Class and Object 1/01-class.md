A **class** in C# is a blueprint for creating objects. It defines the attributes (fields) and behaviors (methods) that the objects created from the class will have. Classes are fundamental to Object-Oriented Programming (OOP) in C#, and they allow you to encapsulate related data and functionality in a structured way.

### **Basic Structure of a Class**

A class in C# is declared using the `class` keyword, followed by the class name. The body of the class contains **fields**, **properties**, **methods**, and **constructors**.

#### Syntax:

```csharp
public class ClassName
{
    // Fields (variables)
    // Properties
    // Methods
    // Constructors
}
```

---

### **Example of a Class**

Let’s create a class called `Car`:

```csharp
public class Car
{
    // Fields
    private string make;
    private string model;
    private int year;

    // Constructor
    public Car(string make, string model, int year)
    {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Method
    public void Start()
    {
        Console.WriteLine("The car is starting.");
    }

    // Method
    public void DisplayInfo()
    {
        Console.WriteLine($"Car: {year} {make} {model}");
    }
}
```

In this example:
- The **fields** (`make`, `model`, `year`) represent the attributes of a `Car`.
- The **constructor** initializes a new instance of the class with values for `make`, `model`, and `year`.
- The **methods** (`Start`, `DisplayInfo`) define the actions a `Car` can perform.

---

### **Creating an Object from a Class (Instantiating a Class)**

Once you’ve defined a class, you can create objects (instances) of that class.

#### Example:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Create a Car object (instance of the Car class)
        Car myCar = new Car("Toyota", "Corolla", 2021);

        // Call methods on the object
        myCar.Start();
        myCar.DisplayInfo();
    }
}
```

#### Output:
```
The car is starting.
Car: 2021 Toyota Corolla
```

Here, `myCar` is an instance of the `Car` class. You can interact with its methods (`Start`, `DisplayInfo`) to perform actions on the `Car` object.

---

### **Key Components of a Class**

1. **Fields**
   - Fields are variables that store data for the object.
   - They are usually `private` to restrict direct access from outside the class.

#### Example:

```csharp
private string make;
private int year;
```

2. **Properties**
   - Properties provide a controlled way to access and modify the values of fields. They often use `get` and `set` accessors.
   - Properties can help enforce validation or encapsulation.

#### Example:

```csharp
public string Make
{
    get { return make; }
    set { make = value; }
}
```

3. **Methods**
   - Methods define the actions or behavior of the class. They contain code that can be executed when called on an object.
   - Methods can take parameters and return values.

#### Example:

```csharp
public void Start()
{
    Console.WriteLine("The car is starting.");
}
```

4. **Constructors**
   - A constructor is a special method that is called when an object of the class is created. It is used to initialize the object’s state.
   - A constructor has the same name as the class and does not have a return type.

#### Example:

```csharp
public Car(string make, string model, int year)
{
    this.make = make;
    this.model = model;
    this.year = year;
}
```

In this constructor, the `this` keyword is used to refer to the current object’s fields (`make`, `model`, `year`).

---

### **Access Modifiers**

Classes, fields, properties, and methods can have **access modifiers** to control their visibility:

- **public**: The member is accessible from any other code.
- **private**: The member is accessible only within the class.
- **protected**: The member is accessible within the class and its derived classes.
- **internal**: The member is accessible within the same assembly.

#### Example:

```csharp
public class Car
{
    // This is a public property
    public string Make { get; set; }

    // This is a private field
    private int year;

    // This is a public method
    public void Start()
    {
        Console.WriteLine("The car is starting.");
    }
}
```

---

### **Static Members**

Classes can have **static** fields, properties, and methods that belong to the class itself, rather than to any specific object. You don’t need to create an instance of the class to access static members.

#### Example:

```csharp
public class MathUtilities
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}
```

#### Usage:

```csharp
int result = MathUtilities.Add(5, 3);
Console.WriteLine(result);  // Output: 8
```

Here, the `Add` method is static, so you don’t need to create an instance of `MathUtilities` to call it.

---

### **Inheritance in Classes**

Classes can inherit from other classes, allowing you to reuse code and extend functionality. The derived class inherits all the fields, properties, and methods of the base class.

#### Example:

```csharp
// Base class
public class Vehicle
{
    public string Make { get; set; }
    
    public void Start()
    {
        Console.WriteLine("Vehicle is starting.");
    }
}

// Derived class
public class Car : Vehicle
{
    public string Model { get; set; }

    public void DisplayCarInfo()
    {
        Console.WriteLine($"Car: {Make}, Model: {Model}");
    }
}
```

#### Usage:

```csharp
class Program
{
    static void Main(string[] args)
    {
        Car myCar = new Car();
        myCar.Make = "Toyota";
        myCar.Model = "Camry";

        myCar.Start();  // Inherited from Vehicle
        myCar.DisplayCarInfo();  // Defined in Car
    }
}
```

#### Output:

```
Vehicle is starting.
Car: Toyota, Model: Camry
```

---

### **Summary**

- **Class**: A blueprint for creating objects.
- **Object**: An instance of a class.
- **Fields**: Variables that hold data for the object.
- **Properties**: Controlled access to fields.
- **Methods**: Actions or behaviors of the class.
- **Constructors**: Special methods to initialize the object.
- **Access Modifiers**: Control visibility (public, private, protected, etc.).
- **Static Members**: Belong to the class, not an instance.
- **Inheritance**: Allows one class to inherit from another.

---

### **Exercise:**
1. Create a class `Person` with fields `Name` and `Age`. Add a method `Greet` that prints "Hello, my name is [Name] and I am [Age] years old."
2. Create a class `Employee` that inherits from `Person`, and add a field `JobTitle`. Add a method `Work` that prints "I am working as a [JobTitle]."
3. Create objects of both classes and call their methods.

Let me know if you need help with these exercises or more explanations!