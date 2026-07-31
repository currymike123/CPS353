# Software Engineering  
## Final Project

The overall project will be graded out of 100 points. Most (though not all) of the pieces are from the checkpoints, so make sure to incorporate any feedback from those to get everything in great shape, if you haven’t already.

## Functionality Requirements:

**Project Infrastructure:** Checkpoint 1

- A repository on github, with **branch protection** for 'main' requiring pull requests with approvals and passing status checks  
- A checkstyle status check that verifies everything in **checkstyle\_checks.xml** from Brightspace plus at least one **additional** check  
- A gradle status check that verifies that all the code **compiles** and all **tests pass**

**Documentation and Design**: Checkpoint 2

- A README with a system design diagram and details of the computation  
- 3 interface classes for APIs between different components of the system

**Testing:** Checkpoint 3

- At least one unit test for each component  
- One integration test verifying that the coordination and compute engine pieces work together  
- (Assignment 6\) TestMultiUser to verify that multiple users can make requests at the same time  
- Note: you will probably want additional tests to be confident in the overall functionality

**Working Implementation**: Checkpoint 4

- The engine should successfully compute the correct output for any given integer greater than zero  
-   
- (**New**) The engine should accept **arbitrarily large** numbers of inputs - if a user has a file with a few terrabytes of numbers, that should still work  
- (Checkpoint 7\) There should be a client of some sort that can be used to make requests of the engine

**Error Handling**: Checkpoint 5

- The engine should gracefully handle any invalid input (return an error to the user, adapt the computation to apply to the input, or log an error to the output file \= graceful handling; crashing/failing silently \= not graceful)

**Multithreading the engine**: Checkpoint 6

- Multiple users should be able to make simultaneous requests to the engine  
- The compute engine should be able to use multiple threads to compute the results more quickly than if it were running on a single CPU

**Network Calls**: Checkpoint 7

- Support cross-network calls with grpc between the client/end user and the computation coordination layer  
- Support cross-network calls with grpc between the computation engine and the data store layer.

**Performance Tuning**: Checkpoint 8

- Have a documented performance improvement, including a benchmark test, benchmark performance numbers, and what the improvement was. You'll want two versions of your API 3 (or whichever component is relevant), one with the old, slow version, and one with the new, fast version. Have your tests generally use the fast version so you can verify correctness.

**Something Extra** **(New)**

You've built a cool system, now have some fun with it\! Pick one of the previous checkpoints, or an entirely different topic, and go further with it. Some examples (you're welcome to use one of these, or pick your own):

- Investigate how to start up servers from within gradle, and use that to create an automated end-to-end testing of the grpc logic that runs along with the rest of the tests in github for every pull request  
- Create a fancier client that uses the cross-language abilities of grpc to connect a non-Java client (such as javascript in a web browser) to the Java server. **Note:** there are some tricky parts to this due to Http2 \- if you haven't taken Web Programming already, you may want to focus on just the code generation aspects. I’d recommend downgrading the grpc version in build.gradle to switch back to Http1 if you want to do this.  
- Set up producer/consumer multithreading to parallelize I/O as well as CPU multithreading  
- Extend the output of the engine to not just be text; create useful visualizations for the user either as a per-input computation or to summarize the computation job, and display those after a successful computation.  
- Something else\! If you aren't sure if you've picked something substantial enough, feel free to email me your ideas to double-check.

## Process Requirements

As always, any code changes should have nice descriptive commit messages and reviewed pull requests that pass all status checks

**Pair Programming**

For the final project, since we have dedicated class time to work on it, the process requirement will include **synchronous** collaboration. Have one person typing, and another one (or two) people reviewing live \- for the pull request, have the person who was doing the typing create the pull request, and the two reviewers can approve with a comment explaining that the review was done via pair programming.

Everyone in the group will need to be involved in at least one pair programming commit, although for groups of 3 you can choose to round-robin this requirement. 
