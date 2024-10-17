# Bool
In C#, a `bool` (short for boolean) is a data type that can hold only two values: `true` or `false`. It's commonly used for conditions, comparisons, and decision-making in code.

### Declaring a Boolean
You can declare a boolean variable like this:

```csharp
bool isRaining = true;
bool hasCompletedTask = false;
```

### Common Boolean Operations

1. **Logical Operators** – Used to perform logical operations on boolean values:

    - **AND (`&&`)**: Both conditions must be `true` for the result to be `true`.
     ```csharp
     bool result = (5 > 3) && (8 > 6); // true && true -> true
     ```

    - **OR (`||`)**: At least one condition must be `true` for the result to be `true`.
     ```csharp
     bool result = (5 > 3) || (8 < 6); // true || false -> true
     ```

    - **NOT (`!`)**: Negates the value (turns `true` into `false` and vice versa).
     ```csharp
     bool result = !(5 > 3); // !(true) -> false
     ```

2. **Comparison Operators** – Often used with booleans to compare values:

    - **Equal to (`==`)**: Checks if two values are equal.
     ```csharp
     bool isEqual = (5 == 5); // true
     ```

    - **Not equal to (`!=`)**: Checks if two values are not equal.
     ```csharp
     bool isNotEqual = (5 != 3); // true
     ```

    - **Greater than (`>`)**: Checks if the left value is greater than the right.
     ```csharp
     bool isGreater = (10 > 5); // true
     ```

    - **Less than (`<`)**: Checks if the left value is less than the right.
     ```csharp
     bool isLess = (5 < 10); // true
     ```

3. **If Statements** – Boolean values are most commonly used in `if` statements for decision-making:

    ```csharp
    bool isSunny = true;
    
    if (isSunny)
    {
        Console.WriteLine("It's a sunny day!");
    }
    else
    {
        Console.WriteLine("It's not sunny today.");
    }
    ```

4. **Boolean Methods** – Some methods return boolean values. For example, `Contains` and `StartsWith` for strings return `true` or `false`.
 
    ```csharp
    string text = "Hello, World!";
    bool containsHello = text.Contains("Hello");  // true
    bool startsWithHi = text.StartsWith("Hi");    // false
    ```

### Example

Here's a full example that combines boolean variables, comparison operators, and an if statement:

```csharp
bool isWeekend = true;
bool isHoliday = false;

if (isWeekend || isHoliday)
{
    Console.WriteLine("You can relax!");
}
else
{
    Console.WriteLine("It's a working day.");
}
```

### Truth Table for Logical Operators
Here’s a simple truth table showing how AND (`&&`), OR (`||`), and NOT (`!`) work with boolean values:

```
| A     | B     | A && B | A || B | !A    |
|-------|-------|--------|--------|-------|
| true  | true  | true   | true   | false |
| true  | false | false  | true   | false |
| false | true  | false  | true   | true  |
| false | false | false  | false  | true  |
```

Booleans are fundamental in programming for controlling logic flow and making decisions. Let me know if you need more examples or details!