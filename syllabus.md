# CPS 353: Software Engineering

## Course Description
This course introduces fundamental principles and techniques of modern software construction. Students will learn how to build, test, and deploy robust, scalable applications. The course covers the entire development lifecycle, including environment setup, version control with Git, automated builds, testing methodologies, CI/CD, and collaborative practices. All concepts are grounded in the Java programming language, using industry-standard tools like Gradle, and JUnit.

## Course Philosophy
This course is guided by three core principles for building robust software:
- **Safe from bugs:** Correctness and robustness are paramount.
- **Easy to understand:** Code must be readable and maintainable.
- **Ready for change:** Software must be designed to adapt to new requirements.

## Schedule

### Weeks 1-2: Foundations: Dev Environment & Version Control
- **Topics:**
  - Course Introduction & Philosophy
  - Development Environment Setup (IDE, VIM Motions, and essential tools)
  - Introduction to Version Control with Git (basic commands, branching, merging)
  - Collaborative workflows with GitHub (Pull Requests, Code Reviews)

### Week 3-4: API Design & Project Kickoff
- **Topics:**
  - Designing clean and effective APIs
  - Introduction to Design Patterns
- **Project:**
  - **Term Project Part 1 Assigned (Infrastructure & Design)**

### Weeks 5-6: Building & Testing
- **Topics:**
  - Introduction to Build Tools (Gradle)
  - Managing Dependencies & Building JARs
  - The Importance of Testing: Writing Unit Tests with JUnit
  - Test-Driven Development (TDD) as a design practice

### Week 6: Documentation & Debugging
- **Topics:**
  - Writing Effective Documentation (Javadoc)
  - Code Review Best Practices
  - Debugging Techniques in an IDE

### Week 7: Exceptions & Generics
- **Topics:**
  - Handling errors gracefully with Exceptions
  - Java Generics for type-safe code

### Week 8: Midterm Exam
- **Midterm Review & Exam**
- **Project:**
  - **Term Project Part 1 Due, Part 2 Assigned (Implementation & Testing)**

### Week 9: Concurrency
- **Topics:**
  - Introduction to Multithreading
  - Applying concurrent programming patterns to the project

### Week 10: Networking & Remote Communication
- **Topics:**
  - Introduction to Networking, RPC (Remote Procedure Calls)
  - High-performance communication with gRPC

### Week 11: Performance Tuning
- **Topics:**
  - Profiling applications to identify performance bottlenecks
  - Strategies for performance optimization

### Week 12: Advanced CI/CD & Project Work
- **Topics:**
  - Introduction to CI/CD with GitHub Actions
- **Project:**
  - **Term Project Part 2 Due, Part 3 Assigned (Concurrency & CI/CD)**
  - Project Work Session

### Week 13: Project Work & Advanced Topics
- **Project:**
  - Project Work Session & Instructor Feedback
  - Advanced Topics & Project Q&A 
  - Agentic Coding: Leveraging AI tools for code generation and review

### Week 14: Project Presentations & Review
- **Project:**
  - **Final Project Presentations**
  - **Term Project Part 3 Due**
  - Course Review
- **Final Project Due**

### Week 15: Final Exam
- **Final Exam Review**
- **Final Exam**

## Projects
- **Term Project:** Throughout the semester, students will build and evolve a single, scalable web service using Java. The project is broken down into a series of checkpoints that build on each other, culminating in a final application that incorporates all concepts from the course. The goal is to build a robust, production-ready application.

### Project Components & Milestones:
The project will be developed in parts, with each part focusing on a key area of software construction:

- **Part 1: Project Infrastructure & Design (Weeks 5-8)**
  - Set up a version-controlled repository on GitHub with branch protection and automated status checks (Checkstyle, Gradle).
  - Design the system architecture, including a system diagram and API contracts for communication between components (`@NetworkAPI`, `@ProcessAPI`, `@ConceptualAPI`).
  - Define the core computation for the compute engine.

- **Part 2: Implementation & Testing (Weeks 8-12)**
  - Implement the core components of the compute engine: coordination, computation, and data storage.
  - Develop a comprehensive test suite, including unit tests for each component and integration tests to verify component interactions.
  - Implement robust error handling to gracefully manage invalid inputs and unexpected failures.

- **Part 3: Concurrency, Networking & Performance (Weeks 12-14)**
  - Enhance the compute engine to handle multiple simultaneous user requests using multi-threading.
  - Set up a full Continuous Integration/Continuous Deployment (CI/CD) pipeline using GitHub Actions to automate builds, testing, and deployments.
  - Integrate gRPC for efficient, cross-network communication between system components.
  - Identify and resolve performance bottlenecks through profiling and benchmarking.

The final project submission will be graded on functionality, design, documentation, testing, and adherence to process requirements (e.g., code reviews, commit history).

## Grading
- Homework: 25%
- Term Project: 25% (split between checkpoints and the final submission)
- Midterm Exam: 25%
- Final Exam: 25%
