### Adding JUnit5 to our VS

1. Download JAR file from Maven.org: https://repo1.maven.org/maven2/org/junit/platform/junit-platform-console-standalone/1.6.2/junit-platform-console-standalone-1.6.2.jar and save it somewhere you'll remember - I suggest the same place as your Java JDK
2. Open up your settings.json in VS Code by using the Command Pallate (Ctrl+Shift+P / CMD+Shift+P) and searching settings.json
3. Add the following snippet of code to your settings.json file, making sure to add your own filepath to wherever you saved the JUnit JAR file:

```"java.project.referencedLibraries": [
    "lib/**/*.jar",
    "C:\\Program Files\\Java\\junit-platform-console-standalone-1.6.2.jar"
  ]
```

# Test Driven Development (TDD)

That JAR file we just downloaded is a Java library - we're essentially loading in our own library so that we can run imports, etc.

What is TDD?

- writing tests for yourself before you actually write any code
- approach of programming which gives instructions to developers to write new code only when a test has failed

Why TDD?

- avoid duplication of code
- makes our code clearer, simple and bug-free

TDD Process (Simplified)

1. Write unit test for one small step of functionality
2. Run that test - it obviously fails because we haven't written the code to add that functionality yet!
3. Write the minumum amount of code needed for that test to pass
4. Run the test - did it pass?
5. Passed) Great! Go back to Step 1 | Failed) Refactor your code from Step 3

![https://www.whizlabs.com/wp-content/uploads/2016/04/TDD.png](https://www.whizlabs.com/wp-content/uploads/2016/04/TDD.png)

Define Refactor: "to change a section of code without changing its actual functionality"

### Levels of TDD

1. Acceptance TDD (ATDD)

- Used to be called Behavioral Driven Development (BDD)
- Write a single test that tests the end goal of your program

2. Developer TDD (TDD)

- Write a single unit test for every step of the process adding functionality to our program

### Fizz Buzz

This is a super classic developer interview problem/question/test/etc.

- If divisible by 3, instead of returning number, return "Fizz"
- If divisible by 5, instead of returning number, return "Buzz"
- If dividible by 3 and 5 (15), instead of returning number, return "Fizz Buzz"

Input [1, 2, 3, 4, 5, ...]
Expected Output [1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz,...]

TDD Requirements:

- Don't write any production code without a failing test first
- Make each step as small and simple as possible
- Commit immeadiately when our test passes

### String Calculator

Requirements:

1. Create a simple String calculator with a method int Add(String numbers)
2. The add method can take 0, 1, or 2 numbers and returns their sum - for an empty string, it returns 0 - example: "" would return 0, "1" returns 1, "1,2" returns 3
3. Allow the add() to handle an unknown amount of numbers
4. Calling add() with a negative number will throw an exception "negatives not allowed" and the negative number given - if multiple negative numbers, show them all
5. Numbers bigger than 1000 should be ignored - add("2,1001") should return 2
