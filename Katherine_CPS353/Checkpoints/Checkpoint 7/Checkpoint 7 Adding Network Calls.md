# Software Engineering Checkpoint 7  
## Add Networking Calls

Finally, we'll add the 'User' box of the System Design Diagram\!

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when. 
   

## Functional Requirements

1. Set up a gRPC server for your network API layer \- you can move the exception handling logic from Checkpoint 5 into this layer if you'd prefer  
2. Create a basic frontend for your engine  
   1. Create a java client file with a main method  
   2. Set up gRPC and protocol buffers to support your user \<-\> compute server API (Network API 1, the controller/coordinator/manager component)  
   3. Allow a user to specify (via Scanner prompts, command line arguments, or other)  
      1. **either** a file to upload or a typed-in list of numbers for computation  
      2. An output file  
      3. Optionally, a delimiter to use for the output file  
   4. Provide a way to let the user know when the task is complete, and if it succeeded or failed  
      1. Optional: If you'd like to display some results to the user as well, and that makes sense for your compute engine, feel free\!  
           
3. Move the data store component (ProcessAPI) to its own process  
   1. Set up gRPC and protocol buffers to support your compute engine \<-\> data store API  
   2. Change the coordination component in the compute server (generally, the component that implements API 1\) to use protocol buffers to talk to your data store  
   3. Continue to use a test in-memory store for your junit tests

        **Hint**: This is much easier to do if you have the grpc client side implement the current process API \- that way none of your code that uses the process api needs to change

4. Manually run an end-to-end test of your system \- start the data store process, compute engine process, and client process, and verify that you pass in data and get results in both in-memory and file formats (for inputs) and file formats (for outputs)

   

5. Make sure everything is **merged** to the main branch, and that all the tests are compiling and passing. Once everything looks good, submit a link to your repo to Brightspace; I'll look at everything as of that timestamp, and you're free to make further edits without impacting this assignment.

## Checkpoint Submission

1. Make sure everything is **merged** to the main branch. Note that there are no provided tests for this checkpoint \- you'll need to make sure your testing is sufficient\!

2. Make sure you've addressed any feedback from checkpoint 6

3. On Brightspace, for Checkpoint 7, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
     - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
     - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs
