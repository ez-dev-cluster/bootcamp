# Exercise Answer

### 1. Basic List Operations

**Task Recap:**
- Create a `List<int>` and ask the user to input 5 integers.
- Calculate the sum, largest, and smallest numbers in the list.

**Answer:**
```csharp
using System;
using System.Collections.Generic;
using System.Linq; // For Sum(), Max(), and Min()

class Program
{
    static void Main()
    {
        List<int> numbers = new List<int>();

        // Get 5 integers from the user
        for (int i = 0; i < 5; i++)
        {
            Console.Write($"Enter integer {i + 1}: ");
            int num = int.Parse(Console.ReadLine());
            numbers.Add(num);
        }

        // Calculate sum, max, and min
        int sum = numbers.Sum();
        int max = numbers.Max();
        int min = numbers.Min();

        // Display results
        Console.WriteLine($"Sum: {sum}");
        Console.WriteLine($"Largest: {max}");
        Console.WriteLine($"Smallest: {min}");
    }
}
```

### 2. Managing a List of Strings

**Task Recap:**
- Create a `List<string>`, ask the user for names, and stop when "stop" is entered.
- Print the number of names, remove the last name, and print the updated list.

**Answer:**
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> names = new List<string>();
        string input;

        // Get names until "stop" is entered
        do
        {
            Console.Write("Enter a name (or type 'stop' to finish): ");
            input = Console.ReadLine();
            if (input.ToLower() != "stop")
            {
                names.Add(input);
            }
        } while (input.ToLower() != "stop");

        // Print the total number of names
        Console.WriteLine($"You entered {names.Count} names.");

        // Remove the last name and display remaining names
        if (names.Count > 0)
        {
            names.RemoveAt(names.Count - 1);
            Console.WriteLine("Updated list after removing the last name:");
            foreach (string name in names)
            {
                Console.WriteLine(name);
            }
        }
        else
        {
            Console.WriteLine("No names to remove.");
        }
    }
}
```

### 3. Finding and Replacing Elements in a List

**Task Recap:**
- Declare a `List<string>` of fruits, ask the user for a fruit name.
- If the fruit is in the list, replace it with "Grapes", otherwise print "Fruit not found."

**Answer:**
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> fruits = new List<string> { "Apple", "Banana", "Cherry", "Date", "Elderberry" };

        Console.Write("Enter the name of a fruit: ");
        string input = Console.ReadLine();

        if (fruits.Contains(input))
        {
            int index = fruits.IndexOf(input);
            fruits[index] = "Grapes"; // Replace the fruit with "Grapes"
            Console.WriteLine("Updated list of fruits:");
            foreach (string fruit in fruits)
            {
                Console.WriteLine(fruit);
            }
        }
        else
        {
            Console.WriteLine("Fruit not found in the list.");
        }
    }
}
```

### 4. Sorting a List of Numbers

**Task Recap:**
- Ask the user to input 10 numbers and store them in a `List<int>`.
- Sort the list in ascending and descending order, and print both orders.

**Answer:**
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<int> numbers = new List<int>();

        // Get 10 numbers from the user
        for (int i = 0; i < 10; i++)
        {
            Console.Write($"Enter number {i + 1}: ");
            numbers.Add(int.Parse(Console.ReadLine()));
        }

        // Sort in ascending order
        numbers.Sort();
        Console.WriteLine("\nNumbers sorted in ascending order:");
        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }

        // Sort in descending order
        numbers.Reverse();
        Console.WriteLine("\nNumbers sorted in descending order:");
        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }
    }
}
```

### 5. List of Objects (Advanced)

**Task Recap:**
- Define a `Person` class with `Name` and `Age`.
- Create a `List<Person>` and ask the user to enter 3 people.
- Print the names of all people older than 18.

**Answer:**
```csharp
using System;
using System.Collections.Generic;

class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

class Program
{
    static void Main()
    {
        List<Person> people = new List<Person>();

        // Get 3 people's names and ages
        for (int i = 0; i < 3; i++)
        {
            Console.Write("Enter name: ");
            string name = Console.ReadLine();

            Console.Write("Enter age: ");
            int age = int.Parse(Console.ReadLine());

            people.Add(new Person(name, age));
        }

        // Print the names of people older than 18
        Console.WriteLine("\nPeople older than 18:");
        foreach (Person person in people)
        {
            if (person.Age > 18)
            {
                Console.WriteLine(person.Name);
            }
        }
    }
}
```
