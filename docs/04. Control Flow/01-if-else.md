# `if-else`

### 1. **if Statement**

The `if` statement executes a block of code only if a specified condition is `true`. If the condition is `false`, the code block is skipped.

#### Syntax:

```csharp
if (condition)
{
    // Code to execute if the condition is true
}
```

#### Example:

```csharp
int age = 18;

if (age >= 18)
{
    Console.WriteLine("You are an adult.");
}
```

In this example, the condition `age >= 18` is `true`, so the message "You are an adult." is printed.

### 2. **if-else Statement**

The `if-else` statement allows you to execute one block of code if the condition is `true`, and another block of code if the condition is `false`.

#### Syntax:

```csharp
if (condition)
{
    // Code to execute if the condition is true
}
else
{
    // Code to execute if the condition is false
}
```

#### Example:

```csharp
int age = 16;

if (age >= 18)
{
    Console.WriteLine("You are an adult.");
}
else
{
    Console.WriteLine("You are a minor.");
}
```

In this case, since `age` is less than 18, the message "You are a minor." is printed.

### 3. **if-else if-else Statement**

The `if-else if-else` statement allows you to test multiple conditions. The first condition that evaluates to `true` will execute its corresponding block of code. If none of the conditions are `true`, the `else` block is executed.

#### Syntax:

```csharp
if (condition1)
{
    // Code to execute if condition1 is true
}
else if (condition2)
{
    // Code to execute if condition2 is true
}
else
{
    // Code to execute if neither condition1 nor condition2 is true
}
```

#### Example:

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

In this example, since the `score` is 85, the program prints "Grade: B".

### Comparison of all three:

1. **`if`**: Tests a single condition.
2. **`if-else`**: Tests a condition and provides an alternative action if the condition is `false`.
3. **`if-else if-else`**: Allows you to test multiple conditions in a sequence.

### Examples of Common Conditions

- **Equality**: `==`
- **Not equal**: `!=`
- **Greater than**: `>`
- **Less than**: `<`
- **Greater than or equal to**: `>=`
- **Less than or equal to**: `<=`

#### Example:

```csharp
int x = 10;
int y = 20;

if (x > y)
{
    Console.WriteLine("x is greater than y");
}
else if (x < y)
{
    Console.WriteLine("x is less than y");
}
else
{
    Console.WriteLine("x is equal to y");
}
```

This code checks whether `x` is greater than, less than, or equal to `y`, and prints the appropriate message.

---

### Exercise:
1. Write a program that takes an integer input from the user and checks if the number is positive, negative, or zero.
2. Write a program that assigns a letter grade based on a score between 0 and 100 (use if-else if-else).

Let me know if you'd like help with any of these!