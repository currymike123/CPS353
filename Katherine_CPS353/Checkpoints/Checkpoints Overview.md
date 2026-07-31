# Checkpoint Introduction

The semester-long project for this class is both large and complex, and designed to illustrate the **process** of building large scale software. In order to manage the complexity, it's going to be broken down into a series of **checkpoints**. These are similar to small assignments, but with a key difference: rather than strict due dates, at which point you turn in whatever you have, checkpoints are focused on **successfully accomplishing the task**. 

## Deadlines

Checkpoints do not have strict due dates, but they do still have some constraints:

- the "recommended" deadline (what shows up as the due date in Brightspace): this is the date by which you should try to have the checkpoint done; we'll have covered all the material you need in class, and we'll be moving on to topics that assume you've completed the checkpoint. This is especially relevant for exams, which will assume you've had a chance to practice all the material on checkpoints that should be completed before the exam

- feedback on checkpoints can take **up to 4 days**, and subsequent checkpoints cannot be submitted until you've addressed the feedback. This limits how quickly you can move through the checkpoints; if you get several weeks behind, you may not have time to catch up before the end of the semester. 

Learning to manage your time through a large project that has many "soft" internal milestones, external dependencies that can cause delays, and a hard deadline several months later is an important skill for software engineering (fortuitously, it's also an important skill for many aspects of life). **Managing your time through the checkpoints is an explicit part of your grade** \- if you're unable to complete the project due to not handling the 4 day delay between checkpoints properly, you should expect that to negatively impact your grade.

## Submission Requirements

The idea behind checkpoints is that you should have a certain amount of functionality completed, and you should be building off the work done in previous checkpoints. In order to submit a checkpoint for grading/feedback, you must have two things completed:

- Respond to feedback from the previous checkpoint (does not apply to checkpoint 1\)  
- Merge the automated tests for that checkpoint to your main branch, and have those tests passing  

  **Checkpoint Tests**  
    
  Most checkpoints will have a set of tests available on Brightspace. These tests are **not exhaustive** \- just because the tests pass does not necessarily mean everything is done perfectly. The tests will tell you if you're **on the right track**, though \- if the tests are passing, that means you can get **substantive feedback** on your checkpoint. You can think of these as similar to email address validation on a website form: most websites will reject '123 Fake Street' as an email address, but allow '123Fake@Street.com' \- the idea behind the validation is to catch any confusion about what is actually being asked.
    
  **You should not edit these tests** unless you have explicit permission from the professor. If you edit the tests to get them to pass, your checkpoint submission will be sent back to you to fix rather than being graded so you can move on to the next checkpoint.  
  
  **How to handle a failing checkpoint test**
  
  Remember that the goal for these tests is to tell you if you're on the right track - if they aren't passing, something significant is missing or incorrect. You should figure out what that is - it's completely possible to get the tests to pass but have the code be incorrect, so if you focus on fixing the test without understanding why it's complaining, you're going to end up having a lot to fix as part of the feedback for that checkpoint.
    
## Grading  
    
  Each checkpoint will serve as a **first draft** of that aspect of your project \- it's not expected that you will complete each checkpoint flawlessly your first time through. Checkpoints are graded largely based on how well you've followed the **process** of building software \- ie, using feature branches, commits, and code reviews effectively. In contrast, at the end of the semester, the final project grade will be based on the functionality and code quality of your entire project **after you've incorporated feedback on each checkpoint**. 
  
## FAQ

Q: I submitted checkpoint 1 and 2, but can't see checkpoint 3!

A: Make sure you've received and responded to feedback on checkpoint 1 - feedback for each checkpoint must be addressed in the next checkpoint.


Q: The checkpoint is past the deadline in Brightspace, can I still submit it?

A: Yup, the checkpoint deadlines in Brightspace are just recommendations - if you get a little behind, that's ok, just **make sure you plan how to catch back up**. To simulate external dependencies, checkpoints cannot be submitted faster than one every 4 days.


Q: The checkpoint tests aren't passing, but I don't want to get behind - can I submit what I have?

A: No. Each checkpoint builds on the previous one, so if the checkpoint tests aren't passing, you won't be able to effectively move forward until they are. 
