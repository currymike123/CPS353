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

Git/GitHub = required
Gradle = required
Eclipse = recommended
IntelliJ = allowed
VS Code = allowed
JUnit = required
Java = required!!!

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

This lecture will cover tools and practices to improve code quality.

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

