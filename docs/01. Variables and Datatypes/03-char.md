# Char

The `char` data type in C# is used to represent a single 16-bit Unicode character. It is a value type and can store any character, including letters, digits, and special symbols.

## Declaring and Initializing `char`

You can declare and initialize a `char` variable as follows:

```csharp
char myChar = 'A';
```

## `char` methods
You can use the char.IsDigit method to check if a character is a digit:

```cs
char c = '5';
bool isDigit = char.IsDigit(c);
Console.WriteLine("Is Digit: " + isDigit); // Output: Is Digit: True
```

```cs
char c = 'A';
bool isLetter = char.IsLetter(c);
Console.WriteLine("Is Letter: " + isLetter); // Output: Is Letter: True
```

```cs
char lower = 'a';
char upper = char.ToUpper(lower);
Console.WriteLine("Uppercase: " + upper); // Output: Uppercase: A
```

```cs
char upper = 'A';
char lower = char.ToLower(upper);
Console.WriteLine("Lowercase: " + lower); // Output: Lowercase: a
```