# Exercise Answer

### **Exercise 1: Basic Dictionary Operations**

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Step 1: Create a Dictionary and add entries
        Dictionary<string, int> people = new Dictionary<string, int>
        {
            { "John", 35 },
            { "Mary", 28 },
            { "Mark", 40 },
            { "Susan", 22 },
            { "Bob", 30 }
        };

        // Step 2: Print all names and ages
        Console.WriteLine("All entries:");
        foreach (var entry in people)
        {
            Console.WriteLine($"{entry.Key}: {entry.Value}");
        }

        // Step 3: Remove "Mark"
        people.Remove("Mark");

        // Step 4: Check if "Alice" exists
        if (people.ContainsKey("Alice"))
        {
            Console.WriteLine("Alice is found.");
        }
        else
        {
            Console.WriteLine("Alice is not in the dictionary.");
        }

        // Step 5: Print count of entries
        Console.WriteLine($"Number of entries after removal: {people.Count}");
    }
}
```

### **Exercise 2: Access and Update Dictionary**

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Step 1: Create a Dictionary of city populations
        Dictionary<string, int> cities = new Dictionary<string, int>
        {
            { "Bangkok", 8300000 },
            { "New York", 8400000 },
            { "London", 9000000 },
            { "Tokyo", 14000000 }
        };

        // Step 2: Retrieve and print New York's population
        Console.WriteLine($"New York population: {cities["New York"]}");

        // Step 3: Update London's population
        cities["London"] = 9300000;

        // Step 4: Add Sydney
        cities.Add("Sydney", 5300000);

        // Step 5: Print all cities and populations
        Console.WriteLine("All cities and their populations:");
        foreach (var city in cities)
        {
            Console.WriteLine($"{city.Key}: {city.Value}");
        }
    }
}
```

### **Exercise 3: Safe Access and TryGetValue**

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Step 1: Create a Dictionary of products and prices
        Dictionary<string, double> products = new Dictionary<string, double>
        {
            { "Laptop", 1200.50 },
            { "Headphones", 150.75 },
            { "Monitor", 300.99 }
        };

        // Step 2: Ask the user for a product
        Console.Write("Enter the product name: ");
        string product = Console.ReadLine();

        // Step 3: Try to get the product price
        if (products.TryGetValue(product, out double price))
        {
            Console.WriteLine($"{product} price: {price}");
        }
        else
        {
            Console.WriteLine("Product not found.");
        }
    }
}
```

### **Exercise 4: Counting Word Frequency**

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Step 1: Get a sentence from the user
        Console.Write("Enter a sentence: ");
        string sentence = Console.ReadLine();

        // Step 2: Split the sentence into words
        string[] words = sentence.Split(' ');

        // Step 3: Create a Dictionary to count word frequency
        Dictionary<string, int> wordCount = new Dictionary<string, int>();

        foreach (string word in words)
        {
            if (wordCount.ContainsKey(word))
            {
                wordCount[word]++;
            }
            else
            {
                wordCount.Add(word, 1);
            }
        }

        // Step 4: Print the word frequency
        Console.WriteLine("Word frequencies:");
        foreach (var entry in wordCount)
        {
            Console.WriteLine($"{entry.Key}: {entry.Value}");
        }
    }
}
```

### **Exercise 5: Dictionary of Grades**

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Program
{
    static void Main()
    {
        // Step 1: Create a Dictionary for students and grades
        Dictionary<string, int> grades = new Dictionary<string, int>
        {
            { "John", 85 },
            { "Mary", 92 },
            { "Bob", 76 },
            { "Susan", 89 },
            { "James", 95 }
        };

        // Step 2: Print each student's name and grade
        Console.WriteLine("Student Grades:");
        foreach (var entry in grades)
        {
            Console.WriteLine($"{entry.Key}: {entry.Value}");
        }

        // Step 3: Find the student with the highest grade
        var highestGrade = grades.Aggregate((l, r) => l.Value > r.Value ? l : r);
        Console.WriteLine($"\nHighest grade: {highestGrade.Key} with {highestGrade.Value}");

        // Step 4: Calculate the average grade
        double average = grades.Values.Average();
        Console.WriteLine($"\nAverage grade: {average:F2}");
    }
}
```

### **Exercise 6: Reversing Key-Value Pairs**

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Original Dictionary
        Dictionary<string, string> fruits = new Dictionary<string, string>
        {
            { "Apple", "Red" },
            { "Banana", "Yellow" },
            { "Grapes", "Purple" },
            { "Orange", "Orange" }
        };

        // Step 1: Create a new Dictionary for reversed key-value pairs
        Dictionary<string, string> colors = new Dictionary<string, string>();

        foreach (var fruit in fruits)
        {
            colors.Add(fruit.Value, fruit.Key);
        }

        // Step 2: Print the reversed dictionary
        Console.WriteLine("Reversed Dictionary (color -> fruit):");
        foreach (var entry in colors)
        {
            Console.WriteLine($"{entry.Key}: {entry.Value}");
        }
    }
}
```

---

Try running these solutions in your C# environment! Let me know if you need further explanation or tweaks to the code.