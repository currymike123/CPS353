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

