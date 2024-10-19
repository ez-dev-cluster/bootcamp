# Dictionary

A `Dictionary` in C# is a collection of key-value pairs. It is similar to a real-life dictionary where you look up a word (the key) and get its definition (the value). The keys in a `Dictionary` must be unique, and each key is associated with exactly one value. 

Here's a simple guide to working with `Dictionary` in C#:

### Creating a Dictionary

To create a `Dictionary`, you specify the type of keys and values it will store:

```csharp
// Create a Dictionary with string keys and int values
Dictionary<string, int> ages = new Dictionary<string, int>();
```

### Adding Items

You can add items to a `Dictionary` using the `Add` method or by directly setting the value for a key:

```csharp
// Add key-value pairs
ages.Add("Alice", 30);
ages.Add("Bob", 25);

// Or assign directly
ages["Charlie"] = 22;
```

### Accessing Values

You can access values by referencing the key:

```csharp
int aliceAge = ages["Alice"];
Console.WriteLine("Alice is " + aliceAge + " years old.");
```

### Checking if a Key Exists

Before accessing a value, it's a good idea to check if the key exists to avoid exceptions:

```csharp
if (ages.ContainsKey("David"))
{
    Console.WriteLine("David's age: " + ages["David"]);
}
else
{
    Console.WriteLine("David is not in the dictionary.");
}
```

### Iterating Over a Dictionary

You can iterate through a `Dictionary` using a `foreach` loop:

```csharp
foreach (KeyValuePair<string, int> entry in ages)
{
    Console.WriteLine(entry.Key + " is " + entry.Value + " years old.");
}
```

### Removing Items

To remove an item, use the `Remove` method:

```csharp
ages.Remove("Charlie");
```

### TryGetValue Method

A safe way to retrieve values is to use the `TryGetValue` method, which returns `true` if the key exists and outputs the value:

```csharp
if (ages.TryGetValue("Alice", out int age))
{
    Console.WriteLine("Alice's age: " + age);
}
else
{
    Console.WriteLine("Alice not found.");
}
```

### Dictionary Properties and Methods

- **Count**: Gets the number of key-value pairs.
- **Clear()**: Removes all items from the dictionary.
- **Keys**: Returns a collection of all the keys.
- **Values**: Returns a collection of all the values.

Example:

```csharp
Console.WriteLine("Number of entries: " + ages.Count);

foreach (string name in ages.Keys)
{
    Console.WriteLine(name);
}

foreach (int value in ages.Values)
{
    Console.WriteLine(value);
}
```

### Example Program

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Creating a dictionary
        Dictionary<string, int> ages = new Dictionary<string, int>();

        // Adding entries
        ages.Add("Alice", 30);
        ages.Add("Bob", 25);
        ages["Charlie"] = 22; // Alternative way to add

        // Accessing values
        Console.WriteLine("Alice's age: " + ages["Alice"]);

        // Checking if key exists
        if (ages.ContainsKey("David"))
        {
            Console.WriteLine("David's age: " + ages["David"]);
        }
        else
        {
            Console.WriteLine("David not found.");
        }

        // Iterating over the dictionary
        foreach (KeyValuePair<string, int> entry in ages)
        {
            Console.WriteLine(entry.Key + " is " + entry.Value + " years old.");
        }

        // Removing an item
        ages.Remove("Charlie");

        // Trying to get a value safely
        if (ages.TryGetValue("Bob", out int age))
        {
            Console.WriteLine("Bob's age: " + age);
        }
    }
}
```

This is how you can use `Dictionary` in C# to store and manipulate key-value pairs.