# Software Engineering Checkpoint 4  
## Implementing the Compute Engine

This week we'll be building out the implementation of the compute engine, and making all the tests from checkpoint 3 start passing\!

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when. 
   

## Functional Requirements**

**Terminology:**  
In the steps below:  
'computation component' refers to your implementation of the @ConceptualApi interface  
'coordination component' refers to your implementation of the @NetworkApi interface  
'data storage component' refers to your implementation of the @ProcessApi interface

1. In the 'src' folder, implement the **computation** you chose and added to the README in the computation component of the engine. Remember to use good coding **style**\! Choose descriptive variable names, and break out sub-routines into their own methods.  
     
2. In the 'src' folder, implement the **coordination** component of the engine. This piece will do a couple of things, although exactly how it does these is up to you\!  
   1. Receive requests from the user to **start** the computation (the method signature for this will come from your API), and return a suitable result status back to the user  
   2. Request that the data storage component **read** integers from the location specified by the user   
   3. Pass the integers to the **compute** component  
   4. Request that the data storage component **write** the results to the output

      

3. In the 'src' folder, implement a version of the data storage component that can read and write to **user-specified files**. Right now, this will only be used by the unit tests from checkpoint 3\.

**Optional**: if you want to support additional input and output formats for your data storage layer (such as visualizations, json, etc), feel free to add more options that the user can specify\! 

4. Verify that all the unit and integration **tests** from Checkpoint 3 are now passing (may involve fixing any bugs they uncover\!). Once this is working, remove the filtering in your build.gradle file that excluded these tests from Github Actions

5. In the 'test' folder, add (at least) **one additional test** to your test suite (unit or integration) based on analyzing your implementation \- this could be based on code coverage results from your previous tests, a code review comment flagging something that looks fragile, or noticing a branching situation/edge case during implementation.

6. **From Brightspace** (not from a feature branch), download the checkpoint-4-tests.zip file, and put the unzipped contents in the test/ folder under the package project.checkpointtests. **On a new feature branch**, fill in the two TODO pieces of code in ManualTestingFramework. Verify that Checkpoint4TestSuite passes. **Note:** If necessary, you may update the input data format on line 20 of Checkpoint4TestSuite

7. Make sure everything is **merged** to the main branch, and that all status checks are passing. Once everything looks good, submit a link to your repo to Brightspace; I'll look at everything as of that timestamp, and you're free to make further edits without impacting this assignment.

## Checkpoint Submission

1. Make sure everything (including the checkpoint tests from Brightspace from step 6\) is **merged** to the main branch.

2. Make sure you've addressed any feedback from checkpoint 3

3. On Brightspace, for Checkpoint 4, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
     - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
     - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs
