---
marp: true
size: 16:9
theme: default
---

# Code Quality

---

## Course Goal

---
Build software

---

Build software

With other people


---

Build software

With other people

Effectively

---

Build software

With other people

Effectively

Over time

![bg right width:500px](img/Infrastructure%20Slides_0.png)

---

# Course Philosophy

1. Build a useful foundation.
    - Learn the theory of version control, testing, dependency management, code quality, and design patterns.

2. Practice with real tools.
    - Use Git, Gradle, Java, JUnit and other tools to build software.


---

# Development Ecosystem

Version Control + Local Checkout + Build Tool + IDE + Testing Framework + CI/CD 

 Git + Gradle + Eclipse/IntelliJ/VS Code + JUnit + GitHub Actions

---

# Supported vs. Allowed

- **Supported**: Tools, practices, and standards officially endorsed and recommended by the organization or project.
- **Allowed**: Tools, practices, and standards that are permitted but not officially recommended. No guarantees of support!

---

# Specific Tools

**Git/GitHub** = required
**Gradle** = required
**Eclipse** = recommended
**IntelliJ** = allowed
**VS Code** = allowed
**JUnit** = required
**Java** = required!!!

---

# Setup your IDE!

- Gather your tools and begin to set them up before the next lecture. 
- We will go into more detail about all the tools in the coming lectures.
- You should be able to write/compile/run Java code.

---

# What is Code Quality?

Code quality refers to the characteristics of code that make it reliable, maintainable, and easy to understand. High-quality code is:
- **Readable**: Easy for other developers to understand.
- **Maintainable**: Easy to modify and extend.
- **Reliable**: Functions correctly and is robust to errors.
- **Efficient**: Uses resources wisely.

---

# Code Review

Your code will be read by other developers, your future self, and more LLMs.

Best practices make the process:
- **Lightweight**: Easy to review and understand.
- **Effective**: Catches issues early and improves code quality.
- **Pleasant**: Encourages collaboration and knowledge sharing.

---

![bg center width:700px](img/Infrastructure%20Slides_20.png)

---

<style scoped>
section {
  font-size: 24px;
}
</style>

# Structure your code

Style **conventions** are aspects of code not enforced by the compiler but are important for readability and maintainability.

Clear and understandable:
```java
int getWidth() { 
    return width;
}

retangle.getWidth(); 
```
Unclear and confusing:
```java
int Width(){retun a};

b.Width();
```

Your code should be readable and understandable by other developers, including your future self.

---

# Structure your code

Typical style conventions include:
- Methods and variables begind with a lowercase letter. (e.g., `getWidth()`, `width`)
- Constants are in all uppercase letters with underscores separating words. (e.g., `MAX_WIDTH`)
- Classes and interfaces begin with an uppercase letter. (e.g., `Rectangle`, `TestCase`)

Optional style conventions:
- Indentation: tabs vs 2 spaces vs 4 spaces
- { on the same line vs on a new line

---

<style scoped>
section {
  font-size: 24px;
}
</style>

# Structure your code

**Commenting** your code is important for readability and maintainability. Comments should explain **why** something is done, not **what** is done. I can look at the code to see what it does. Your implementation could have been done in many different ways, but you chose this way. Why?

Don't just explain **what**:
```java
// Checks if password length is greater than or equal to 12
if (password.length() >= 12) {
    savePassword(password);
}
```

Explain **why**:
```java
// NIST 800-63B guidelines require a minimum of 12 characters to prevent dictionary attacks
if (password.length() >= 12) {
    savePassword(password);
}
```

---

# Structure your code

Remember good **object oriented design** principles:

- A **class** should have a single responsibility/concept.
- A **method** should have one task/behavior.

If you can't explain what a class or method does in one sentence, it probably has too many responsibilities and should be split into multiple classes or methods.

```java
getWidthAndHeight()
```

```java
getWidth()
getHeight()
```

---

# Structure your code

### Every rule has exceptions. 

Sometimes it is better to break the rules for clarity and maintainability.

```java
//Represents a deck of cards. Supports shuffling and dealing.

public class Deck {
    List<Card> cards;
    public void shuffle() {}
    public Card deal() {}
}
```

There are multiple sentences and an 'and', but there's a single 'data' concept and the two 'behaviors' are both closely related to the data and in separate methods. 


---

<style scoped>
section {
  font-size: 20px;
}
</style>

# Structure your code

### Bad examples:

```java
// Represents card numbers and suits.
public class Deck {
    List<Integer> cardNumbers;
    List<String> cardSuits;     
}
```

The "and" here is a red flag. Managing raw parallel lists creates fragile data structures. Cards should be **encapsulated** into their own class.

```java
/* Represents a deck of cards. Supports shuffling and coordinates placing pieces on a game board. */
public class Deck {
    List<Card> cards;
    GameBoard board;

    public void shuffle() {}
    public void placePieceOnBoard(Piece piece) {}
}
```

Here, the "and" is a true red flag. The two behaviors belong to entirely different domains. A deck of cards should not handle game board placement logic.


---

# Structure your code

Code should not be surprising:

Main.java

```java
System.out.println("Rectangle width: " + rectangle.getWidth());
```

Rectangle.java

```java
public int getWidth() {
    setHieght(3); // This is surprising! A getter should not have side effects.
    return width;
}
```

You should not be surprised by what a method does. If a method has side effects, it should be clearly documented and named appropriately.

---

<style scoped>
section {
  font-size: 25px;
}
</style>

# Structure your code

Manage your commit messages and history. 

- Each commit should represent a single logical change. 
- Avoid large commits that mix multiple changes together.
- Less than 200 lines of non-auto-generated code is a good rule of thumb for a single commit.
- A single feature/bug/task!
- Detailed description of the change.

![bg right width:550px](img/Infrastructure%20Slides_26.png)

---

# Formatting

Code formatters automatically apply a consistent style to your code. This eliminates debates over style and improves readability.

- **Tools for Java**:
    - `google-java-format`
    - IDE built-in formatters (Eclipse, IntelliJ)
- **EditorConfig**: Helps maintain consistent coding styles for multiple developers working on the same project across various editors and IDEs.

You can set up your IDE to auto-format code on save.

---

# Linting

Linters perform static analysis on your code to find potential issues, bugs, and stylistic errors without running it.

- **Checkstyle for Java**: A popular linter for Java that enforces a coding standard.
- **Linter Rules**: Linters have a set of configurable rules. You can disable rules for specific lines or files if needed.
- **Automated Fixes**: Some linters can automatically fix the issues they find.
- **Semgrep**: A powerful, multi-language static analysis tool that can be used to write custom rules.

---

# Testing

Testing is crucial for ensuring code correctness and preventing regressions.

- **Unit Tests**: Test individual components (e.g., a single class or method). JUnit is the standard for Java.
- **Integration Tests**: Test how multiple components work together.
- **Functional Tests**: Test end-to-end scenarios from the user's perspective.
- **Test-Driven Development (TDD)**: A development process where you write tests before writing the implementation.
- **Mocking**: Using mock objects to simulate the behavior of real dependencies. Mockito is a popular mocking framework for Java.

---

## Code Coverage

Code coverage measures the percentage of your code that is executed by your tests.

- It helps identify untested parts of your codebase.
- Tools like JaCoCo can generate coverage reports for Java projects.
- **Warning**: High coverage does not guarantee high-quality tests. Focus on writing meaningful tests rather than just chasing a high coverage number.

---

# IDEs and Build Tools

- **IDEs (Integrated Development Environments)**: Tools like **Eclipse** and **IntelliJ IDEA** provide powerful features for Java development:
    - Constant compilation and error checking.
    - Syntax highlighting and auto-completion.
    - Automated refactoring and code generation.
    - Debugging tools.
- **Build Tools**: **Gradle** and **Maven** are the standard build automation tools for Java. They manage dependencies, compile code, run tests, and package your application.

---

# Version Control & Collaboration

- **Git & GitHub**: Git is the version control system, and GitHub is a platform for hosting repositories and collaborating on code.
- **Code Reviews**: A process where other developers review your code before it is merged. It is a critical practice for improving code quality and sharing knowledge.
- **Pull Requests**: The standard mechanism on GitHub for proposing changes and initiating code reviews.
- **Pair Programming**: Two developers work together at one workstation. One writes code while the other reviews it in real-time.

---

# Continuous Integration (CI)

CI is the practice of automatically building and testing your code every time a change is pushed to the repository.

- **CI Services**: GitHub Actions, Jenkins, CircleCI.
- **CI Pipeline**: A typical CI pipeline will:
    1.  Run the formatter and linter.
    2.  Compile the code.
    3.  Run all tests.
- **Benefits**:
    - Catches integration issues early.
    - Provides fast feedback to developers.
    - Automates the release process.

---

# Continuous Deployment (CD)

Continuous Deployment is an extension of CI that automatically deploys your code to production after it passes all tests.

- The Missing Semester website is an example of CD. When we push changes to the lecture notes, the site is automatically rebuilt and deployed.
- Other artifacts like application binaries or Docker images can also be deployed automatically.

---

# Pre-commit Hooks

Pre-commit hooks are scripts that run automatically before each commit.

- You can use them to run formatters and linters to ensure that no poorly-formatted code or code with linter errors is committed.
- The `pre-commit` framework is a popular tool for managing pre-commit hooks.

---

# Command Runners

Command runners simplify running project-specific commands.

- Instead of memorizing `gradle checkstyleMain`, you can have a simple command like `gradle check`.
- **Gradle** and **Maven** have built-in support for defining custom tasks.

---

# Regular Expressions (Regex)

Regex is a powerful language for pattern matching in text.

- Used in many command-line tools (`grep`) and IDEs for searching and replacing text.
- Can be used in testing frameworks to run a subset of tests.
- Most programming languages, including Java, have built-in support for regex.
- Online tools like `regex101.com` can help you build and debug regex patterns.

