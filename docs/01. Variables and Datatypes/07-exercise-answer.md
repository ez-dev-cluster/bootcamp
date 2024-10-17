# Exercise Answer

### 1. Integer (`int`) Exercise:
**Task:** Create a program that asks the user to input two integers, then calculates and displays their sum, difference, product, and quotient (division).

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the first integer: ");
        int num1 = int.Parse(Console.ReadLine());

        Console.Write("Enter the second integer: ");
        int num2 = int.Parse(Console.ReadLine());

        Console.WriteLine($"Sum: {num1 + num2}");
        Console.WriteLine($"Difference: {num1 - num2}");
        Console.WriteLine($"Product: {num1 * num2}");
        Console.WriteLine($"Quotient: {num1 / num2}");
    }
}
```

### 2. Double (`double`) Exercise:
**Task:** Write a program that asks the user for the radius of a circle (as a double) and then calculates and displays the area and circumference of the circle.

Formula:
- Area = π * r²
- Circumference = 2 * π * r

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the radius of the circle: ");
        double radius = double.Parse(Console.ReadLine());

        double area = Math.PI * Math.Pow(radius, 2);
        double circumference = 2 * Math.PI * radius;

        Console.WriteLine($"Area: {area}");
        Console.WriteLine($"Circumference: {circumference}");
    }
}
```

### 3. Boolean (`bool`) Exercise:
**Task:** Create a program that asks the user for their age and checks if they are eligible to vote (18 years or older). Print "Eligible to vote" if true and "Not eligible to vote" if false.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter your age: ");
        int age = int.Parse(Console.ReadLine());

        bool canVote = age >= 18;
        if (canVote)
        {
            Console.WriteLine("Eligible to vote");
        }
        else
        {
            Console.WriteLine("Not eligible to vote");
        }
    }
}
```

### 4. String (`string`) Exercise:
**Task:** Create a program that asks the user for their first and last name, then prints a greeting message using string concatenation and interpolation.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter your first name: ");
        string firstName = Console.ReadLine();

        Console.Write("Enter your last name: ");
        string lastName = Console.ReadLine();

        string greeting = "Hello, " + firstName + " " + lastName + "!";
        Console.WriteLine(greeting);

        // Using string interpolation
        Console.WriteLine($"Hello, {firstName} {lastName}!");
    }
}
```

### 5. Char (`char`) Exercise:
**Task:** Write a program that asks the user to enter a single character and checks if it is a vowel or consonant. Assume the input is a letter.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a single letter: ");
        char letter = char.Parse(Console.ReadLine().ToLower());

        bool isVowel = "aeiou".Contains(letter);

        if (isVowel)
        {
            Console.WriteLine("The letter is a vowel.");
        }
        else
        {
            Console.WriteLine("The letter is a consonant.");
        }
    }
}
```

These exercises cover basic operations and concepts for each of the specified types (`int`, `double`, `bool`, `string`, and `char`). Let me know if you'd like more or specific types of exercises!