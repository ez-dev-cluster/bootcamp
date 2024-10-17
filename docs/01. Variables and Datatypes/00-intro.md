# Intro 
**A variable** is a storage location in programming that holds a value which can be 
changed during the execution of a program. It is identified by a name and can store 
different types of data such as numbers, strings, or objects.

<details>
<summary>Vocabs</summary>
<ul>
  <li><b>Variable</b> - ตัวแปร</li>
  <li><b>Storage location</b> - ที่เก็บข้อมูล</li>
  <li><b>Programming</b> - การเขียนโปรแกรม</li>
  <li><b>Value</b> - ค่า</li>
  <li><b>Execution</b> - การทำงาน</li>
  <li><b>Identified</b> - ถูกระบุ</li>
  <li><b>Name</b> - ชื่อ</li>
  <li><b>Data types</b> - ประเภทของข้อมูล</li>
  <li><b>Numbers</b> - ตัวเลข</li>
  <li><b>Strings</b> - สตริง</li>
  <li><b>Objects</b> - อ็อบเจ็กต์</li>
</ul>
</details>

```cs linenums="1" hl_lines="7-10 18-21"
using System;

class Program
{
    static void Main()
    {
        // Declare and initialize variables
        int number = 10;
        string text = "Hello, World!";
        object obj = new { Name = "John", Age = 30 };

        // Print initial values
        Console.WriteLine("Initial Values:");
        Console.WriteLine("Number: " + number);
        Console.WriteLine("Text: " + text);
        Console.WriteLine("Object: " + obj);

        // Change the values of the variables
        number = 20;
        text = "Goodbye, World!";
        obj = new { Name = "Jane", Age = 25 };

        // Print new values
        Console.WriteLine("\nNew Values:");
        Console.WriteLine("Number: " + number);
        Console.WriteLine("Text: " + text);
        Console.WriteLine("Object: " + obj);
    }
}
```