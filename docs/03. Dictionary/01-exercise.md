# Exercise

### Exercise 1: Basic Dictionary Operations
Create a `Dictionary` to store the names and ages of 5 people. Perform the following tasks:

   1. Add entries for the following people: 
      - John, 35
      - Mary, 28
      - Mark, 40
      - Susan, 22
      - Bob, 30
   2. Print all the names and ages.
   3. Remove the entry for "Mark".
   4. Check if "Alice" exists in the dictionary and print a message if she’s found or not.
   5. Print the count of entries in the dictionary after removing "Mark".

### Exercise 2: Access and Update Dictionary
Given a `Dictionary` storing the population of various cities, perform the following tasks:

   1. Create a `Dictionary<string, int>` for the following cities and populations:
      - Bangkok, 8300000
      - New York, 8400000
      - London, 9000000
      - Tokyo, 14000000
   2. Retrieve and print the population of New York.
   3. Update the population of London to 9300000.
   4. Add a new city: "Sydney" with a population of 5300000.
   5. Print all the cities and their populations.

### Exercise 3: Safe Access and TryGetValue
Write a program that:

   1. Creates a `Dictionary<string, double>` to store product prices for the following products:
      - "Laptop", 1200.50
      - "Headphones", 150.75
      - "Monitor", 300.99
   2. Ask the user to enter a product name, and safely retrieve the price using `TryGetValue`.
   3. If the product is found, print the price. If not, print "Product not found."

### Exercise 4: Counting Word Frequency
Write a program that:

   1. Takes a string input from the user (a sentence).
   2. Splits the sentence into words and stores the count of each word in a `Dictionary<string, int>`.
   3. Print the word frequency for each word.

   For example, if the input is: "hello world hello C#", the output should be:
   ```
   hello: 2
   world: 1
   C#: 1
   ```

### Exercise 5: Dictionary of Grades
Create a `Dictionary` that stores student names and their grades (on a scale of 0 to 100). Perform the following:

   1. Add 5 students and their grades.
   2. Print out each student's name and grade.
   3. Find and print the student with the highest grade.
   4. Find and print the average grade of the class.

### Exercise 6: Reversing Key-Value Pairs

Given the following `Dictionary` of fruits and their colors:

   ```csharp
   Dictionary<string, string> fruits = new Dictionary<string, string>
   {
      { "Apple", "Red" },
      { "Banana", "Yellow" },
      { "Grapes", "Purple" },
      { "Orange", "Orange" }
   };
   ```
   Write a program that creates a new `Dictionary<string, string>` where the colors are the keys and the fruits are the values.

   Expected output:
   ```
   Red: Apple
   Yellow: Banana
   Purple: Grapes
   Orange: Orange
   ```
