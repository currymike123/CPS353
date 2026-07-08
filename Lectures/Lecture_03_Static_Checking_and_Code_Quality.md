---
marp: true
theme: default
---

# Lecture 3: Static Checking & Code Quality

---

## Today's Plan

1.  **Recap:** The Software Construction Philosophy
2.  **What is Static Checking?**
3.  **The Bug-Catching Spectrum**
4.  **Static Checking in Java: Examples**
5.  **Tools of the Trade**
6.  **In-Class Exercise: Bug Hunt!**

---

## Part 1: Recap

Our goal is to build software that is:
1.  **Safe from bugs**
2.  **Easy to understand**
3.  **Ready for change**

Today, we focus on the first pillar: **Safe from bugs**. Our first line of defense is to find bugs *before the program even runs*.

---

## Part 2: What is Static Checking?

**Static checking** is the process of analyzing source code to find potential bugs without executing it.

- It catches certain kinds of errors automatically.
- It operates on the *text* of the code, not the running program.
- The compiler (`javac`) is your first and most important static checker.

---

### Static vs. Dynamic Checking

A quick review:

- **Static Checking:** Bugs found at compile-time.
  - *Examples:* Syntax errors, type mismatches, calling a non-existent method.
  - *Cost:* Cheap. Happens on the developer's machine in seconds.

- **Dynamic Checking:** Bugs found at run-time.
  - *Examples:* `NullPointerException`, `ArrayIndexOutOfBoundsException`, logic errors.
  - *Cost:* More expensive. Requires running the program, writing tests, or getting bug reports from users.

---

## Part 3: The Bug-Catching Spectrum

We want to catch bugs as early (and cheaply) as possible.

1.  **Static Checking:** Compile-time errors, style warnings.
2.  **Dynamic Checking (Testing):** Unit tests, integration tests.
3.  **Code Review:** Manual inspection by humans.
4.  **Field Reports:** Bugs found by users in production (most expensive!).

**A good developer uses a combination of all of these.** Static checking is the first, essential step.

---

## Part 4: Static Checking in Java

Let's see what kinds of bugs the Java compiler and other static analysis tools can find for us.

---

### Example: Type Mismatches

This is the most common and powerful type of static check.

```java
String message = "Hello, world!";
int year = 2026;

// The compiler immediately flags this as an error.
// You can't assign a String to an int.
year = message; // COMPILE ERROR!
```
This simple check prevents a massive category of bugs that are common in dynamically-typed languages.

---

### Example: Method Signature Errors

The compiler checks that you're calling methods that actually exist and using the correct number and types of arguments.

```java
String name = "Alice";

// Error 1: Method does not exist
name.substringg(0, 3); // COMPILE ERROR! (typo)

// Error 2: Wrong number of arguments
name.substring(0); // This is fine
name.substring(0, 3, 10); // COMPILE ERROR!

// Error 3: Wrong argument type
name.substring("start", "end"); // COMPILE ERROR!
```

---

### Example: Unused Variables

Modern compilers and IDEs will warn you about declared variables that are never used. This helps keep code clean and can reveal bugs of omission.

```java
public double calculateArea(int radius) {
    double pi = 3.14159;
    // This warning might indicate you forgot the next line!
    // return pi * radius * radius;
    return radius * radius; // Warning: Variable 'pi' is not used.
}
```

---

### Example: Unreachable Code

The compiler can detect code that can never be executed. This is almost always a sign of a logic error.

```java
public void greet(String name) {
    System.out.println("Hello, " + name);
    return;
    // The compiler knows this line can never be reached.
    System.out.println("Welcome!"); // COMPILE ERROR!
}
```

---

## Part 5: Tools of the Trade

The compiler is just the beginning. The Java ecosystem has powerful tools to go deeper.

- **Checkstyle:** Enforces a consistent coding style (e.g., indentation, naming conventions, spacing). Makes code easier to read.
- **SpotBugs** (or FindBugs): Analyzes your compiled bytecode to find common bug patterns.
  - *Example:* `myString == "hello"` instead of `myString.equals("hello")`.
  - *Example:* Forgetting to close a file stream.
- **SonarLint / SonarQube:** A suite of tools that combines style checking, bug patterns, and complex analysis (e.g., potential `NullPointerException`s).

Most modern IDEs (IntelliJ, Eclipse, VS Code) have excellent integration for these tools.

---

## Part 6: In-Class Exercise (15 mins)

**Goal:** Use static analysis to find and fix bugs in a small Java program.

1.  **Get the code:** I've provided a `Buggy.java` file.
2.  **Compile it:** Run `javac Buggy.java`. Note the errors the compiler finds for you. Fix them.
3.  **Run SpotBugs:** Once it compiles, run a static analysis tool like SpotBugs on the compiled `.class` file.
4.  **Analyze the report:** SpotBugs will generate a report of potential bugs and style issues. Discuss them with a partner.
5.  **Fix the bugs:** Fix the issues identified by SpotBugs.

I will provide the `Buggy.java` file and instructions for running the tools.

---

## Conclusion: The Power and Limits of Static Checking

- **Power:** Static checking is your automated first line of defense. It catches whole categories of bugs for free, every time you compile.
- **Limits:** It can't catch every bug. It can't know your *intent*. It doesn't understand the program's logic.

For logic bugs, we need **dynamic checking** (testing), which we'll cover in the next lecture.
