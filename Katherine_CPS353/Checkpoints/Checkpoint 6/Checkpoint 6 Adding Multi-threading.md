# Software Engineering Assignment 6  
## Parallelize the Compute Engine

This week we'll be adding parallelism to the compute engine\!

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when. 
   

## Functional Requirements

1. Implement the testing harness so that the TestMultiUser test connects to your service \- this will be very similar to your ManualTestFramework from checkpoint 4\.  
   1. Download testHarness.zip from Brightspace; put the two java files in your 'test' folder \- depending on what custom checkstyle rules you have, you may need to edit the code to conform to your repo's style  
   2. Fix the 2 TODOs in TestMultiUser  
   3. Fix the 2 TODOs in TestUser  
   4. Create a test input file with the numbers: 1,15,10,5,2,3,8 Depending on what file format you chose for Assignment 4, this might be in a csv, text file, or other format. Call this file testInputFile.test, and add it to your repo under the 'test' folder  
   5. Verify that the TestMultiUser test now passes (grading note: I'll check that the files output partway through the test are correct too \- if you have a thorough testing framework already, you won't need to do anything extra here, but if you don't, you may want to use the debugger to verify that the test state makes sense during the test as well. For example, if your engine doesn't write anything at all to the output file, the test will pass JUnit but not count as correct for assignment purposes)

2. Create a **new multi-threaded implementation** of your NetworkAPI interface, specifically by making the calls to the ConceptualAPI component run on several threads at once   
   1. Decide on a way to have the two implementations share as much **logic** as possible \- this might involve static methods in either class or a utility class, or an abstract parent class  
   2. Pick a reasonable upper bound for the number of threads to use, and document this in your README  
   3. Use Executors.newFixedThreadPool to limit the number of threads to that upper bound  
   4. Update the TestMultiUser framework to use the multi-threaded implementation of your code; your **smoke tests** should still be **single-threaded**  
   5. Verify that TestMultiUser still passes  
        
3. **Optional**: Add multi-threading to the actual computation (depending on what computation you're using, this may or may not make sense)

## Checkpoint Submission

1. Make sure everything (including the TestMultiUser test from Brightspace from step 1\) is **merged** to the main branch.

2. Make sure you've addressed any feedback from checkpoint 5

3. On Brightspace, for Checkpoint 6, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
     - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
     - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs
