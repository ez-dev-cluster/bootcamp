# `List<T>`

In C#, a `List<T>` is a collection that stores elements in a dynamic array, meaning its size can grow or shrink as needed. It's part of the `System.Collections.Generic` namespace and is a very useful type for storing a sequence of elements that may change over time.

### Declaring a List

To declare a `List`, you must specify the type of elements the list will store (e.g., `int`, `string`, etc.):

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Declare a list of integers
        List<int> numbers = new List<int>();

        // Declare a list of strings
        List<string> names = new List<string>();
    }
}
```

### Adding Elements to a List

You can add elements to a `List` using the `Add` method:

```csharp
List<int> numbers = new List<int>();
numbers.Add(10);
numbers.Add(20);
numbers.Add(30);
```

### Accessing Elements in a List

You can access elements in a `List` using an index, similar to arrays. The index is zero-based (the first element is at index 0).

```csharp
List<int> numbers = new List<int> { 10, 20, 30 };
Console.WriteLine(numbers[0]);  // Output: 10
Console.WriteLine(numbers[1]);  // Output: 20
Console.WriteLine(numbers[2]);  // Output: 30
```

### Modifying Elements in a List

You can modify elements by accessing them using their index:

```csharp
numbers[1] = 25;  // Change the second element (20) to 25
Console.WriteLine(numbers[1]);  // Output: 25
```

### Removing Elements from a List

You can remove elements using the `Remove` method (which removes the first occurrence of the element) or `RemoveAt` (which removes the element at a specific index).

```csharp
List<int> numbers = new List<int> { 10, 20, 30 };
numbers.Remove(20);       // Removes the element 20
numbers.RemoveAt(0);      // Removes the element at index 0 (10)
```

### List Methods

Here are some useful methods you can use with `List`:

1. **Count** – Get the number of elements in the list:
   ```csharp
   int count = numbers.Count;
   Console.WriteLine(count);  // Output: 2 (after the removals above)
   ```

2. **Contains** – Check if the list contains a certain element:
   ```csharp
   bool contains30 = numbers.Contains(30);
   Console.WriteLine(contains30);  // Output: true
   ```

3. **Insert** – Insert an element at a specific index:
   ```csharp
   numbers.Insert(1, 15);  // Inserts 15 at index 1
   ```

4. **Clear** – Remove all elements from the list:
   ```csharp
   numbers.Clear();  // List is now empty
   ```

### Iterating Over a List

You can loop through a list using a `for` loop or a `foreach` loop:

```csharp
List<string> names = new List<string> { "John", "Jane", "Alice" };

// Using a for loop
for (int i = 0; i < names.Count; i++)
{
    Console.WriteLine(names[i]);
}

// Using a foreach loop
foreach (string name in names)
{
    Console.WriteLine(name);
}
```

### Example Program Using List

Here’s an example program that demonstrates adding, accessing, modifying, and removing elements in a `List`:

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Declare and initialize a list of strings
        List<string> names = new List<string> { "Alice", "Bob", "Charlie" };

        // Add an element to the list
        names.Add("David");

        // Access and print elements
        Console.WriteLine("Original List:");
        foreach (string name in names)
        {
            Console.WriteLine(name);
        }

        // Modify an element
        names[1] = "Bobby";

        // Remove an element
        names.Remove("Charlie");

        // Print the updated list
        Console.WriteLine("\nUpdated List:");
        foreach (string name in names)
        {
            Console.WriteLine(name);
        }
    }
}
```

### Summary

- `List<T>` is a dynamic array that can grow or shrink as elements are added or removed.
- You can use methods like `Add`, `Remove`, and `Insert` to manage elements in the list.
- You can access elements using an index or loop through them using `for` or `foreach` loops.
- `List<T>` automatically manages the size, making it more flexible than arrays.

Let me know if you have any more questions!