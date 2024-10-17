# Double

The `double` data type in C# is a double-precision floating-point type that is used to represent decimal numbers. It is a 64-bit number and can store very large or very small numbers with a high degree of precision.

## Declaring and Initializing `double`

You can declare and initialize a `double` variable as follows:

```csharp
double myDouble = 10.5;
```

## Performing Operations with double
You can perform various arithmetic operations with double variables. Here are some examples:

```cs
double a = 5.5;
double b = 2.2;

// Addition
double sum = a + b;
Console.WriteLine("Sum: " + sum); // Output: Sum: 7.7

// Subtraction
double difference = a - b;
Console.WriteLine("Difference: " + difference); // Output: Difference: 3.3

// Multiplication
double product = a * b;
Console.WriteLine("Product: " + product); // Output: Product: 12.1

// Division
double quotient = a / b;
Console.WriteLine("Quotient: " + quotient); // Output: Quotient: 2.5
```

## Precision and Rounding
double provides a high degree of precision, but it is important to be aware of potential rounding errors when performing arithmetic operations. You can use the Math.Round method to round a double to a specified number of decimal places:

```cs
double value = 5.6789;
double roundedValue = Math.Round(value, 2);
Console.WriteLine("Rounded Value: " + roundedValue); // Output: Rounded Value: 5.68
```