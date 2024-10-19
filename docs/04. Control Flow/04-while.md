# `while`
The `while` loop in C# repeatedly executes a block of code as long as the given condition remains `true`. It’s useful when you don’t know beforehand how many times a loop should run, but you know that it should continue until a certain condition is met.

### **Syntax of the `while` loop**:

```csharp
while (condition)
{
    // Code to execute while the condition is true
}
```

The `condition` is evaluated before each iteration of the loop. If the condition is `true`, the code block inside the loop is executed. This repeats until the condition becomes `false`.

### **Example 1: Basic `while` loop**

```csharp
int count = 1;

while (count <= 5)
{
    Console.WriteLine("Count is: " + count);
    count++;  // Increment the count
}
```

#### Output:

```
Count is: 1
Count is: 2
Count is: 3
Count is: 4
Count is: 5
```

In this example, the loop continues to run as long as `count` is less than or equal to 5. After each iteration, `count` is incremented by 1, and once `count` becomes greater than 5, the loop stops.

### **Infinite `while` loop**

If the condition never becomes `false`, the `while` loop will run indefinitely, which can cause your program to hang. For example:

```csharp
while (true)
{
    Console.WriteLine("This loop will run forever!");
}
```

This loop runs infinitely because the condition `true` will always remain true. You usually avoid infinite loops unless you intentionally want this behavior, such as in certain background processes or waiting for a user to trigger an action.

### **Breaking out of a `while` loop**

You can use the `break` statement to exit a `while` loop prematurely, even if the condition is still `true`.

#### Example:

```csharp
int number = 1;

while (number <= 10)
{
    if (number == 5)
    {
        Console.WriteLine("Breaking the loop at 5");
        break;  // Exit the loop
    }
    Console.WriteLine("Number is: " + number);
    number++;
}
```

#### Output:

```
Number is: 1
Number is: 2
Number is: 3
Number is: 4
Breaking the loop at 5
```

In this example, the loop breaks when `number` equals 5, even though the condition `number <= 10` is still true.

### **Using `continue` in a `while` loop**

The `continue` statement skips the rest of the code in the current iteration and proceeds to the next iteration of the loop.

#### Example:

```csharp
int i = 0;

while (i < 10)
{
    i++;

    if (i % 2 == 0)
    {
        continue;  // Skip the rest of the loop body if `i` is even
    }

    Console.WriteLine("Odd number: " + i);
}
```

#### Output:

```
Odd number: 1
Odd number: 3
Odd number: 5
Odd number: 7
Odd number: 9
```

In this example, the loop skips printing even numbers by using the `continue` statement when `i` is even.

### **Example 2: Waiting for user input**

```csharp
string input = "";

while (input != "exit")
{
    Console.Write("Enter a command (type 'exit' to quit): ");
    input = Console.ReadLine();
}

Console.WriteLine("You have exited the loop.");
```

In this example, the program keeps asking the user to enter a command. The loop continues until the user types "exit".

### **Summary**

- **`while` loop**: Runs a block of code as long as a specified condition is `true`.
- **Infinite loop**: If the condition is always `true`, the loop will run forever.
- **`break` statement**: Exits the loop prematurely.
- **`continue` statement**: Skips the current iteration and continues with the next one.

---

### **Exercise:**
Write a program that asks the user to enter numbers, and it will sum them up. The loop will continue until the user enters a negative number, at which point the program will print the total sum of the entered numbers.

Let me know if you need further help!