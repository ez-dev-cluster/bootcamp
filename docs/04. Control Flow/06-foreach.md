# `foreach`

The `foreach` loop in C# is used to iterate over elements in a collection, such as an array, a `List`, or any other enumerable type. It’s a simple and more readable way to loop through each element without needing to worry about the size or indexes of the collection.

### **Syntax of `foreach`**:

```csharp
foreach (type variable in collection)
{
    // Code to execute for each element in the collection
}
```

- **`type`**: The data type of the elements in the collection.
- **`variable`**: A temporary variable that stores the current element of the collection during each iteration.
- **`collection`**: The collection or array that you are iterating over.

### **Example 1: Iterating through an array**

```csharp
string[] fruits = { "Apple", "Banana", "Cherry", "Date" };

foreach (string fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

#### Output:

```
Apple
Banana
Cherry
Date
```

In this example, the `foreach` loop automatically iterates over each element in the `fruits` array, and `fruit` holds the value of the current element in each iteration.

### **How `foreach` Works**

1. The `foreach` loop picks the first element from the collection and assigns it to the loop variable (`fruit` in the above example).
2. The code inside the loop is executed.
3. The process repeats for each element in the collection until all elements have been processed.

### **Example 2: Iterating over a `List`**

```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };

foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```

#### Output:

```
1
2
3
4
5
```

Here, the `foreach` loop is used to iterate over a `List` of integers. The loop runs for each element in the `List`.

### **Modifying Elements in a Collection**

It is important to note that the `foreach` loop doesn’t allow you to modify the elements of the collection directly. If you need to modify elements, you should use a `for` loop or work with collections that allow modification.

For example, trying to modify a `List` inside a `foreach` loop will result in a compilation error:

```csharp
List<int> numbers = new List<int> { 1, 2, 3 };

foreach (int number in numbers)
{
    // This will cause an error because 'number' is read-only in a foreach loop
    number += 1;
}
```

### **Example 3: Iterating through a Dictionary**

The `foreach` loop is also useful for iterating through key-value pairs in a `Dictionary`:

```csharp
Dictionary<string, int> ages = new Dictionary<string, int>
{
    { "John", 30 },
    { "Mary", 25 },
    { "Bob", 35 }
};

foreach (KeyValuePair<string, int> entry in ages)
{
    Console.WriteLine($"{entry.Key} is {entry.Value} years old.");
}
```

#### Output:

```
John is 30 years old.
Mary is 25 years old.
Bob is 35 years old.
```

In this example, the `foreach` loop iterates over each key-value pair in the `Dictionary`. `entry.Key` accesses the key, and `entry.Value` accesses the value.

### **Example 4: Breaking out of a `foreach` loop**

If you want to exit a `foreach` loop early, you can use the `break` statement:

```csharp
string[] fruits = { "Apple", "Banana", "Cherry", "Date" };

foreach (string fruit in fruits)
{
    if (fruit == "Cherry")
    {
        Console.WriteLine("Found Cherry, stopping the loop.");
        break;  // Exit the loop when "Cherry" is found
    }

    Console.WriteLine(fruit);
}
```

#### Output:

```
Apple
Banana
Found Cherry, stopping the loop.
```

### **Example 5: Skipping iterations using `continue`**

You can use the `continue` statement to skip certain elements in a `foreach` loop:

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };

foreach (int number in numbers)
{
    if (number % 2 == 0)
    {
        continue;  // Skip even numbers
    }

    Console.WriteLine("Odd number: " + number);
}
```

#### Output:

```
Odd number: 1
Odd number: 3
Odd number: 5
```

In this example, even numbers are skipped because the `continue` statement prevents the rest of the loop from executing when `number % 2 == 0`.

### **Summary**

- The `foreach` loop is a convenient way to iterate over all elements in a collection.
- It’s useful for reading data from arrays, lists, dictionaries, and other collections.
- You cannot modify the collection elements directly in a `foreach` loop.
- You can use `break` to exit the loop early or `continue` to skip an iteration.

---

### **Exercise:**
1. Write a program that iterates over a list of numbers and prints out only the even numbers.
2. Create a `Dictionary` with names and grades, then use a `foreach` loop to print each student’s grade.
3. Write a program that loops through an array of strings and prints only those strings that start with the letter "A".

Let me know if you need further explanations or help with these exercises!