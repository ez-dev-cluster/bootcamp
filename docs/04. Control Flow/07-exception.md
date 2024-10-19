# Exceptions in C#

**Exceptions** are runtime errors that occur during the execution of a program. In C#, when an error occurs, an **exception** is thrown. If not handled properly, this exception will cause the program to terminate. To ensure that your program can deal with unexpected situations, C# provides exception handling mechanisms.

### **Key Concepts of Exception Handling in C#:**

1. **`try-catch` block**: Catches and handles exceptions.
2. **`finally` block**: Code that is executed whether an exception is thrown or not.
3. **Throwing exceptions**: Manually raising an exception.
4. **Custom exceptions**: Creating your own exceptions.
5. **Types of exceptions**: There are many built-in exceptions in C# like `ArgumentException`, `NullReferenceException`, `DivideByZeroException`, etc.

---

### **1. `try-catch` Block**

A `try-catch` block allows you to handle exceptions that occur in a block of code. The `try` block contains the code that may throw an exception, while the `catch` block contains code to handle the exception.

#### Syntax:

```csharp
try
{
    // Code that might throw an exception
}
catch (ExceptionType ex)
{
    // Code to handle the exception
}
```

#### Example 1: Handling a `DivideByZeroException`

```csharp
class Program
{
    static void Main(string[] args)
    {
        try
        {
            int dividend = 10;
            int divisor = 0;
            int result = dividend / divisor;  // This will throw a DivideByZeroException
            Console.WriteLine(result);
        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine("Error: You cannot divide by zero.");
        }
    }
}
```

#### Output:

```
Error: You cannot divide by zero.
```

In this example, the `DivideByZeroException` is caught, and the error message is printed, preventing the program from crashing.

---

### **2. `finally` Block**

The `finally` block is used to execute code whether an exception is thrown or not. It's useful for releasing resources like closing files or network connections, regardless of whether the `try` block succeeds or fails.

#### Syntax:

```csharp
try
{
    // Code that might throw an exception
}
catch (ExceptionType ex)
{
    // Code to handle the exception
}
finally
{
    // Code that always runs
}
```

#### Example 2: Using `finally`

```csharp
class Program
{
    static void Main(string[] args)
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]);  // This will throw an IndexOutOfRangeException
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine("Error: Index out of range.");
        }
        finally
        {
            Console.WriteLine("This will always be executed.");
        }
    }
}
```

#### Output:

```
Error: Index out of range.
This will always be executed.
```

In this example, the `finally` block is executed whether or not the exception occurs.

---

### **3. Throwing Exceptions**

You can use the `throw` keyword to raise (or re-throw) an exception in C#. This is useful when you need to indicate that something went wrong in your code or when you want to propagate an exception to higher-level code.

#### Example 3: Throwing an Exception

```csharp
class Program
{
    static void Main(string[] args)
    {
        try
        {
            ValidateAge(15);
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static void ValidateAge(int age)
    {
        if (age < 18)
        {
            throw new ArgumentException("Age must be 18 or older.");
        }
    }
}
```

#### Output:

```
Age must be 18 or older.
```

In this example, the `ValidateAge` method throws an exception if the age is less than 18. The exception is caught in the `try-catch` block in `Main`.

---

### **4. Creating Custom Exceptions**

You can define your own exception types by creating a new class that inherits from the `Exception` class. This is useful when you want to handle specific kinds of errors in your application.

#### Example 4: Custom Exception

```csharp
// Define a custom exception
public class InvalidAgeException : Exception
{
    public InvalidAgeException(string message) : base(message)
    {
    }
}

class Program
{
    static void Main(string[] args)
    {
        try
        {
            ValidateAge(15);
        }
        catch (InvalidAgeException ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static void ValidateAge(int age)
    {
        if (age < 18)
        {
            throw new InvalidAgeException("Custom Exception: Age must be 18 or older.");
        }
    }
}
```

#### Output:

```
Custom Exception: Age must be 18 or older.
```

In this example, `InvalidAgeException` is a custom exception that is thrown when the age is invalid.

---

### **5. Types of Exceptions in C#**

C# has many built-in exception types. Here are some commonly used ones:

1. **`ArgumentException`**: Thrown when an invalid argument is passed to a method.
   - **`ArgumentNullException`**: A subtype of `ArgumentException`, thrown when `null` is passed to a method that doesn't accept it.
   - **`ArgumentOutOfRangeException`**: Thrown when an argument is outside the allowed range.
   
2. **`IndexOutOfRangeException`**: Thrown when accessing an invalid index in an array or collection.

3. **`NullReferenceException`**: Thrown when attempting to access members of an object that is `null`.

4. **`InvalidOperationException`**: Thrown when a method call is invalid for the object’s current state.

5. **`DivideByZeroException`**: Thrown when an attempt to divide by zero occurs.

6. **`FileNotFoundException`**: Thrown when an attempt to access a file that does not exist on disk fails.

#### Example 5: Handling Multiple Exceptions

```csharp
class Program
{
    static void Main(string[] args)
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]);  // IndexOutOfRangeException

            string name = null;
            Console.WriteLine(name.Length);  // NullReferenceException
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine("Index out of range: " + ex.Message);
        }
        catch (NullReferenceException ex)
        {
            Console.WriteLine("Null reference: " + ex.Message);
        }
        catch (Exception ex)
        {
            // General catch for any other exception types
            Console.WriteLine("An error occurred: " + ex.Message);
        }
    }
}
```

#### Output:

```
Index out of range: Index was outside the bounds of the array.
```

In this example, the `IndexOutOfRangeException` is caught and handled. If any other exception occurred, it would be handled by the generic `Exception` block.

---

### **Best Practices for Exception Handling:**

1. **Catch only the exceptions you can handle**: Don’t catch every exception unless you have a specific reason to do so.
   
   - **Bad practice**: Catching all exceptions with `catch (Exception)` when you don’t know what went wrong.
   - **Good practice**: Catch specific exceptions that you can handle.

2. **Use finally for cleanup**: The `finally` block is perfect for releasing resources (closing files, network connections, etc.).

3. **Never suppress exceptions**: Avoid empty `catch` blocks. If you catch an exception, handle it appropriately or rethrow it.

4. **Throw exceptions only when necessary**: Don’t throw exceptions for normal program flow. Exceptions should be used for exceptional cases, not as a control mechanism.

---

### **Summary:**

- **`try-catch` block**: Used to handle exceptions and prevent your program from crashing.
- **`finally` block**: Code that is always executed after the `try` block, whether or not an exception occurs.
- **Throwing exceptions**: You can manually throw exceptions using the `throw` keyword.
- **Custom exceptions**: You can create your own exceptions by inheriting from the `Exception` class.
- **Types of exceptions**: C# has built-in exception types like `ArgumentException`, `NullReferenceException`, `DivideByZeroException`, etc.

---

### **Exercise:**
1. Write a program that asks the user for two numbers and divides them. Handle `DivideByZeroException` and `FormatException` (if the user enters non-numeric values).
2. Create a custom exception called `NegativeNumberException` that is thrown when a user enters a negative number in a method that calculates the square root.

Let me know if you need further help or explanations!