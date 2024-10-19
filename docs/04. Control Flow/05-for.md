# `for`

The `for` loop in C# is a control structure that allows you to repeat a block of code a specific number of times. It's commonly used when you know in advance how many times you want to iterate. 

### **Syntax of the `for` loop**:

```csharp
for (initialization; condition; increment/decrement)
{
    // Code to execute for each iteration
}
```

- **Initialization**: This step is executed once before the loop starts. It typically declares and initializes a counter variable.
- **Condition**: Before each iteration, the condition is checked. If it’s `true`, the loop continues. If it’s `false`, the loop stops.
- **Increment/Decrement**: After each iteration, the counter is updated (usually incremented or decremented).

### **Example 1: Basic `for` loop**

```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine("Iteration number: " + i);
}
```

#### Output:

```
Iteration number: 1
Iteration number: 2
Iteration number: 3
Iteration number: 4
Iteration number: 5
```

- **Initialization**: `int i = 1` (The loop starts with `i = 1`)
- **Condition**: `i <= 5` (The loop runs as long as `i` is less than or equal to 5)
- **Increment**: `i++` (After each iteration, `i` is incremented by 1)

### **Flow of a `for` loop**

1. The **initialization** step runs once.
2. The **condition** is checked. If `true`, the loop body executes.
3. After the loop body, the **increment/decrement** step runs.
4. The **condition** is checked again, and the loop continues until the condition is `false`.

### **Example 2: Sum of numbers using a `for` loop**

```csharp
int sum = 0;

for (int i = 1; i <= 10; i++)
{
    sum += i;
}

Console.WriteLine("The sum of numbers from 1 to 10 is: " + sum);
```

#### Output:

```
The sum of numbers from 1 to 10 is: 55
```

In this example, the loop runs 10 times, adding each value of `i` to the `sum` variable.

### **Example 3: Looping over an array**

You can also use a `for` loop to iterate over an array or any collection:

```csharp
string[] fruits = { "Apple", "Banana", "Cherry", "Date" };

for (int i = 0; i < fruits.Length; i++)
{
    Console.WriteLine(fruits[i]);
}
```

#### Output:

```
Apple
Banana
Cherry
Date
```

- The loop runs from `i = 0` to `i < fruits.Length`, which means it iterates over each element in the `fruits` array.
- `fruits.Length` gives the number of elements in the array.

### **Using `break` and `continue` in a `for` loop**

- **`break`**: Exits the loop prematurely.
- **`continue`**: Skips the current iteration and moves to the next one.

#### Example: Using `break` in a `for` loop

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i == 5)
    {
        break;  // Exit the loop when i is 5
    }
    Console.WriteLine(i);
}
```

#### Output:

```
1
2
3
4
```

The loop exits when `i` equals 5 due to the `break` statement.

#### Example: Using `continue` in a `for` loop

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
    {
        continue;  // Skip the rest of the loop when i is 3
    }
    Console.WriteLine(i);
}
```

#### Output:

```
1
2
4
5
```

The loop skips printing the value `3` due to the `continue` statement.

### **Example 4: Looping backwards (decrementing)**

You can also decrement the counter in a `for` loop:

```csharp
for (int i = 5; i >= 1; i--)
{
    Console.WriteLine("Countdown: " + i);
}
```

#### Output:

```
Countdown: 5
Countdown: 4
Countdown: 3
Countdown: 2
Countdown: 1
```

Here, the loop starts at `i = 5` and decrements down to `i = 1`.

---

### **Exercise 1: Multiplication table**
Write a program that prints the multiplication table for any given number up to 10 using a `for` loop.

### **Exercise 2: Factorial of a number**
Write a program that calculates the factorial of a given number using a `for` loop.

### **Exercise 3: Finding even numbers**
Write a program that prints all even numbers from 1 to 20 using a `for` loop.

Let me know if you need help with these exercises or further explanation!