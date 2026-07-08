---
marp: true
theme: default
style: |
  section {
    font-size: 90%;
  }

---

# Lecture 1: Introduction to Version Control & Basic Git

---

## Today's Plan

1.  **The "Why":** What is Version Control?
2.  **The "What":** Introduction to Git
3.  **The "How":** Core Git Commands (`init`, `add`, `commit`)
4.  **Hands-On:** Creating and Tracking a Project

---

## Part 1: What is Version Control?

A **Version Control System (VCS)** is a tool that tracks changes to files over time.

Think of it as "undo" on steroids, or a complete history of your project.

---

## Why Use a VCS? (In Practice)

- **Scenario 1: The "Oops" Moment**
  - You delete a feature, save the file, and realize it was a huge mistake. Without a VCS, you're relying on your editor's undo buffer. With Git, you can simply revert to the last committed state.
- **Scenario 2: The "It Worked Yesterday" Problem**
  - You come back to your project after a week, and it's broken. You have no idea what you changed. With `git log`, you can see the exact history of changes and pinpoint where the bug was introduced.
- **Scenario 3: The "Two Features at Once" Dilemma**
  - You're working on a new login form, but you're asked to fix a critical bug immediately. With branches, you can save your in-progress work, switch to a new branch to fix the bug, then come back to your feature branch right where you left off.

---

## The Three Areas (A Visual)

This is the fundamental concept you need to understand.

```
+------------------+     git add      +-----------------+     git commit     +----------------+
|                  |----------------->|                 |------------------->|                |
| Working          |                  | Staging Area    |                    | .git directory |
| Directory        |<-----------------| (Index)         |                    | (Repository)   |
|                  |   git checkout   |                 |<------------------|                |
+------------------+                  +-----------------+   (staging)      +----------------+
```

---

## Part 3: Core Git Commands

- `git init`
- `git add`
- `git commit`
- `git status`
- `git log`
- `git diff`
- `git show`

---

## `git log` (With Options)

The default `git log` can be verbose. Try these options:

- `git log --oneline`: Shows a compact, one-line view of the history.
- `git log --graph`: Shows the commit history as a graph (very useful for branches).
- `git log --oneline --graph --decorate --all`: My personal favorite alias for a quick overview of the entire repository.

---

## `git diff`

- Shows the differences between your working directory and the staging area.
- In other words, it shows all the changes you've made that you *haven't't* staged yet.

```bash
# See all unstaged changes
$ git diff

# See the differences for a specific file
$ git diff main.java
```

---

## `git diff --staged`

- Shows the differences between the staging area and the last commit.
- This shows you what's in the "snapshot" you're about to commit.

---

## `git show`

- Shows the changes made in a specific commit.

```bash
# Show the most recent commit
$ git show

# Show a specific commit by its ID (from git log)
$ git show a1b2c3d4
```

---

## Part 4: Live Demo: Your First Repository



Let's walk through the entire basic workflow together.



---



### Step 1: Initialization



First, we create a directory and initialize Git inside it.



```bash

$ mkdir calculator

$ cd calculator

$ git init

Initialized empty Git repository in /home/mike/Desktop/calculator/.git/

```



**What happened?** Git created a hidden `.git` folder. This is your repository. **Never touch the files inside this folder directly.**



---



### Step 2: Create a File



Let's create our first Java file, `Calculator.java`.



```java

// src/Calculator.java

public class Calculator {

    public static void main(String[] args) {

        System.out.println("Hello from Calculator!");

    }

}

```



Now, let's check the status. This is the most important command in Git.



```bash

$ git status

On branch main

No commits yet

Untracked files:

  (use "git add <file>..." to include in what will be committed)

        Calculator.java

nothing added to commit but untracked files present (use "git add" to track)

```

**Key takeaway:** Git sees the file, but it's not tracking it yet.



---



### Step 3: Staging the File



We use `git add` to move our untracked file into the staging area.



```bash

$ git add Calculator.java

```



Let's check the status again:

```bash

$ git status

On branch main

No commits yet

Changes to be committed:

  (use "git rm --cached <file>..." to unstage)

        new file:   Calculator.java

```

**Key takeaway:** The file is now "staged". It's ready for the next commit (snapshot).



---



### Step 4: Making a Commit



We use `git commit` to save our staged changes into the repository's history.



```bash

$ git commit -m "feat: Initial implementation of Calculator"

[main (root-commit) a1b2c3d] feat: Initial implementation of Calculator

 1 file changed, 5 insertions(+)

 create mode 100644 Calculator.java

```

- The `-m` flag is for the commit message.

- "feat:" is a common convention for a commit that adds a new feature.

- `a1b2c3d` is the short hash (unique ID) of our commit.



**Key takeaway:** We have created our first permanent snapshot in the project's history.



---



### Step 5: Modifying a File



Now let's add a method to our calculator.



```java

// src/Calculator.java

public class Calculator {

    public int add(int a, int b) {

        return a + b;

    }



    public static void main(String[] args) {

        System.out.println("Hello from Calculator!");

    }

}

```



Check the status:

```bash

$ git status

On branch main

Changes not staged for commit:

  (use "git add <file>..." to update what will be committed)

  (use "git restore <file>..." to discard changes in working directory)

        modified:   Calculator.java

no changes added to commit (use "git add" or "git commit -a")

```



---



### Step 6: Viewing the Changes



Git knows the file is modified. But what are the changes? Use `git diff`.



```bash

$ git diff

diff --git a/Calculator.java b/Calculator.java

index e8e4ce9..d78a109 100644

--- a/Calculator.java

+++ b/Calculator.java

@@ -1,5 +1,9 @@

 public class Calculator {

+    public int add(int a, int b) {

+        return a + b;

+    }

+

     public static void main(String[] args) {

         System.out.println("Hello from Calculator!");

     }

 }

```

`+` indicates lines that were added.



---



### Step 7: Committing the Changes



Let's stage and commit our changes.



```bash

$ git add Calculator.java

$ git commit -m "feat: Add 'add' method to Calculator"

[main 4e5f6g7] feat: Add 'add' method to Calculator

 1 file changed, 4 insertions(+)

```



Now, let's look at our history with `git log --oneline`.



```bash

$ git log --oneline

4e5f6g7 (HEAD -> main) feat: Add 'add' method to Calculator

a1b2c3d feat: Initial implementation of Calculator

```

We can see our two commits, each with a unique ID and message.



---



## In-Class Exercise (10 minutes)



1.  In your `calculator` repository, add a `subtract` method to `Calculator.java`.

2.  Use `git status` and `git diff` to check your work.

3.  Stage the change.

4.  Commit the change with a descriptive message (e.g., "feat: Implement subtract method").

5.  Use `git log --oneline` to view the new history.

6.  **Bonus:** Use `git show HEAD` to see the details of your latest commit.



---



## Common Questions & Pitfalls



- **"I forgot to add a file to my last commit!"**

  - Add the file (`git add ...`), then run `git commit --amend --no-edit`. This will add the file to your *previous* commit. **Warning:** Only do this on commits you haven't pushed to a remote yet!



- **"What makes a good commit message?"**

  - Start with a type (e.g., `feat`, `fix`, `docs`, `style`, `refactor`).

  - Keep the subject line short (under 50 chars).

  - Use the imperative mood (e.g., "Add feature", not "Added feature").



---



## A Note on `.gitignore`



What if you have files you *don't* want to track? (e.g., compiled `.class` files, IDE configs, secret keys).



Create a file named `.gitignore` in your project's root directory. List the files and directories you want Git to ignore.



Example `.gitignore`:

```

# Compiled Java files

*.class



# IDE files

.idea/

*.iml



# Log files

*.log

```



---



## Next Time



- **Lecture 2:** Git Branching, Merging, and Collaboration

- We will cover how to work with branches and how to collaborate with others using remote repositories (like GitHub).
