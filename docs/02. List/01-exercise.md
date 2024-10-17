### Exercise
**Task:** Create a program that does the following:

1. Declares a `List<int>`.
2. Asks the user to input 5 integers and adds them to the list.
3. Prints the sum, the largest number, and the smallest number in the list.

**Hints:**

- Use `Add()` to add items to the list.
- Use a loop to get multiple inputs from the user.
- Use `List.Sum()`, `List.Max()`, and `List.Min()` to calculate the sum, max, and min of the list.

---

### 2. Managing a List of Strings
**Task:** Write a program that:

1. Declares a `List<string>` to store names.
2. Asks the user to enter names and add them to the list until the user types "stop".
3. Prints the total number of names entered.
4. Removes the last name in the list and prints the remaining names.

**Hints:**

- Use a `while` loop to keep adding names until "stop" is entered.
- Use `RemoveAt()` to remove the last name.

---

### 3. Finding and Replacing Elements in a List
**Task:** Create a program that:

1. Declares a `List<string>` with the following items: "Apple", "Banana", "Cherry", "Date", and "Elderberry".
2. Prompts the user to enter a fruit name.
3. If the fruit is in the list, replace it with "Grapes" and print the updated list.
4. If the fruit is not found, print "Fruit not found in the list."

**Hints:**

- Use `Contains()` to check if the list contains the fruit.
- Use `IndexOf()` to get the index of the fruit in the list.
- Use `RemoveAt()` and `Insert()` or `Replace()` to update the list.

---

### 4. Sorting a List of Numbers
**Task:** Write a program that:

1. Asks the user to input 10 numbers and stores them in a `List<int>`.
2. Sorts the list in ascending and descending order.
3. Prints the sorted list in both orders.

**Hints:**

- Use `Sort()` for ascending order and `Reverse()` for descending order.

---

### 5. List of Objects (Advanced)
**Task:** Create a program that:

1. Defines a `Person` class with `Name` (string) and `Age` (int) properties.
2. Declares a `List<Person>` to store a list of people.
3. Prompts the user to input 3 people’s names and ages and stores them in the list.
4. Prints the names of all people who are older than 18.

**Hints:**

- Define the `Person` class.
- Use `Add()` to add objects to the list.
- Use a `foreach` loop to iterate through the list and check the `Age` property.

---

### Example for Exercise 5:

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

        for (int i = 0; i < 3; i++)
        {
            Console.Write("Enter name: ");
            string name = Console.ReadLine();

            Console.Write("Enter age: ");
            int age = int.Parse(Console.ReadLine());

            people.Add(new Person(name, age));
        }

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
