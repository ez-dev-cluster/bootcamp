# String

Here's a quick overview:

### Declaring a String
You can declare a string using double quotes:

```csharp
string greeting = "Hello, World!";
```

### Common String Methods
C# provides several useful methods to work with strings. Here are a few of the most common ones:

1. **Concatenation** – Combining two strings:
   ```csharp
   string part1 = "Hello";
   string part2 = "World";
   string full = part1 + ", " + part2 + "!";
   Console.WriteLine(full); // Output: Hello, World!
   ```

2. **Length** – Getting the length of a string:
   ```csharp
   string text = "Hello";
   int length = text.Length;
   Console.WriteLine(length); // Output: 5
   ```

3. **Substring** – Extracting a part of a string:
   ```csharp
   string word = "Hello";
   string sub = word.Substring(0, 2); // Start at index 0, take 2 characters
   Console.WriteLine(sub); // Output: He
   ```

4. **Contains** – Checking if a string contains a certain substring:
   ```csharp
   string phrase = "Hello, World!";
   bool containsWorld = phrase.Contains("World");
   Console.WriteLine(containsWorld); // Output: True
   ```

5. **Replace** – Replacing part of a string with another string:
   ```csharp
   string sentence = "I like cats.";
   string newSentence = sentence.Replace("cats", "dogs");
   Console.WriteLine(newSentence); // Output: I like dogs.
   ```

6. **ToUpper/ToLower** – Changing the case of a string:
   ```csharp
   string word = "Hello";
   Console.WriteLine(word.ToUpper()); // Output: HELLO
   Console.WriteLine(word.ToLower()); // Output: hello
   ```

### String Interpolation
You can use string interpolation to embed variables directly in a string, making it easier to format:

```csharp
string name = "John";
int age = 30;
string info = $"Name: {name}, Age: {age}";
Console.WriteLine(info); // Output: Name: John, Age: 30
```

### Escape Characters
If you need to include special characters in your string, such as a newline (`\n`) or a tab (`\t`), you can use escape sequences:

```csharp
string escaped = "Hello\nWorld";
Console.WriteLine(escaped); // Output: 
// Hello
// World
```

These are some of the basics of working with `string` in C#. Let me know if you'd like more examples!